<template>
	<div id="committee-selection" v-if="chamberCommittees"> 
		<select class="committee-select" v-model="committees">
			<option disabled value="">Pick a Committee</option>
			<option v-for="committee in chamberCommittees" v-bind:value="committee.id" >{{ committee.name }}</option>
		</select>
	  <errormessage v-if="errors !==''" :errorMsgs="errors"></errormessage>
		<img v-if="loading" :src="loaderIcon">	
		<committeeresults :committeeInfo="committeeData" :chamber="chamberName"></committeeresults>
	</div>
</template>

<script>
	import committeeresults from "./CommitteeResults"
	import errormessage from "./ErrorMessage"
	import axios from "axios"
	export default {
		name: "committeedropdown", 
		props: ["chamberCommittees", "chamberName", "loaderIcon"],
		data: function() {
			return {
				chamber: "",
				committees: "",
				committeeData: "",
				errors: "",
				loading: false 
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
					this.loading = true
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
			    .catch(err => {
			      this.errors = err
			      console.log(err)
			      this.loading=false
			    })						
				}
			}
		}, 
		components: {
			committeeresults, errormessage
		}
	}
</script>