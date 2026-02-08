<script>
    import { onMount } from 'svelte';
    import Chart from "chart.js/auto";

    let chartCanvas;

    onMount(async (promise) => {
        const ctx = document.getElementById('myChart');

        new Chart(ctx, {
            type: 'doughnut',
            data: {
                labels: [ 'January', 'February', 'March' ],
                datasets: [
                    {
                        label: 'My Doughnut Chart',
                        data: [40, 20, 12],
                        backgroundColor: [
                            'rgba(255, 99, 132, 0.2)',
                            'rgba(54, 162, 235, 0.2)',
                            'rgba(255, 206, 86, 0.2)',
                        ],
                        borderColor: [
                            'rgba(255, 99, 132, 1)',
                            'rgba(54, 162, 235, 1)',
                            'rgba(255, 206, 86, 1)',
                        ],
                        borderWidth: 1
                    }
                ]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false
            }
        });
    });

</script>

<div style="width: 400px; height: 400px">
    <canvas bind:this={chartCanvas} id="myChart" width="400" height="400"></canvas>
</div>

