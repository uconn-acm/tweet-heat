<template>
	<v-card dark hover class="mx-auto pa-3" color="blue" width="450">
		<stock-chart :data="twitterData" title="Twitter" />
		<stock-chart :data="marketData" title="Market" />

		<v-card-text>
			<div class="display-1 font-weight-thin text-xs-center">Stock Ticker</div>
		</v-card-text>
	</v-card>
</template>

<script>
import StockChart from './stock-chart.vue';

export default {
	name: 'ChartsComparision',

	components: {
		StockChart
	},

	props: {
		twitterData: {
			type: Array,
			required: true
		},
		marketData: {
			type: Array,
			required: true
		}
	}
};
</script>
