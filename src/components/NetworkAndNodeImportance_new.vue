<template>
    <div id="networkandnodeimportance_new">
        <div id="div_3_1_1"></div>
        <div id="div_3_1_2"></div>
    </div>
</template>
<script>
import * as echarts from 'echarts';

export default {
    data() {
        return {}
    },
    mounted() {
        this.drawstructrueimportance();
        this.drawnodeimportance();
    },
    computed: {},
    methods: {
        drawnodeimportance() {
            var chartDom = document.getElementById('div_3_1_2');
            var myChart = echarts.init(chartDom);
            var option;

            // prettier-ignore
            const hours = [
                '12a', '1a', '2a', '3a', '4a', '5a', '6a',
                '7a', '8a', '9a', '10a', '11a',
                '12p', '1p', '2p', '3p', '4p', '5p',
                '6p', '7p', '8p', '9p', '10p', '11p'
            ];
            // prettier-ignore
            const days = [
                'Saturday', 'Friday', 'Thursday',
                'Wednesday'
            ];
            // prettier-ignore
            const data = [[0, 0, 5], [0, 1, 1], [0, 2, 0], [0, 3, 0], [0, 4, 0], [0, 5, 0], [0, 6, 0], [0, 7, 0], [0, 8, 0], [0, 9, 0], [0, 10, 0], [0, 11, 2], [0, 12, 4], [0, 13, 1], [0, 14, 1], [0, 15, 3], [0, 16, 4], [0, 17, 6], [0, 18, 4], [0, 19, 4], [0, 20, 3], [0, 21, 3], [0, 22, 2], [0, 23, 5], [1, 0, 7], [1, 1, 0], [1, 2, 0], [1, 3, 0], [1, 4, 0], [1, 5, 0], [1, 6, 0], [1, 7, 0], [1, 8, 0], [1, 9, 0], [1, 10, 5], [1, 11, 2], [1, 12, 2], [1, 13, 6], [1, 14, 9], [1, 15, 11], [1, 16, 6], [1, 17, 7], [1, 18, 8], [1, 19, 12], [1, 20, 5], [1, 21, 5], [1, 22, 7], [1, 23, 2], [2, 0, 1], [2, 1, 1], [2, 2, 0], [2, 3, 0], [2, 4, 0], [2, 5, 0], [2, 6, 0], [2, 7, 0], [2, 8, 0], [2, 9, 0], [2, 10, 3], [2, 11, 2], [2, 12, 1], [2, 13, 9], [2, 14, 8], [2, 15, 10], [2, 16, 6], [2, 17, 5], [2, 18, 5], [2, 19, 5], [2, 20, 7], [2, 21, 4], [2, 22, 2], [2, 23, 4], [3, 0, 7], [3, 1, 3], [3, 2, 0], [3, 3, 0], [3, 4, 0], [3, 5, 0], [3, 6, 0], [3, 7, 0], [3, 8, 1], [3, 9, 0], [3, 10, 5], [3, 11, 4], [3, 12, 7], [3, 13, 14], [3, 14, 13], [3, 15, 12], [3, 16, 9], [3, 17, 5], [3, 18, 5], [3, 19, 10], [3, 20, 6], [3, 21, 4], [3, 22, 4], [3, 23, 1]];
            const title = [];
            const singleAxis = [];
            const series = [];
            days.forEach(function (day, idx) {
                title.push({
                    textBaseline: 'middle',
                    top: ((idx + 0.5) * 100) / 4 + '%',
                    text: day,
                    textStyle: {
                        fontsize: 1
                    }
                });
                singleAxis.push({
                    left: '8%',
                    type: 'category',
                    boundaryGap: false,
                    data: hours,
                    top: (idx * 100) / 4 + 5 + '%',
                    height: 100 / 4 - 15 + '%',
                    // bottom:'20%',
                    axisLabel: {
                        interval: 2
                    }
                });
                series.push({
                    singleAxisIndex: idx,
                    coordinateSystem: 'singleAxis',
                    type: 'scatter',
                    data: [],
                    symbolSize: function (dataItem) {
                        return dataItem[1] * 2;
                    }
                });
            });
            data.forEach(function (dataItem) {
                series[dataItem[0]].data.push([dataItem[1], dataItem[2]]);
            });
            option = {
                color: ['#99CCFF', '#84CED4'],
                tooltip: {
                    position: 'top'
                },
                // title: title,
                singleAxis: singleAxis,
                series: series
            };

            option && myChart.setOption(option);


        },
        drawstructrueimportance() {
            var chartDom = document.getElementById('div_3_1_1');
            var myChart = echarts.init(chartDom);
            var option;

            option = {
                color: ["#66CCCC", "#CCFF66", "#FF99CC", "#99CCFF"],
                series: [{
                    name: 'Nightingale Chart',
                    type: 'pie',
                    radius: [3, 30],
                    center: ['10%', '20%'],
                    roseType: 'area',
                    itemStyle: {
                        borderRadius: 30,
                        borderWidth: 3,
                        borderColor: 'white'
                    },
                    label: {
                        show: false
                    },
                    data: [{
                        value: 40,
                        name: 'rose 1'
                    },
                    {
                        value: 38,
                        name: 'rose 2'
                    },
                    {
                        value: 32,
                        name: 'rose 3'
                    },
                    {
                        value: 30,
                        name: 'rose 4'
                    }
                    ]
                },
                {
                    name: 'Nightingale Chart',
                    type: 'pie',
                    radius: [3, 30],
                    center: ['30%', '20%'],
                    roseType: 'area',
                    itemStyle: {
                        borderRadius: 30,
                        borderWidth: 3,
                        borderColor: 'white'
                    },
                    label: {
                        show: false
                    },
                    data: [{
                        value: 40,
                        name: 'rose 1'
                    },
                    {
                        value: 38,
                        name: 'rose 2'
                    },
                    {
                        value: 32,
                        name: 'rose 3'
                    },
                    {
                        value: 30,
                        name: 'rose 4'
                    }
                    ]
                },
                {
                    name: 'Nightingale Chart',
                    type: 'pie',
                    radius: [3, 30],
                    center: ['50%', '20%'],
                    roseType: 'area',
                    itemStyle: {
                        borderRadius: 30,
                        borderWidth: 3,
                        borderColor: 'white'
                    },
                    label: {
                        show: false
                    },
                    data: [{
                        value: 40,
                        name: 'rose 1'
                    },
                    {
                        value: 38,
                        name: 'rose 2'
                    },
                    {
                        value: 32,
                        name: 'rose 3'
                    },
                    {
                        value: 30,
                        name: 'rose 4'
                    }
                    ]
                },
                {
                    name: 'Nightingale Chart',
                    type: 'pie',
                    radius: [3, 30],
                    center: ['70%', '20%'],
                    roseType: 'area',
                    itemStyle: {
                        borderRadius: 30,
                        borderWidth: 3,
                        borderColor: 'white'
                    },
                    label: {
                        show: false
                    },
                    data: [{
                        value: 40,
                        name: 'rose 1'
                    },
                    {
                        value: 38,
                        name: 'rose 2'
                    },
                    {
                        value: 32,
                        name: 'rose 3'
                    },
                    {
                        value: 30,
                        name: 'rose 4'
                    }
                    ]
                },
                {
                    name: 'Nightingale Chart',
                    type: 'pie',
                    radius: [3, 30],
                    center: ['90%', '20%'],
                    roseType: 'area',
                    itemStyle: {
                        borderRadius: 30,
                        borderWidth: 3,
                        borderColor: 'white'
                    },
                    label: {
                        show: false
                    },
                    data: [{
                        value: 40,
                        name: 'rose 1'
                    },
                    {
                        value: 38,
                        name: 'rose 2'
                    },
                    {
                        value: 32,
                        name: 'rose 3'
                    },
                    {
                        value: 30,
                        name: 'rose 4'
                    }
                    ]
                },
                {
                    name: 'Nightingale Chart',
                    type: 'pie',
                    radius: [3, 30],
                    center: ['10%', '65%'],
                    roseType: 'area',
                    itemStyle: {
                        borderRadius: 30,
                        borderWidth: 3,
                        borderColor: 'white'
                    },
                    label: {
                        show: false
                    },
                    data: [{
                        value: 40,
                        name: 'rose 1'
                    },
                    {
                        value: 38,
                        name: 'rose 2'
                    },
                    {
                        value: 32,
                        name: 'rose 3'
                    },
                    {
                        value: 30,
                        name: 'rose 4'
                    }
                    ]
                },
                {
                    name: 'Nightingale Chart',
                    type: 'pie',
                    radius: [3, 30],
                    center: ['30%', '65%'],
                    roseType: 'area',
                    itemStyle: {
                        borderRadius: 30,
                        borderWidth: 3,
                        borderColor: 'white'
                    },
                    label: {
                        show: false
                    },
                    data: [{
                        value: 40,
                        name: 'rose 1'
                    },
                    {
                        value: 38,
                        name: 'rose 2'
                    },
                    {
                        value: 32,
                        name: 'rose 3'
                    },
                    {
                        value: 30,
                        name: 'rose 4'
                    }
                    ]
                },
                {
                    name: 'Nightingale Chart',
                    type: 'pie',
                    radius: [3, 30],
                    center: ['50%', '65%'],
                    roseType: 'area',
                    itemStyle: {
                        borderRadius: 30,
                        borderWidth: 3,
                        borderColor: 'white'
                    },
                    label: {
                        show: false
                    },
                    data: [{
                        value: 40,
                        name: 'rose 1'
                    },
                    {
                        value: 38,
                        name: 'rose 2'
                    },
                    {
                        value: 32,
                        name: 'rose 3'
                    },
                    {
                        value: 30,
                        name: 'rose 4'
                    }
                    ]
                },
                {
                    name: 'Nightingale Chart',
                    type: 'pie',
                    radius: [3, 30],
                    center: ['70%', '65%'],
                    roseType: 'area',
                    itemStyle: {
                        borderRadius: 30,
                        borderWidth: 3,
                        borderColor: 'white'
                    },
                    label: {
                        show: false
                    },
                    data: [{
                        value: 40,
                        name: 'rose 1'
                    },
                    {
                        value: 38,
                        name: 'rose 2'
                    },
                    {
                        value: 32,
                        name: 'rose 3'
                    },
                    {
                        value: 30,
                        name: 'rose 4'
                    }
                    ]
                },
                {
                    name: 'Nightingale Chart',
                    type: 'pie',
                    radius: [3, 30],
                    center: ['90%', '65%'],
                    roseType: 'area',
                    itemStyle: {
                        borderRadius: 30,
                        borderWidth: 3,
                        borderColor: 'white'
                    },
                    label: {
                        show: false
                    },
                    data: [{
                        value: 40,
                        name: 'rose 1'
                    },
                    {
                        value: 38,
                        name: 'rose 2'
                    },
                    {
                        value: 32,
                        name: 'rose 3'
                    },
                    {
                        value: 30,
                        name: 'rose 4'
                    }
                    ]
                },
                ],
                
             
            };

            option && myChart.setOption(option);
        }
    },
    components: {}
}
</script>
<style>
#networkandnodeimportance_new {
    width: 100%;
    height: 100%;
    position: relative;
}

#div_3_1_1 {
    width: 100%;
    height: 40%;
    position: relative;
    float: left;
}

#div_3_1_2 {
    width: 100%;
    height: 60%;
    float: left;
    position: relative;
}
</style>