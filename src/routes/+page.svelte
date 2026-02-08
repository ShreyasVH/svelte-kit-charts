<script>
    import BarChart from '../components/barChart.svelte'
    import DoughnutChart from '../components/doughnutChart.svelte'
    import { page } from '$app/stores';

    $: type = $page.url.searchParams.get('type') ?? 'bar';

    let dataDoughnut1 = {
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
    };

    let dataDoughnut2 = {
        type: 'doughnut',
        data: {
            labels: [ 'April', 'May', 'June' ],
            datasets: [ { label: 'My Doughnut Chart 2', data: [33, 25, 18],
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
    };
</script>

<div>
    <div style="margin-bottom: 30px">
        <a href={'?type=bar'}>Bar Chart</a>
        &nbsp;
        <a href={'?type=doughnut'}>Doughnut Chart</a>
    </div>
    {#if type === 'bar'}
        <BarChart />
    {:else if type === 'doughnut'}
        <DoughnutChart data={dataDoughnut1} id="doughnut1" />
        <DoughnutChart data={dataDoughnut2} id="doughnut2" />
    {/if}
</div>