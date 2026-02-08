<script>
    import BarChart from '../components/barChart.svelte'
    import DoughnutChart from '../components/doughnutChart.svelte'
    import { page } from '$app/stores';

    $: type = $page.url.searchParams.get('type') ?? 'bar';
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
        <DoughnutChart />
    {/if}
</div>