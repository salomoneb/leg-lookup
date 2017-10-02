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
				text: "Copy Members", 
				people: ""
			}
		}, 
		watch: {
			committeeMembers() {
				// Remove the selection when the member listings change
				window.getSelection().removeAllRanges()
			}
		},
		methods: {
			// https://stackoverflow.com/questions/2044616/select-a-complete-table-with-javascript-to-be-copied-to-clipboard
			copyText() {
				// Reselects whenever button clicked
				window.getSelection().removeAllRanges()

				var body = document.body, range, sel		
				var el = this.$parent.$refs.table

				if (document.createRange && window.getSelection) {
					range = document.createRange()
					sel = window.getSelection()
					try {
						range.selectNodeContents(el)
						sel.addRange(range)				
				} catch (e) {
						range.selectNode(el)
						sel.addRange(range)
					}
				} 
				else if (body.createTextRange) {
					range = body.createTextRange()
					range.moveToElementText(el)
					range.select()
				}	
				document.execCommand("copy")	
			}
		}
	}
</script>