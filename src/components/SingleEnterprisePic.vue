<template>
    <div id="singleenterprisepic">
        <div id="div_1_4_0">
            <div id="div_1_4_1"></div>
            <div id="div_1_4_2"></div>
            <div id="div_1_4_3"></div>
        </div>
        <div id="div_1_4_left">
            <img id="line_zhexian2" src='/img/line_zhexian.png' alt="">
            <img id="circle_huaxiang" src="/img/circle_huaxiang.png" alt="">
            <img id="abnormal" src='/img/异常.png' alt="">
            <img id="files" src="/img/证书.png" alt="">
            <img id="touzi" src="/img/投资.png" alt="">
            <img id="scope" src="/img/scope.png" alt="">
            <h4 id="label_line_zhexian2">Turnover</h4>
            <h4 id="label_circle_huaxiang">Debt</h4>
            <h4 id="label_abnormal">Unfaithfulness</h4>
            <h4 id="label_files">Certificates</h4>
            <h4 id="label_touzi">Abnormal</h4>
            <h4 id="label_scope">Type</h4>
        </div>
    </div>
</template>

<script>
import * as echarts from 'echarts';
// const pathSymbols = {
//     // 自定义图标
//     yichang: 'image://img/异常.png',
//     diya_touzi: 'image://img/投资.png',
//     xuke: 'image://img/证书.png',
//     jianzhu: 'image://img/建筑.png'
// };
export default {
    data() {
        return {
            pathSymbols: {
                // 自定义图标
                //注意格式
                yichang: 'image://img/异常.png',
                diya_touzi: 'image://img/投资.png',
                xuke: 'image://img/证书.png',
                jianzhu: 'image://img/建筑.png'
            }
        }
    },
    mounted() {     //待所有dom元素加载后执行
        this.draw_single_enterprise_middle_pic();
        this.draw_yichang();
        this.draw_jingying();
    },
    computed: {

    },
    methods: {
        draw_single_enterprise_middle_pic() {
            var myChart = echarts.init(document.getElementById('div_1_4_1'));
            // prettier-ignore
            const my_angles = [
                '12a', '1a', '2a', '3a', '4a', '5a', '6a',
                '7a', '8a', '9a', '10a', '11a',
                '12p', '1p', '2p', '3p', '4p', '5p',
                '6p', '7p', '8p', '9p', '10p', '11p'
            ];
            // prettier-ignore
            const my_radius = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24];
            let my_test_data = [];
            for (let ii = 0; ii < 24; ii++) {
                let my_linshi_flag = Math.random() * 10;

                let linshi_yichang = {
                    value: [17, ii, 10],
                    symbol: this.pathSymbols.yichang
                };
                let linshi_diyatouzi = {
                    value: [8, ii, 9],
                    symbol: this.pathSymbols.diya_touzi
                };
                let linshi_xuke = {
                    value: [12.5, ii, 10],
                    symbol: this.pathSymbols.xuke
                }
                if (my_linshi_flag >= 8) {
                    my_test_data.push(linshi_yichang);
                }
                else if (my_linshi_flag >= 5) {
                    my_test_data.push(linshi_diyatouzi);
                }
                else {
                    my_test_data.push(linshi_xuke);
                }

            }

            my_test_data.push({
                value: [0.1, 0, 20],//这里在vue框架中，需要将位置改一下，才能显示，0.1
                symbol: this.pathSymbols.jianzhu,
                symbolSize: 45
            });
            // prettier-ignore
            let option = {
                polar: {}, //这个不能删
                angleAxis: {
                    type: 'category',
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
                    // type: 'category',
                    max: 25,
                    type: 'value',
                    data: my_radius,
                    axisLine: {
                        show: false
                    },
                    axisLabel: {
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
                    symbolSize: function (val) {
                        return val[2] * 2;
                    },
                    data: my_test_data,
                    animationDelay: function (idx) {
                        return idx * 5;
                    }
                }]
            };
            myChart.setOption(option);
        },
        draw_yichang() {
            var chartDom = document.getElementById('div_1_4_2');
            var myChart = echarts.init(chartDom);
            var option;

            option = {
                color: ['#FF99CC', '#66CCCC'],
                // tooltip: {
                //   trigger: 'item'
                // },
                // legend: {
                //   top: '5%',
                //   left: 'center'
                // },
                series: [{
                    name: 'Access From',
                    type: 'pie',
                    radius: ['65%', '75%'],
                    avoidLabelOverlap: false,
                    label: {
                        show: false,
                        position: 'center'
                    },
                    emphasis: {
                        label: {
                            show: true,
                            fontSize: '40',
                            fontWeight: 'bold'
                        }
                    },
                    labelLine: {
                        show: false
                    },
                    data: [{
                        value: 70
                    },
                    {
                        value: 30
                    }
                    ]
                }]
            };

            option && myChart.setOption(option);
        },
        draw_jingying() {
            var chartDom = document.getElementById('div_1_4_3');
            var myChart = echarts.init(chartDom);
            var option;

            let linshi_data = [];
            for (let ii = 0; ii < 24; ii++) {
                linshi_data.push(Math.random() * 4);
            };

            option = {
                color: ['#99CCFF'],
                polar: {
                    radius: ['80%', '95%']
                },
                radiusAxis: {
                    max: 4,
                    axisTick: {
                        show: false
                    },
                    splitLine: {
                        show: false
                    },
                    axisLine: {
                        show: false
                    },
                    axisLabel: {
                        show: false
                    }

                },
                angleAxis: {
                    type: 'category',
                    data: ['1', '2', '3', '4', '5', '6', '7', '8', '9', '10', '11', '12', '13', '14', '15', '16', '17', '18', '19', '20', '21', '22', '23', '24'],
                    // startAngle: 75
                    axisTick: {
                        show: false
                    },
                    splitLine: {
                        show: false
                    },
                    axisLine: {
                        show: false
                    },
                    axisLabel: {
                        show: false
                    }
                },
                tooltip: {},
                series: {
                    type: 'bar',
                    data: linshi_data,
                    coordinateSystem: 'polar'
                },
                backgroundColor: '#fff',
                animation: false
            };

            option && myChart.setOption(option);
        }
    },
    watch: {},
    components: {
    }
}






