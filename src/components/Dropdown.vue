<template>
	<div class="dropdowns">
		<select class="chamber-dropdown" v-model="chamber" v-on:change="getCommitteeList()">
			<option disabled value="">Select a Chamber</option>
			<option>House</option>
			<option>Senate</option>
		</select>
		<select class="committee-dropdown" v-if="chamber" v-model="committee">
			<option disabled value="">Select a Committee</option>
			<option v-for="committee in committees" :value="committee.api_uri"> {{ committee.name }}</option>
			<!-- <option :value="chamber">{{ getCommitteeList() }}</option> -->
			<!-- <option v-for="post in posts" :value="post"> {{ parseResults() }} works as an </option> -->
		</select>
		<results :lawmakerData="committee"></results>
<!-- 		<table>
			<tr v-for="committee in committees"><td>{{committee.userId}}</td><td>{{committee.body}}</td></tr>
		</table> -->
		<!-- <results :lawmakerData="committee"></results> -->
	</div>
</template>

<script>
	import Results from './Results'
	import axios from 'axios';
  var lawmakers = [
    {name: "tom", occupations: [
      { 
        job: "accountant", 
        hobby: "lawyer"
      }  
    ]},
    {name: "dick", occupations: [
      { 
        job: "doctor", 
        hobby: "businessman"
      }  
    ]},
    {name: "harry"}
  ]	
	export default {
		name: "dropdown", 
		data: function() {
			return {
				chamber: false,
				committee: "",
				committees: [],
				errors: [],
				chamber: "",
				lawmakers: lawmakers
			}
		},
		// created: function() {

		// }, 
		methods: {
			parseResults: function() {
				var item = this.posts
				var results = item.results
				console.log(results)
			}, 
			getChamber: function() {
				return this.chamber
			}, 
			getCommitteeList: function() {
				if (this.chamber != "") {
					console.log(`https://api.propublica.org/congress/v1/115/${this.chamber.toLowerCase()}/committees.json`)
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