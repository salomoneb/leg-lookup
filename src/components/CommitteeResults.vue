<template >
	<div class="committee-results">
		<div class="committee-facts" v-if="facts">
			<h2>Quick Facts:</h2>
			<p>Name: {{facts.name}}</p>
			<p>Chair: {{facts.chair}}</p>
			<p>Number of Members: {{facts.current_members.length}}</p>
			<p>Website: <a v-bind:href="facts.url" target="_blank">{{facts.url}}</a></p>
		</div>
		<table class="committee-members" v-if="members.length">
			<tr class="member-headers">
				<th>Name</th>
				<th>State</th>
				<th>Party</th>
				<th>Chamber</th>
			</tr>
			<tr class="member-info" v-for="member in members">
				<td>{{member.name}}</td>
				<td>{{member.state}}</td>
				<td>{{member.party}}</td>
				<td>{{member.chamber | capitalize}}</td>
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
				facts: "",
				loading: false,
				facts: "", 
				errors: "", 
			}
		}, 
		watch: {
			committeeInfo(val) {
				if (this.committeeInfo !== "") {
						this.members = this.committeeInfo.current_members	
						this.facts = this.committeeInfo	
						console.log(this.facts)
				}
			}, 
			chamber(val) {
				if (this.chamber !== "") {
					console.log(val)
					this.members = ""
					this.facts = ""
				}
			}
		}, 
	  filters: {
	    capitalize: function(value) {
	      if (!value) {
	      	return ""
	      } 
	      value = value.toString()
	      return value.charAt(0).toUpperCase() + value.slice(1)
	    }
	  }
	}
</script>
<style>
</style>