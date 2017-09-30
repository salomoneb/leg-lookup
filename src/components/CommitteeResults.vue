<template >
	<div id="committee-results">
		<div class="committee-facts" v-if="facts">
			<h2>Quick Facts</h2>
			<p><span class="bold">Name: </span>{{facts.name}}</p>
			<p><span class="bold">Chair: </span>{{facts.chair}}</p>
			<p><span class="bold"># of Members: </span>{{facts.current_members.length}}</p>
			<p><span class="bold">Website: </span><a v-bind:href="facts.url" target="_blank">{{facts.url}}</a></p>
		</div>
		<table class="committee-members" v-if="members.length" ref="table">
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
		<copybutton :committeeMembers="members"></copybutton>
	</div>
</template>
 
<script>
	import copybutton from "./CopyButton"

	export default {
		name: "committeeresults", 
		props: ["committeeInfo", "chamber"], 
		data: function() {
			return {
				errors: "", 
				facts: "",
				loading: false,
				members: ""
			}
		}, 
		watch: {
			committeeInfo(val) {
				if (this.committeeInfo !== "") {									
					this.members = this.committeeInfo.current_members	
					this.facts = this.committeeInfo	
				}
			}, 
			chamber(val) {
				if (this.chamber !== "") {
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
	  }, 
	  components: {
	  	copybutton
	  }
	}
</script>