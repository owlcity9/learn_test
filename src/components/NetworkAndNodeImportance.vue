<template>
    <div id="networkandnodeimportance">
        <div id="div_3_1_1"></div>
    </div>
</template>
<script>
import * as echarts from 'echarts';
export default {
    data() {
        return{
            
        }
    },
    mounted() {
        this.draw_network_evalu();
    },
    computed: {

    },
    methods: {
        draw_network_evalu() {
            var chartDom = document.getElementById('div_3_1_1');
            var myChart = echarts.init(chartDom);
            var option;

            option = {
                color: ['#99CCFF', '#66CCCC', '#99CC66'],
                xAxis: [{
                    type: 'value',
                    gridIndex: 0
                },
                {
                    type: 'value',
                    gridIndex: 1
                },
                {
                    type: 'category',
                    data: ['a', 'b', 'c', 'd', 'e', 'f', 'h', 'i', 'j', 'k'],
                    gridIndex: 2
                }
                ],
                yAxis: [{
                    type: 'category',
                    data: ['nodes', 'edges', 'density', 'A_degree', 'N_diameter', 'A_length'],
                    gridIndex: 0,
                    axisLabel: {
                        show: true
                    }
                },
                {
                    type: 'category',
                    data: ['nodes', 'edges', 'density', 'A_degree', 'N_diameter', 'A_length'],
                    gridIndex: 1,
                    axisLabel: {
                        show: false
                    }
                },
                {
                    type: 'value',
                    gridIndex: 2
                }
                ],
                grid: [{
                    top: '5%',
                    left: '15%',
                    right: '47.5%',
                    bottom: '50%'
                },
                {
                    top: '5%',
                    left: '57.5%',
                    right: '5%',
                    bottom: '50%'
                },
                {
                    top: '60%',
                    left: '10%',
                    right: '5%',
                    bottom: '5%'
                }
                ],
                series: [{
                    // 变化前  度中心性
                    data: [100, 90, 20, 21.6, 40, 36],
                    type: 'bar',
                    xAxisIndex: 0,
                    yAxisIndex: 0
                },
                {
                    data: [60, 50, 60, 20, 20, 20],
                    type: 'bar',
                    xAxisIndex: 1,
                    yAxisIndex: 1
                },
                ///////////////////////////////////////////////////////////////////////////////////
                // 变化前，度中心性
                // {
                //     data: [0.1, 0.1, 0.3, 0.2, 0.1, 0.1, 0.1, 0.1, 0.1,0.6],
                //     type: 'line',
                //     name: 'Degree Centrality',
                //     xAxisIndex: 2,
                //     yAxisIndex: 2
                // },
                //变化后，度中心性
                // {
                //     data: [0.036, 0.036, 0.05, 0.0625, 0.045, 0.045, 0.045, 0.045,0.045,0.0714],
                //     type: 'line',
                //     name: 'Closeness Centrality',
                //     xAxisIndex: 2,
                //     yAxisIndex: 2
                // },
                {
                    data: [0, 0, 1, 1, 1, 0, 0, 0, 0, 0],
                    type: 'line',
                    name: 'Between Centrality',
                    xAxisIndex: 2,
                    yAxisIndex: 2
                },
                    //////////////////////////////////////////////////////////////////////////////////////////
                    //变化前，接近中心性
                    // {
                    //     data: [45, 20, 10, 50, 30, 10, 10, 37, 45],
                    //     type: 'line',
                    //     name: 'Closeness Centrality',
                    //     xAxisIndex: 2,
                    //     yAxisIndex: 2
                    // },
                    // //变化后，接近中心性
                    // {
                    //     data: [40, 15, 15, 40, 20, 9, 8, 20, 30],
                    //     type: 'line',
                    //     name: 'Closeness Centrality',
                    //     xAxisIndex: 2,
                    //     yAxisIndex: 2
                    // },
                    // ////////////////////////////////////////////////////////////////////////////////////////////////
                    // //变化前，接近中心性
                    // {
                    //     data: [100, 46, 70, 60, 50, 70, 65, 45, 76],
                    //     type: 'line',
                    //     name: 'Between Centrality',
                    //     xAxisIndex: 2,
                    //     yAxisIndex: 2
                    // },
                    // //变化后，接近中心性
                    // {
                    //     data: [90, 40, 60, 55, 45, 60, 60, 40, 70],
                    //     type: 'line',
                    //     name: 'Between Centrality',
                    //     xAxisIndex: 2,
                    //     yAxisIndex: 2
                    // }
                ]
            };

            option && myChart.setOption(option);
        }
    },
    watch: {

    },
    components: {

    }
}
</script>
<style>
#networkandnodeimportance {
    width: 100%;
    height: 100%;
}

#div_3_1_1 {
    width: 100%;
    height: 100%;
}
</style>