<script>
    import Line from "svelte-chartjs/src/Line.svelte"

    export let currency;

    window.onload = function() {
        init();
    };


    function init() {

        var ctx = document.getElementById('myChart').getContext('2d');
        var myChart = new Chart(ctx, {
            type: 'line',
            data: {
                datasets: [{
                    label: 'test 1',
                    borderColor: 'rgba(255,0,0)',
                    background: false,
                    data: [{
                        x: '2021-06-16 10:00:00',
                        // x: 1604082854,
                        y: 23
                    }, {
                        x: '2021-06-17 10:00:00',
                        // x: 1614082854,
                        y: 20
                    }, {
                        x: '2021-06-18 10:00:00',
                        // x: 1624082854,
                        y: 21
                    }, {
                        x: '2021-06-19 10:00:00',
                        // x: 1634082854,
                        y: 26
                    },
                    ]
                },
                {
                    label: 'test 2',
                    borderColor: 'rgba(100,255,100)',
                    background: false,
                    data: [{
                        x: '2021-06-16 10:00:00',
                        // x: 1604082854,
                        y: 21
                    }, {
                        x: '2021-06-17 10:00:00',
                        // x: 1614082854,
                        y: 23
                    }, {
                        x: '2021-06-18 10:00:00',
                        // x: 1624082854,
                        y: 22
                    }, {
                        x: '2021-06-19 10:00:00',
                        // x: 1634082854,
                        y: 27
                    },]
                }
                ]
            },
            options: {
                scales: {
                    y: {
                        beginAtZero: true,
                    },
                    xAxes: [
                        {
                            type: 'time',
                            position: 'bottom',
                            time: {
                                unit: 'day',
                                unitStepSize: 1,
                                displayFormats: {
                                    'day': 'YYYY MMM DD'
                                },
                            },
                        },
                    ]
                },
                maintainAspectRatio: false,
            },
        });
    }
</script>


<style>
    .chart-container {
        margin: 0 auto;
        width: 80%;
    }
</style>

<div class="chart-container">
    <canvas id="myChart" width="200" height="400"></canvas>
</div>