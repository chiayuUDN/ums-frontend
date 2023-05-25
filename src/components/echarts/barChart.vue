<!-- 長條圖 -->
<template>
    <chart :option="option"></chart>
</template>
<script>
import chart from './chart.vue';

export default {
    props: {
        data: Object,
    },
    components: { chart },
    computed: {
        names() {
            return Object.keys(this.data);
        },
        values() {
            return Object.values(this.data);
        },
        option() {
            return {
                title: {
                    text: '柱狀圖示例',
                    subtext: '銷售數據',
                    left: 'center',
                },
                tooltip: {

                },
                legend: {
                    orient: 'vertical',
                    left: 'left'
                },
                xAxis: {
                    type: 'category',
                    data: this.names
                },
                yAxis: {
                    type: 'value'
                },
                series: [
                    {
                        type: 'bar',
                        name: 'test1',
                        data: this.values
                    }
                ]
            }
        }
    }
}
</script>