</script>
<style>
#singleenterprisepic {
    width: 100%;
    height: 100%;
    /* background-color: aqua; */
}

#div_1_4_0 {
    height: 100%;
    width: 65%;
    position: relative;
    float: left;
}

#div_1_4_1 {
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
}

#div_1_4_2 {
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
}

#div_1_4_3 {
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
    z-index: -99;
}

#div_1_4_left {
    width: 35%;
    height: 100%;
    float: left;
    /* background-color: sandybrown; */
    position: relative;
}
#line_zhexian2{
    width: 25%;
    top: 7%;
    left: 0%;
    position: absolute;
}
#circle_huaxiang{
    width: 25%;
    top: 22%;
    left: 0%;
    position: absolute;
}
#abnormal{
    width: 25%;
    top: 37%;
    left: 0%;
    position: absolute;
}
#files{
    width: 25%;
    top: 51%;
    left: 0%;
    position: absolute;
}
#touzi{
    width: 25%;
    top: 67%;
    left: 0%;
    position: absolute;
}
#scope{
    width: 25%;
    top: 82%;
    left: 0%;
    position: absolute;
}
#label_line_zhexian2{
    position:absolute;
    left: 29%;
    top: 7%;
}
#label_circle_huaxiang{
    position:absolute;
    left: 29%;
    top: 21%;
}
#label_abnormal{
    position:absolute;
    left: 29%;
    top: 35%;
}
#label_files{
    position:absolute;
    left: 29%;
    top: 49%;
}
#label_touzi{
    position:absolute;
    left: 29%;
    top: 64%;
}
#label_scope{
    position:absolute;
    left: 29%;
    top: 79%;
}
</style>