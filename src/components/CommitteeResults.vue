<template >
	<div class="results">
		<img v-if="loading" src="https://upload.wikimedia.org/wikipedia/commons/b/b1/Loading_icon.gif">	
		<p>{{ committeeId }}</p>	
		
<!-- 		<div class="facts" v-if="committeeData" @change="showMembers">
			<h2>Quick Facts:</h2>
			<p>Name: {{ facts.name }}</p>
			<p>Committee Website: <a v-bind:href="facts.url">{{ facts.url }}</a></p>
		</div> -->

<!-- 		<table class="committee-members">
			<tr v-for="member in members">
				<td>{{ member.name}}</td>
				<td>{{ member.state}}</td>
				<td>{{ member.party}}</td>
			</tr>
		</table> -->

		</div>
</template>
 
<script>
	export default {
		name: "committeeresults", 
		props: ["committeeId"], 
		data: function() {
			return {
				loading: false,
				facts: [],
				members: [], 
				errors: [], 
			}
		}, 
		computed: {
			showMembers: function() {
				// return axios.request("get", {
				// 	url: `https://api.propublica.org/congress/v1/115/${this.chamber.toLowerCase()}/committees/${this.committeeData.toLowerCase()}.json`, 
				// 	headers: {
				// 		"X-API-Key": "2eX2Dxe43hYuiIoXVeBg463BY8rpXVfY1PzbIUBu"
				// 	}
				// })
				// .then(response => {
				// 	console.log("")
		  //     this.facts = response.data.results[0]
		  //     this.members = this.facts.current_members

		  //     this.chamberControl = this.chamber
		  //     this.loading = false
		  //   })
		  //   .catch(e => {
		  //     this.errors.push(e)
		  //   })					
			}
		}

	}
</script>
<style>
	.results {
		display: flex;
		flex-direction: row;
		align-items: flex-start;
		justify-content: center;
	}
</style>