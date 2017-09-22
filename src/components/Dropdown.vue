<template>
	<div class="dropdowns">
		<select class="chamber-dropdown" v-model="chamber" v-on:change="getCommitteeList()">
			<option disabled value="">Select a Chamber</option>
			<option>House</option>
			<option>Senate</option>
		</select> 
		<img v-if="chamber && !committees.length" src="https://upload.wikimedia.org/wikipedia/commons/b/b1/Loading_icon.gif">
		<select class="committee-dropdown" v-if="chamber && committees.length" v-model="committee">
			<option disabled value="">Select a Committee</option>
			<option v-for="committee in committees" :value="committee.api_uri"> {{ committee.name }}</option>
		</select>
		<results v-if="committee" :committeeUrl="committee"></results>
	</div>
</template>

<script>
	import Results from "./Results"
	import axios from "axios"

	export default {
		name: "dropdown", 
		data: function() {
			return {
				committee: "",
				chamber: "",
				committees: [],
				errors: []
			}
		},
		methods: {
			getCommitteeList: function() {
				if (this.chamber != "") {
					return axios.request("GET", {
						url: `https://api.propublica.org/congress/v1/115/${this.chamber.toLowerCase()}/committees.json`, 
						headers: {
							"X-API-Key": "2eX2Dxe43hYuiIoXVeBg463BY8rpXVfY1PzbIUBu"
						}
					})
					.then(response => {
			      // JSON responses are automatically parsed.
			      this.committees = response.data.results[0].committees
			    })
			    .catch(e => {
			      this.errors.push(e)
			    })			
				}
			}
		},
		components: { Results }
	}
</script>