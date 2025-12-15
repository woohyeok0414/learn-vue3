<template>
	<div></div>
</template>

<script>
import { reactive, ref } from 'vue';

export default {
	setup() {
		//ref 로 선언한 것은 .value를 생략해도 된다.
		const count = ref(0);
		const state = reactive({
			count,
		});
		count.value++;
		count.value++;
		// console.log(count.value);
		// console.log('state.count: ', state.count);

		//배열에 담았을 때는 .value를 넣어야한다.
		const message = ref('Hello');
		const arr = reactive([message]);
		console.log('arr[0] ', arr[0]);

		return {};
	},
};
</script>

<style lang="scss" scoped></style>
