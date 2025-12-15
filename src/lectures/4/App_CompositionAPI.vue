<template>
	<div>
		<h2>반응형 메시지</h2>
		<p>{{ reactiveMessage }}</p>
		<button v-on:click="addReactiveMessage">Add message</button>
		<h2>일반 메시지</h2>
		<p>{{ noramlMessage }}</p>
		<button v-on:click="addNormalMessage">Add message</button>
	</div>
</template>

<script>
import { isRef, onBeforeMount, onMounted, ref } from 'vue';

export default {
	setup() {
		console.log('setup()');
		const reactiveMessage = ref('Hello Reactive Message');
		const addReactiveMessage = () => {
			reactiveMessage.value = reactiveMessage.value + '!';
		};

		console.log('isRef(reactiveMessage)', isRef(reactiveMessage));

		let noramlMessage = 'Hello Normal Message';
		const addNormalMessage = () => {
			noramlMessage = noramlMessage + '!';
		};

		console.log('isRef(noramlMessage)', isRef(noramlMessage));

		onMounted(() => {
			console.log('onMounted');
		});

		onBeforeMount(() => {
			console.log('onBeforeMounted');
		});

		return {
			reactiveMessage,
			noramlMessage,
			addReactiveMessage,
			addNormalMessage,
		};
	},
};
</script>

<style lang="scss" scoped></style>
