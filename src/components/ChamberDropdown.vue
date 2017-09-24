<template>
	<div class="chamber-selection">
		<p>{{prompt}}</p>
		<select class="chamber-select" v-model="chamber">
			<option disabled value="">Pick a Chamber</option>
			<option>House</option>
			<option>Senate</option>
			<option>Joint</option>
		</select> 
		<committeedropdown :chamberCommittees="committees" :chamberName="chamber"></committeedropdown>
	</div>
</template>

<script>
	import committeedropdown from "./CommitteeDropdown"
	import axios from "axios"
	export default {
		name: "chamberdropdown", 
		data: function() {
			return {
				chamber: "",
				committees: "",
				prompt: "Find information on a federal committee"
			}
		}, 
		watch: {
			chamber(val) {
				axios.request("get", {
					url: `https://api.propublica.org/congress/v1/115/${this.chamber.toLowerCase()}/committees.json`, 
					headers: {
						"X-API-Key": "2eX2Dxe43hYuiIoXVeBg463BY8rpXVfY1PzbIUBu"
					}
				})
				.then(response => {
					this.committees = response.data.results[0].committees
		      this.loading = false
		    })
		    .catch(e => {
		      this.errors.push(e)
		    })				
			}
		},
		components: {
			committeedropdown
		}
	}
</script>