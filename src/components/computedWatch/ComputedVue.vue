<template>
	<div>
		<p>{{ message }}</p>
		<p>{{ reversedMessage }}</p>
	</div>
</template>

<script>
export default {
	name: 'ComputedVue',
	data() {
		return {
			message: 'Hello'
		}
	},
	computed: {
		reversedMessage: function() {
			return this.message.split('').reverse().join('')
		}
	}
}
</script>

<style scoped>
	
</style>