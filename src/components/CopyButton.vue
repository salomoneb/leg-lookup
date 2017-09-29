<template >
	<div id="copy-button-container">
		<button v-if="committeeMembers.length" class="copy-button" type="button" v-on:click="copyText()">{{text}}</button>
	</div>
</template>
 
<script>
	export default {
		name: "copybutton",
		props: ["committeeMembers"], 
		data: function() {
			return {
				text: "Button stuff", 
				people: ""
			}
		}, 
		methods: {
			copyText(el) {
			// var body = document.body, range, sel;		
			// if (document.createRange && window.getSelection) {
			// 	range = document.createRange();
			// 	sel = window.getSelection();
			// 	sel.removeAllRanges();
			// 	try {
			// 		range.selectNodeContents(el);
			// 		sel.addRange(range);
			// } catch (e) {
			// 		range.selectNode(el);
			// 		sel.addRange(range);
			// 	}
			// } else if (body.createTextRange) {
			// 		range = body.createTextRange();
			// 		range.moveToElementText(el);
			// 		range.select();
			// 	}		
				console.log(this.$parent)		
			}
		}
	}
</script>