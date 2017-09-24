<template>
	<div class="committee-selection" v-if="chamberCommittees"> 
		<select class="committee-select" v-model="committees">
			<option disabled value="">Pick a committee</option>
			<option v-for="committee in chamberCommittees" :test="committee.id">{{ committee.name }}</option>
		</select>
		<p>{{committees}}</p>
	</div>
</template>

<script>
	import committeeresults from "./CommitteeResults"

	export default {
		name: "committeedropdown", 
		props: ["chamberCommittees", "chamberValue"],
		data: function() {
			return {
				committees: null,
				committee: "",
				errors: [], 
				loading: false, 
				control: ""
			}
		}, 
		watch: {
			committees(val) {
				// console.log(this.committees)
				console.log(this.control)
			}
		}
	}
</script>