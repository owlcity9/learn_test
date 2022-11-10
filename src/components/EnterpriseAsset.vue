<template>
    <div id="enterpriseasset">
        <div id="div_3_2_1"></div>
        <div id="div_3_2_2">
            <img id="asset_pic" src='/img/资产统计.png' alt="">
            <h4 id="asset_title">Assets</h4>
            <img id="asset_jianbian" src="/img/资产渐变.png" alt="">
            <h4 id="asset_jieshi">Asset Gradient Size</h4>
        </div>
    </div>
</template>
<script>
import { CirclePacking } from '@antv/g2plot';

export default {
    data() {
        return {

        }
    },
    mounted() {
        this.draw_assets()
    },
    methods: {
        draw_assets() {
            fetch('/json/basic-packing.json')
                .then((data) => data.json())
                .then((data) => {
                    const plot = new CirclePacking('div_3_2_1', {
                        autoFit: true,
                        padding: 0,
                        data,
                        sizeField: 'r',
                        // color: 'rgb(184,244,255)-rgb(95,217,205)-rgb(255,181,161)',
                        color: 'rgb(221,238,255)-rgb(60,179,179)',
                        // color:'rgb(102,204,204)-rgb(238,247,255)',
                        // 自定义 label 样式
                        label: {
                            formatter: ({
                                name
                            }) => {
                                return name !== 'root' ? name : '';
                            },
                            // 偏移
                            offsetY: 8,
                            style: {
                                fontSize: 12,
                                textAlign: 'center',
                                fill: 'rgba(0,0,0,0.65)',
                            },
                        },
                        legend: false,
                    });

                    plot.render();
                });
        }
    },
    computed: {},
    watch: {},
    components: {}
}
</script>
<style>
#enterpriseasset {
    width: 100%;
    height: 100%;
}

#div_3_2_1 {
    width: 65%;
    height: 100%;
    float: left;
}

#div_3_2_2 {
    /* background-color: aquamarine; */
    width: 35%;
    height: 100%;
    float: left;
    position: relative;
}
#asset_pic{
    width: 35%;
    position: absolute;
    top: 10%;
}
#asset_title{
    top: 8%;
    left: 33%;
    position: absolute;
}
#asset_jianbian{
    width: 65%;
    top: 47%;
    position:absolute;
}
#asset_jieshi{
    position: absolute;
    top: 60%;

}
</style>