<template>
	<div class="results">
		<h3> {{ returnLawmakers() }} </h3>
	</div>
</template>

<script>
	import axios from 'axios';

	// Add API call to the committee endpoint, add table to this template where committee data will be displayed
	export default {
		name: "results", 
		props: ["lawmakerData"],
		methods: {
			returnLawmakers: function() {
				var item = this.lawmakerData
				console.log(this.lawmakerData)
				return item
			}
		}
	}
</script>