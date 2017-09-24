<template>
	<div class="committee-selection" v-if="chamberCommittees"> 
		<select class="committee-select" v-model="committees">
			<option disabled value="">Pick a committee</option>
			<option v-for="committee in chamberCommittees" v-bind:value="committee.id" >{{ committee.name }}</option>
		</select>
		<committeeresults :committeeInfo="committeeData"></committeeresults>
	</div>
</template>

<script>
	import committeeresults from "./CommitteeResults"
	import axios from "axios"
	export default {
		name: "committeedropdown", 
		props: ["chamberCommittees", "chamberName"],
		data: function() {
			return {
				chamber: "",
				committees: "",
				committeeData: "",
				errors: [], 
				loading: false, 
			}
		}, 
		watch: {
			chamberCommittees(val) {
				this.committees = ""			
			}, 
			chamberName(val) {
				this.chamber = val
			}, 
			committees(val) {
				if (this.committees !== "") {
					axios.request("get", {
						url: `https://api.propublica.org/congress/v1/115/${this.chamberName.toLowerCase()}/committees/${this.committees}.json`, 
						headers: {
							"X-API-Key": "2eX2Dxe43hYuiIoXVeBg463BY8rpXVfY1PzbIUBu"
						}
					})
					.then(response => {
						this.committeeData = response.data.results[0]
			      this.loading = false
			    })
			    .catch(e => {
			      this.errors.push(e)
			    })						
				}
			}
		}, 
		components: {
			committeeresults
		}
	}
</script>