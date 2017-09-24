<template>
	<div class="component1">
		<select v-model="component1">
			<option disabled value=""></option>
			<option v-for="item in message" :value="item.text">{{item.text}}</option>
		</select>
		<component2 :comp2="component1"></component2>
	</div>
</template>

<script>
	import component2 from './Component2'
	export default {
		name: "component1",
		data: function() {
			return {
				message: [
					{ text: "message1" },
					{ text: "message2" },
					{ text: "message3" }
				],
				component1: ""
			}
		}, 
		components: {
			component2
		}
	}
</script>