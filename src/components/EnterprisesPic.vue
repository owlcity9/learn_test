<template>
    <div id="enterprsespic">
        <div id="div_1_1_1"></div>
        <div id="div_1_1_2"></div>
        <div id="div_1_1_3"></div>
        <img id="e_pic" src="/img/e_pic.png" alt="">
    </div>
</template>
<script>
import * as echarts from 'echarts';
import { WordCloud } from '@antv/g2plot';

export default {
    data() {
        return {

        }
    },
    mounted() {
        //待所有dom元素加载后执行
        this.draw_enterprise_pic_wai();
        this.draw_enterprise_pic_middle();
        this.draw_word_clound()
    },
    computed: {

    },
    methods: {
        draw_enterprise_pic_wai() {
            var chartDom = document.getElementById('div_1_1_1');
            var myChart = echarts.init(chartDom);
            var option;
            option = {
                // title: {
                //     text: 'Basic Radar Chart'
                // },
                radar: {
                    // shape: 'circle',
                    radius: "98%",
                    shape: "circle",
                    indicator: [{
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    },
                    {
                        max: 100
                    }
                    ],
                    splitArea: {
                        show: false
                    },
                    axisLine: {
                        show: false
                    },
                    axisTick: {
                        show: false
                    },
                    splitLine: {
                        show: false
                    }
                },
                series: [{
                    name: 'Budget vs spending',
                    type: 'radar',
                    data: [{
                        //外围的值保持再75-94最好
                        value: [76, 76, 87, 89, 99, 78, 76, 84, 87, 89, 76, 94, 87, 89, 96, 88, 86, 94, 87, 89, 88, 86, 98, 79, 96, 88, 86, 94, 87, 89, 88, 86, 98, 79, 89, 87]
                    }],
                    lineStyle: {
                        color: '#99CCFF'
                    },
                    itemStyle: {
                        color: '#99CCFF'
                    }
                }]
            };

            option && myChart.setOption(option);
        },
        draw_enterprise_pic_middle() {
            var myChart = echarts.init(document.getElementById('div_1_1_2'));
            // prettier-ignore
            const my_angles = [
                '12a', '1a', '2a', '3a', '4a', '5a', '6a',
                '7a', '8a', '9a', '10a', '11a',
                '12p', '1p', '2p', '3p', '4p', '5p',
                '6p', '7p', '8p', '9p', '10p', '11p'
            ];
            // prettier-ignore
            const my_radius = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24];
            // prettier-ignore


            let my_data = [];
            for (let ii = 0; ii < 24; ii++) {
                let temp_flag = Math.random() * 10;
                let tem_color = '#66CCCC';
                if (temp_flag <= 5) { tem_color = '#FF99CC' }
                let temp_point = {
                    value: [temp_flag / 2 + 14, 0.5, 6],
                    itemStyle: {
                        color: tem_color
                    },
                    symbolSize: temp_flag
                }
                temp_point['value'][1] = ii;
                my_data.push(temp_point);

            }
            // data.forEach(function(value,index,array){
            //   array[index][0]= Math.random()*5+14;
            // })
            let option = {
                // title: {
                //     text: 'Punch Card of Github'
                // },
                // legend: {
                //     data: ['Punch Card'],
                //     left: 'right'
                // },
                polar: {},
                // tooltip: {
                //   formatter: function (params) {
                //     return (
                //       params.value[2] +
                //       ' commits in ' +
                //       hours[params.value[1]] +
                //       ' of ' +
                //       days[params.value[0]]
                //     );
                //   }
                // },
                angleAxis: {
                    type: 'value',
                    data: my_angles,
                    boundaryGap: false,
                    splitLine: {
                        show: false
                    },
                    axisLine: {
                        show: false
                    },
                    axisTick: {
                        show: false
                    },
                    axisLabel: {
                        show: false
                    }
                },
                radiusAxis: {
                    type: 'category',
                    // type:'value',
                    data: my_radius,
                    axisLine: {
                        show: false
                    },
                    axisLabel: {
                        rotate: 45,
                        show: false
                    },
                    axisTick: {
                        show: false
                    }
                },
                series: [{
                    name: 'Punch Card',
                    type: 'scatter',
                    coordinateSystem: 'polar',
                    // symbolSize: function (val) {
                    //   return val[2] * 2;
                    // },
                    data: my_data,
                    animationDelay: function (idx) {
                        return idx * 5;
                    }
                }]
            };


            myChart.setOption(option);
        },
        draw_word_clound() {
            let my_div = document.getElementById("div_1_1_3");
            let my_width = my_div.clientWidth;
            let my_height = my_div.clientHeight;
            fetch('https://gw.alipayobjects.com/os/antfincdn/jPKbal7r9r/mock.json')
                .then((res) => res.json())
                .then((data) => {
                    const wordCloud = new WordCloud('div_1_1_3', {
                        data,
                        // width:0.3*my_width,
                        // height:0.2*my_height,
                        wordField: 'x',
                        weightField: 'value',
                        color: '#99CCFF',
                        wordStyle: {
                            fontFamily: 'Verdana',
                            fontSize: [10, 20],
                        },
                        imageMask: 'data:image/png;base64,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',
                        // 设置交互类型
                        interactions: [{
                            type: 'element-active'
                        }],
                        state: {
                            active: {
                                // 这里可以设置 active 时的样式
                                style: {
                                    lineWidth: 3,
                                },
                            },
                        },
                    });

                    wordCloud.render();
                });
        }
    },
    watch: {},
    components: {
    }
}
</script>


<style>
#enterprsespic {
    width: 100%;
    height: 100%;
}

#e_pic {
    width: 99%;
    position: absolute;
    z-index: -99;
    top: 1%;
}

#div_1_1_1 {
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
}

#div_1_1_2 {
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
}

#div_1_1_3 {
    width: 33%;
    height: 25%;
    position: absolute;
    top: 36%;
    left: 33%;
}
</style>