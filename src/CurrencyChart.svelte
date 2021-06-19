<script>
    import Line from "svelte-chartjs/src/Line.svelte"

    export let currency;

    window.onload = function() {
        init();
    };
    var d = new Date();
    var t = d.getTime();

    let data = {
        datasets: [{
            label: 'test 1',
            data: [{
                x: '2021-06-16 10:00:00',
                y: 37
            }, {
                x: '2021-06-17 10:00:00',
                y: 55
            }, {
                x: '2021-06-18 10:00:00',
                y: 232
            }, {
                x: '2021-06-19 10:00:00',
                y: 112
            }]
        }, {
            label: 'test - '+ t,
            data: [{
                x: '2021-06-16 10:00:00',
                y: 22
            }, {
                x: '2021-06-17 10:00:00',
                y: 33
            }, {
                x: '2021-06-18 10:00:00',
                y: 77
            }, {
                x: '2021-06-19 10:00:00',
                y: 44
            }]
        }]
    };

    let options = {
        // tooltips: {
        //     callbacks: {
        //         // title(datasets) {
        //         //     var time = new Date(datasets[0].xLabel * 1000);
        //         //     return (time.getMonth() + 1) + '/' + time.getDate() + ' ' + time.getHours();
        //         // }
        //     }
        // },
        // scales: {
        //     xAxes: [
        //         {
        //             type: 'linear',
        //             position: 'bottom',
        //             // ticks: {
        //             //     // callback(value) {
        //             //     //     var time = new Date(value * 1000);
        //             //     //     return (time.getMonth() + 1) + '/' + time.getDate() + ' ' + time.getHours();
        //             //     // }
        //             // }
        //         }
        //     ]
        // },
        xAxis: {
            type: 'datetime'
        },
        yAxis: {
            title: {
                text: 'Dollars'
            }
        },
        maintainAspectRatio: false,
    }

    function init() {

        var ctx = document.getElementById('myChart').getContext('2d');
        var myChart = new Chart(ctx, {
            type: 'line',
            data: {
                datasets: [{
                    label: 'test 1',
                    borderColor: 'rgba(255,0,0)',
                    data: [{
                        x: '2021-06-16 10:00:00',
                        y: 23
                    }, {
                        x: '2021-06-17 10:00:00',
                        y: 20
                    }, {
                        x: '2021-06-18 10:00:00',
                        y: 21
                    }, {
                        x: '2021-06-19 10:00:00',
                        y: 26
                    }]
                }, {
                    label: 'test - '+ t,
                    borderColor: 'rgba(0,255,0)',
                    background: false,
                    data: [{
                        x: '2021-06-16 10:00:00',
                        y: 22
                    }, {
                        x: '2021-06-17 10:00:00',
                        y: 24
                    }, {
                        x: '2021-06-18 10:00:00',
                        y: 22
                    }, {
                        x: '2021-06-19 10:00:00',
                        y: 25
                    }]
                }]
            },
            options: {
                scales: {
                    y: {
                        beginAtZero: true,
                    }
                },
                maintainAspectRatio: false,
                backgroundColor: false,
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