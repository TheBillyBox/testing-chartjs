<template>
  <div id="app">
	<div>
		<h1>Rainy vs sunny days in Menorca </h1>
    <canvas id="planet-chart"></canvas>
	</div>
  </div>
</template>


<script>
import planetChartData from './chart-data.js';
import Chart from 'chart.js';
	export default {
		name: 'app',
		components: {
			
		},
		data: function () {
			return {
				planetChartData: planetChartData,
			}
		},
		methods: {
			createChart (chartId, chartData) {
				const ctx = document.getElementById(chartId);
				const myChart = new Chart(ctx, {
					type: chartData.type,
					data: chartData.data,
					options: chartData.options,
				})
				console.log(myChart)
			}
		},
		mounted() {
			this.createChart('planet-chart', this.planetChartData);
		},
}
</script>

<style>
canvas{
	max-width: 75%;
	display: flex;
	margin: auto;
}
h1{
	margin: auto;
	text-align: center;
}
</style>