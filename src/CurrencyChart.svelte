<script>
    import Chart from 'svelte-frappe-charts';

    export let currency;

    let data = {
        labels: ['Sun', 'Mon', 'Tues', 'Wed', 'Thurs', 'Fri', 'Sat'],
        datasets: [
            {
                values: [10, 12, 3, 9, 8, 15, 9]
            }
        ]
    };
</script>


<style>
    .chart-container {
        margin: 0 auto;
        width: 80%;
    }
</style>

<div class="chart-container">
    <Chart data={data} type="line"/>
</div>