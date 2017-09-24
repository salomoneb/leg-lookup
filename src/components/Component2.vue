<template>
	<div class="comp2">
		<select v-bind:value="currentValue" v-on:change="currentValue = $event.target.value" >
			<option>{{comp2}} + 1</option>
			<option>{{comp2}} + 2</option>
			<option>{{comp2}} + 3</option>
		</select>
		<p>{{currentValue}}</p>
	</div>
</template>

<script>
	export default {
		name: "component2",
		props: ["comp2"],
		data: function() {
			return {
				message: "", 
				myModel: "", 
				currentValue: "", 
				pvalue: ""
			}
		}, 
		watch: {
			currentValue(val) {
				console.log(val)
			}
		}
	}
</script>