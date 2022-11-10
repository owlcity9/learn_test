<template>
    <div id="network3d">
        <div id="div_2_2_1_1"></div>
    </div>
</template>
<script>
import ForceGraph3D from '3d-force-graph';
// var my3d_Graph = ForceGraph3D();
export default {
    data() {
        return {
            my3d_Graph:ForceGraph3D()
        }
    },
    mounted() {
        this.draw_force_3d_network();
    },
    methods: {
        draw_force_3d_network() {
            let myData = {
                nodes: [{
                    "id": "id1",
                    "name": "name1",
                    "cluster": "a"
                },
                {
                    "id": "id2",
                    "name": "name2",
                    "cluster": "a"
                },
                // {
                //     "id": "id3",
                //     "name": "name3",
                //     "cluster":"a"
                // },
                // {
                //     "id": "id4",
                //     "name": "name4",
                //     "cluster":"a"
                // },
                {
                    "id": "id5",
                    "name": "name5",
                    "cluster": "a"
                },
                {
                    "id": "id6",
                    "name": "name6",
                    "cluster": "a"
                },
                {
                    "id": "id7",
                    "cluster": "a"
                },
                {
                    "id": "id8",
                    "cluster": "a"
                },
                {
                    "id": "id9",
                    "cluster": "a"
                },
                {
                    "id": "id10",
                    "cluster": "a"
                },
                {
                    "id": "id11",
                    "cluster": "a"
                },
                // {
                //     "id": "id12",
                //     "cluster":"a"
                // },
                // {
                //     "id": "id13",
                //     "cluster":"a"
                // },
                {
                    "id": "id14",
                    "cluster": "a"
                },
                // {
                //     "id": "id15",
                //     "cluster":"a"
                // },
                // {
                //     "id": "id16",
                //     "cluster":"a"
                // },
                //以上为球体a中的节点
                ////////////////////////////////////////////////////////////


                {
                    "id": "ly1",
                    "name": "ly1",
                    "cluster": "b"
                },
                {
                    "id": "ly2",
                    "name": "ly2",
                    "cluster": "b"
                },
                {
                    "id": "ly3",
                    "name": "ly3",
                    "cluster": "b"
                },
                {
                    "id": "ly4",
                    "name": "ly4",
                    "cluster": "b"
                },
                {
                    "id": "ly5",
                    "name": "ly5",
                    "cluster": "b"
                },
                {
                    "id": "ly6",
                    "name": "ly6",
                    "cluster": "b"
                },
                {
                    "id": "ly7",
                    "name": "ly7",
                    "cluster": "b"
                },
                {
                    "id": "ly8",
                    "name": "ly8",
                    "cluster": "b"
                },
                {
                    "id": "ly9",
                    "name": "ly9",
                    "cluster": "b"
                },
                {
                    "id": "ly10",
                    "name": "ly10",
                    "cluster": "b"
                },
                // 以上为球b中的节点
                ////////////////////////////////////////////////////////////////////////
                {
                    "id": "md1",
                    "cluster": "c"
                },
                {
                    "id": "md2",
                    "cluster": "c"
                },
                {
                    "id": "md3",
                    "cluster": "c"
                },
                {
                    "id": "md4",
                    "cluster": "c"
                },
                {
                    "id": "md5",
                    "cluster": "c"
                },
                {
                    "id": "md6",
                    "cluster": "c"
                },
                {
                    "id": "md7",
                    "cluster": "c"
                },
                {
                    "id": "md8",
                    "cluster": "c"
                },
                {
                    "id": "md9",
                    "cluster": "c"
                },
                {
                    "id": "md10",
                    "cluster": "c"
                },
                //以上为球c中的节点
                {
                    "id": "fja1",
                    "cluster": "d"
                },
                {
                    "id": "fja2",
                    "cluster": "d"
                },
                {
                    "id": "fja3",
                    "cluster": "d"
                },
                {
                    "id": "fja4",
                    "cluster": "d"
                },
                {
                    "id": "fja5",
                    "cluster": "d"
                },
                {
                    "id": "fja6",
                    "cluster": "d"
                },
                {
                    "id": "fja7",
                    "cluster": "d"
                },
                // 以上为d类的
                {
                    "id": "fjb1",
                    "cluster": "e"
                },
                {
                    "id": "fjb2",
                    "cluster": "e"
                },
                {
                    "id": "fjb3",
                    "cluster": "e"
                },
                {
                    "id": "fjb4",
                    "cluster": "e"
                },
                //单链
                {
                    "id": "risk_line1",
                    "cluster": "f"
                },
                {
                    "id": "risk_line2",
                    "cluster": "f"
                },
                {
                    "id": "risk_line3",
                    "cluster": "f"
                },
                {
                    "id": "risk_line4",
                    "cluster": "f"
                },
                {
                    "id": "risk_line5",
                    "cluster": "f"
                },


                ],
                links: [{
                    "source": "id1",
                    "target": "id2"
                },
                // {
                //     "source": "id1",
                //     "target": "id3"
                // },
                // {
                //     "source": "id1",
                //     "target": "id4"
                // },
                {
                    "source": "id1",
                    "target": "id5"
                },
                {
                    "source": "id1",
                    "target": "id6"
                },
                {
                    "source": "id1",
                    "target": "id7"
                },
                {
                    "source": "id1",
                    "target": "id8"
                },
                {
                    "source": "id1",
                    "target": "id9"
                },
                {
                    "source": "id9",
                    "target": "id10"
                },
                {
                    "source": "id10",
                    "target": "id11"
                },
                // {
                //     "source": "id10",
                //     "target": "id12"
                // },
                // {
                //     "source": "id12",
                //     "target": "id13"
                // },
                {
                    "source": "id10",
                    "target": "id14"
                },
                // {
                //     "source": "id14",
                //     "target": "id15"
                // },
                // {
                //     "source": "id14",
                //     "target": "id16"
                // },

                ///////////////////////////////////////////////////////////////////////
                {
                    "source": "ly1",
                    "target": "ly2"
                },
                {
                    "source": "ly1",
                    "target": "ly2"
                },
                {
                    "source": "ly1",
                    "target": "ly3"
                },
                {
                    "source": "ly1",
                    "target": "ly4"
                },
                {
                    "source": "ly1",
                    "target": "ly5"
                },
                {
                    "source": "ly1",
                    "target": "ly6"
                },
                {
                    "source": "ly1",
                    "target": "ly7"
                },
                {
                    "source": "ly1",
                    "target": "ly8"
                },
                {
                    "source": "ly1",
                    "target": "ly9"
                },
                {
                    "source": "ly1",
                    "target": "ly10"
                },

                /////////////////////////////////////////////////////////
                {
                    "source": "md1",
                    "target": "md2"
                },
                {
                    "source": "md2",
                    "target": "md3"
                },
                {
                    "source": "md3",
                    "target": "md4"
                },
                {
                    "source": "md4",
                    "target": "md5"
                },
                {
                    "source": "md5",
                    "target": "md6"
                },
                {
                    "source": "md6",
                    "target": "md7"
                },
                {
                    "source": "md7",
                    "target": "md8"
                },
                {
                    "source": "md8",
                    "target": "md9"
                },
                {
                    "source": "md9",
                    "target": "md10"
                },
                //以下事d类的
                {
                    "source": "fja1",
                    "target": "fja2"
                },
                {
                    "source": "fja1",
                    "target": "fja3"
                },
                {
                    "source": "fja1",
                    "target": "fja4"
                },
                {
                    "source": "fja1",
                    "target": "fja5"
                },
                {
                    "source": "fja1",
                    "target": "fja6"
                },
                {
                    "source": "fja1",
                    "target": "fja7"
                },
                //以下为e类的
                {
                    "source": "fjb1",
                    "target": "fjb2"
                },
                {
                    "source": "fjb1",
                    "target": "fjb3"
                },
                {
                    "source": "fjb1",
                    "target": "fjb4"
                },
                //单链
                {
                    "source": "risk_line1",
                    "target": "risk_line2"
                },
                {
                    "source": "risk_line2",
                    "target": "risk_line3"
                },
                {
                    "source": "risk_line3",
                    "target": "risk_line4"
                },
                {
                    "source": "risk_line4",
                    "target": "risk_line5"
                },
                ]
            };
            // 获取目标窗口高宽
            let my_window = document.getElementById("div_2_2_1_1");
            let my_height = my_window.clientHeight - 5; //这里有点影响超出框框，收敛一点
            let my_width = my_window.clientWidth - 15;

            this.my3d_Graph(document.getElementById("div_2_2_1_1"))
                .graphData(myData) //传入数据
                .width(my_width) //传入宽度
                .height(my_height) //传入高度
                .backgroundColor("#FFFFFF") //修改整个的背景颜色
                .showNavInfo(false) //是否显示导航控件页脚信息的获取器/设置器。
                .nodeColor(() => { //节点颜色的设置
                    return "#99CCFF";
                })
                .nodeVal('40')
                // .nodeRelSize(50)
                .nodeOpacity(1) //节点透明度的设置，范围为0到1
                .linkColor(() => {
                    return "#CCFF66";
                })
                .linkWidth(2)
                .linkOpacity(1) //连线透明度，0到1

        }
    },
    computed: {},
    components: {},
    watch: {}
}
</script>
<style>
#network3d {
    width: 100%;
    height: 100%;
}
#div_2_2_1_1{
    width: 100%;
    height: 100%;
}
</style>