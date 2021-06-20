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
                    label: 'test 11',
                    borderColor: 'rgba(255,0,0)',
                    background: false,
                    data: [{
                        x: '2021-06-16 10:00:00',
                        y: 75
                    }, {
                        x: '2021-06-17 10:00:00',
                        y: 11
                    }, {
                        x: '2021-06-18 10:00:00',
                        y: 88
                    }, {
                        x: '2021-06-19 10:00:00',
                        y: 64
                    },
                    ]
                },
                {
                    label: 'test 2',
                    borderColor: 'rgba(100,255,100)',
                    background: false,
                    data: [{
                        x: '2021-06-16 10:00:00',
                        y: 211
                    }, {
                        x: '2021-06-17 10:00:00',
                        y: 233
                    }, {
                        x: '2021-06-18 10:00:00',
                        y: 292
                    }, {
                        x: '2021-06-19 10:00:00',
                        y: 187
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
                    ],
                    yAxes: [{
                        id: 'test 11',
                        type: 'linear',
                        position: 'left',
                    }, {
                        id: 'test 2',
                        type: 'linear',
                        position: 'right',
                        ticks: {
                            min: 0,
                            max: 300,
                        },
                    }]
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