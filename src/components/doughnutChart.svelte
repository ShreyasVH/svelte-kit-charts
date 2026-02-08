<script>
    import { onMount } from 'svelte';
    import Chart from "chart.js/auto";

    let chartCanvas;
    export let data;
    export let id;

    onMount(async (promise) => {
        const ctx = document.getElementById(id);

        new Chart(ctx, data);
    });

</script>

<div style="width: 400px; height: 400px; display: inline-block">
    <canvas bind:this={chartCanvas} id={id} width="400" height="400"></canvas>
</div>

