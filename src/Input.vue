<template>
<div>
	<input type="text" :value="message" @input="changeMessage">
	<p>{{ msg }}</p>
</div>
</template>

<script>
	export default {
		props: ['msg'],
		data() {
			return {
				message: ''
			}
		},
		methods: {
			changeMessage(event) {
				this.message = event.target.value;
				this.$emit('messageChanged', this.message); // $ sign always tells that this is built-in method
			}
		}
	}
</script>