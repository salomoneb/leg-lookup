<template>
	<div class="results" v-if="committeeUrl" @change="committeeMembers">
		<ul>
			<li v-for="member in members">{{ member.name }}</li>
		</ul>
	</div>
</template>
 
<script>
	import axios from "axios"
	// Add API call to the committee endpoint, add table to this template where committee data will be displayed
	export default {
		name: "results", 
		props: ["committeeUrl"], 
		data: function() {
			return {
				members: [], 
				errors: []
			}
		}, 
		computed: {
			committeeMembers: function() {
				return axios.request("GET", {
					url: this.committeeUrl, 
					headers: {
						"X-API-Key": "2eX2Dxe43hYuiIoXVeBg463BY8rpXVfY1PzbIUBu"
					}
				})
				.then(response => {
		      // JSON responses are automatically parsed.
		      this.members = response.data.results[0].current_members
		      console.log(this.members)
		    })
		    .catch(e => {
		      this.errors.push(e)
		    })	
			}
		}	
	}
</script>