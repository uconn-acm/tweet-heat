<template>
	<v-app>
		<v-toolbar app>
			<v-toolbar-title class="headline text-uppercase">
				<span>Tweet</span>
				<span class="font-weight-light">Heat</span>
			</v-toolbar-title>
		</v-toolbar>

		<v-content>
			<v-sparkline
				v-for="data in value"
				auto-draw
				:auto-draw-duration="1000"
				:gradient="gradient"
				:key="data[0]"
				:smooth="16"
				:value="data"
			/>

			<v-btn @click="addData">Add graph</v-btn>
		</v-content>
	</v-app>
</template>

<script>
export default {
	name: 'App',
	mounted() {
		setInterval(() => this.addData(), 5000);
	},

	data() {
		return {
			value: [[0, 2, 5, 9, 5, 10, 3, 5, 0, 0, 1, 8, 2, 9, 0]],
			gradient: ['#00c6ff', '#F0F', '#FF0']
		};
	},

	methods: {
		addData() {
			this.value[0].shift();
			this.value[0].push(3);
		}
	}
};
</script>
