<template>
	<div>
		<h2 v-if="visible">Hello Vue3!</h2>
		<h2 v-else>false 입니다.</h2>
		<button v-on:click="visible = !visible">toggle</button>
		<hr />
		<button v-on:click="type = 'A'">toggle A</button>
		<button v-on:click="type = 'B'">toggle B</button>
		<button v-on:click="type = 'C'">toggle C</button>
		<button v-on:click="type = 'D'">toggle D</button>
		<h2 v-if="type === 'A'">A 입니다.</h2>
		<h2 v-else-if="type === 'B'">B 입니다.</h2>
		<h2 v-else-if="type === 'C'">C 입니다.</h2>
		<h2 v-else>A, B, C 가 아닙니다.</h2>
		<hr />
		<template v-if="visible">
			<h1>TITLE</h1>
			<p>Paragraph 1</p>
			<p>Paragraph 2</p>
		</template>
		<hr />
		<!--v-show 와 v-if 차이는 v-show는 display none처리한다.-->
		<h1 v-show="ok">Title 입니다.</h1>
		<button v-on:click="ok = !ok">show toggle</button>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		const visible = ref(true);

		const type = ref('A');

		const ok = ref(true);

		return { visible, type, ok };
	},
};
</script>

<style lang="scss" scoped></style>
