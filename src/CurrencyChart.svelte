<script>
    import Line from "svelte-chartjs/src/Line.svelte"

    export let currency;

    let data = {
        datasets: [{
            label: 'test 1',
            data: [{
                x: 1472194961,
                y: 37
            }, {
                x: 1472281361,
                y: 55
            }, {
                x: 1472367761,
                y: 883
            },
            ]
        }, {
            label: 'test C',
            data: [{
                x: 1472410961,
                y: 2
            }, {
                x: 1472324561,
                y: 13
            }, {
                x: 1472238161,
                y: 783
            }]
        }]
    };

    let options = {
        tooltips: {
            callbacks: {
                title(datasets) {
                    var time = new Date(datasets[0].xLabel * 1000);
                    return (time.getMonth() + 1) + '/' + time.getDate() + ' ' + time.getHours();
                }
            }
        },
        scales: {
            xAxes: [
                {
                    type: 'linear',
                    position: 'bottom',
                    ticks: {
                        callback(value) {
                            var time = new Date(value * 1000);
                            return (time.getMonth() + 1) + '/' + time.getDate() + ' ' + time.getHours();
                        }
                    }
                }
            ]
        },
        maintainAspectRatio: false,
    }
</script>


<style>
    .chart-container {
        margin: 0 auto;
        width: 80%;
    }
</style>

<div class="chart-container">
    <Line
            data={data}
            width={1100}
            height={250}
            options={options}
    />
</div>