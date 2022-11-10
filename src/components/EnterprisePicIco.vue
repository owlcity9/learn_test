<template>
    <div id="enterprisepicico">
        <!-- 用public下的文件，直接下面这样，虽然提示不一样 -->
        <img id="line_zhexian" src="/img/line_zhexian.png" alt="">
        <img id="node_qiye" src="/img/node_qiye.png" alt="">
        <img id="word_clound" src="/img/word_clound.png" alt="">
        <h4 id="enterprisepicico_profit_label">profit</h4>
        <h4 id="enterprisepicico_enterprise_label">enterprises</h4>
        <h4 id="enterprisepicico_scope_label">scope</h4>
    </div>
</template>

<script>
export default {
    data() {
        return {
           
        }
    },
    mounted() {     //待所有dom元素加载后执行
    },
    computed: {

    },
    methods: {
    },
    watch: {},
    components: {
    }
}
</script>
<style>
#enterprisepicico {
    /* background-color: aquamarine; */
    width: 100%;
    height: 100%;
}
#line_zhexian {
    position: absolute;
    height: 40%;
    left: 15%;
    top: 20%
}

#node_qiye {
    position: absolute;
    height: 30%;
    left: 40%;
    top: 25%
}

#word_clound {
    position: absolute;
    height: 45%;
    left: 70%;
    top: 23%
}
#enterprisepicico_profit_label{
    position:absolute;
    left: 17%;
    top: 55%;
}
#enterprisepicico_enterprise_label{
    position:absolute;
    left: 41%;
    top: 55%;
}
#enterprisepicico_scope_label{
    position:absolute;
    left: 72%;
    top: 55%;
}

</style>