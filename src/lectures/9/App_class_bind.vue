<template>
	<div
		class="text"
		:class="[isActive ? 'active-class' : 'class', errorClass, classObject]"
	>
		텍스트 입니다.
	</div>
	<button v-on:click="toggle">toggle</button>
	<button v-on:click="hasError = !hasError">toggleError</button>
</template>

<script>
import { reactive, ref, computed } from 'vue';

export default {
	setup() {
		const isActive = ref(true);
		const hasError = ref(false);

		const toggle = () => {
			isActive.value = !isActive.value;
		};

		// const classObject = reactive({
		// 	'text-danger': true,
		// 	active: true,
		// });

		const classObject = computed(() => {
			return {
				'text-danger': true && true,
				active: true && true,
				'text-blue': true,
			};
		});

		const activeClass = ref('active');
		const errorClass = ref('error');

		return { isActive, toggle, hasError, classObject, activeClass, errorClass };
	},
};
</script>

<style scoped>
.active {
	font-weight: 900;
}

.text-danger {
	color: red;
}
</style>
