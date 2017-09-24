<template >
	<div class="results">
		<img v-if="loading" src="https://upload.wikimedia.org/wikipedia/commons/b/b1/Loading_icon.gif">	
		<!-- <h1>{{ committeeInfo }}</h1>	 -->
		
<!-- 		<div class="facts" v-if="committeeData" @change="showMembers">
			<h2>Quick Facts:</h2>
			<p>Name: {{ facts.name }}</p>
			<p>Committee Website: <a v-bind:href="facts.url">{{ facts.url }}</a></p>
		</div> -->

		<table class="committee-members" v-if="members.length">
			<tr v-for="member in members">
				<td>{{ member.name}}</td>
				<td>{{ member.state}}</td>
				<td>{{ member.party}}</td>
			</tr>
		</table>

		</div>
</template>
 
<script>
	export default {
		name: "committeeresults", 
		props: ["committeeInfo", "chamber"], 
		data: function() {
			return {
				members: "",
				loading: false,
				facts: [], 
				errors: "", 
			}
		}, 
		watch: {
			committeeInfo(val) {
				if (this.committeeInfo !== "") {
						console.log(this.members)
						this.members = this.committeeInfo.current_members				
				}
			}, 
			chamber(val) {
				if (this.chamber !== "") {
					console.log(val)
					this.members = ""
				}
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