<script>
	let chartData;
	import { onMount } from 'svelte';
	import Chart from "chart.js/auto";

	let ctx;
	let chartCanvas;

	onMount(async (promise) => {
      const ctx = document.getElementById('myChart');

        new Chart(ctx, {
          type: 'bar',
          data: {
            labels: [ 'January', 'February', 'March' ],
                datasets: [
                    {
                        label: 'My Bar Chart',
                        data: [40, 20, 12],
                        backgroundColor: 'rgba(255, 99, 132, 0.2)',
                        borderColor: 'rgb(255, 99, 132)',
                        borderWidth: 1
                    }
                ]
          },
          options: {
            scales: {
              y: {
                beginAtZero: true
              }
            },
            responsive: true,
            maintainAspectRatio: false
          }
        });
	});

</script>

<canvas bind:this={chartCanvas} id="myChart" width="400" height="400"></canvas>
