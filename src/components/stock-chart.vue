<template>
	<v-card color="rgba(0, 0, 0, 0.12)" flat>
		<v-card-title class="justify-center">{{ title }}</v-card-title>
		<v-sparkline
			:gradient="gradient"
			:line-width="3"
			:smooth="16"
			:value="data"
		/>
	</v-card>
</template>

<script>
export default {
	name: 'StockChart',

	props: {
		data: {
			type: Array,
			required: true
		},
		title: {
			type: String,
			required: true
		}
	},

	data() {
		return {
			gradient: ['rgba(255, 255, 255, .7)']
		};
	}
};
</script>
