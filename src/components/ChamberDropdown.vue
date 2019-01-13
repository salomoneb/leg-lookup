<template>
	<div id="chamber-selection">
		<select class="chamber-select" v-model="chamber">
			<option disabled value="">Pick a Chamber</option>
			<option>House</option>
			<option>Senate</option>
			<option>Joint</option>
		</select>
		<errormessage v-if="errors !==''" :errorMsgs="errors"></errormessage>
		<committeedropdown :chamberCommittees="committees" :chamberName="chamber" :loaderIcon="loader"></committeedropdown>
		<img v-if="loading" :src="loader">
	</div>
</template>

<script>
	import committeedropdown from "./CommitteeDropdown"
	import errormessage from "./ErrorMessage"
	import axios from "axios"

	export default {
		name: "chamberdropdown",
		data() {
			return {
				chamber: "",
				committees: "",
				errors: "",
				loader: require("@/assets/images/loader.svg"),
				loading: false
			}
		},
		watch: {
			chamber(val) {
				if (this.chamber !== "") {
					this.errors = ""
					this.loading = true
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
			    .catch(err => {
			      this.errors = err
			      this.loading=false
			    })
				}
			}
		},
		components: {
			committeedropdown, errormessage
		}
	}
</script>