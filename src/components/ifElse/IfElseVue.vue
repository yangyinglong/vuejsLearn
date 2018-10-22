<template>
	<div>
		<template v-if="loginType === 'username'">
			<label>Username</label>
			<input placeholder="Enter your username" key="username-input">
		</template>
		<template v-else>
			<label>Email</label>
			<input placeholder="Enter your email address" key="email-input">
		</template>
		<button @click="changeLoginType"> Toggle login type </button>
	</div>
</template>

<script>
export default {
	name: 'IfElseVue',
	data() {
		return {
			loginType: 'username'
		}
	},
	methods: {
	  changeLoginType: function () {
	  	if (this.loginType === 'username') {
	  		this.loginType = 'email address'
	  	}
	  	else {
	  		this.loginType = 'username'
	  	}
	    
	  }
	}
	
}
</script>

<style scoped>
	
</style>