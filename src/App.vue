<template>
	<v-app>
		<v-toolbar app>
			<v-toolbar-title class="headline text-uppercase">
				<span>Tweet</span>
				<span class="font-weight-light">Heat</span>
			</v-toolbar-title>
		</v-toolbar>

		<v-content>
			<v-container fluid>
				<charts-comparison
					:twitterData="twitterData"
					:marketData="marketData"
				/>
			</v-container>
		</v-content>
	</v-app>
</template>

<script>
import ChartsComparison from './components/charts-comparison.vue';

export default {
	name: 'App',

	components: {
		ChartsComparison
	},

	mounted() {
		setInterval(() => this.updateData(), 1000);
	},

	data() {
		return {
			twitterData: [0, 2, 5, 9, 5, 10, 3, 5, 0, 0, 1, 8, 2, 9, 0],
			marketData: [0, 3, 7, 3, 7, 4, 9, 5, 8, 5, 3, 2, 2, 2, 5, 2]
		};
	},

	methods: {
		updateData() {
			this.twitterData.shift();
			this.twitterData.push(Math.floor(Math.random() * 10));
			this.marketData.shift();
			this.marketData.push(Math.floor(Math.random() * 10));
		}
	}
};
</script>
