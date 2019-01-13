<template>
	<div class="error-status">
		<p>Uh oh, we got the following error:</p>
		<p class="error-message">{{errorMsgs.message}}</p>
		<p>Refresh your page and try again.</p>
	 </div>
</template>

<script>
	export default {
		name: "errormessage",
		props: ["errorMsgs"]
	}
</script>