<!-- 圓餅圖 -->
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
        dataObject() {
            return Object.keys(this.data).map(name => ({
                name: name,
                value: this.data[name]
            }) );
        },
        option() {
            return {
                title: {
                    text: '餅圖示例',
                    subtext: '銷售數據',
                    left: 'center',
                },
                tooltip: {

                },
                legend: {
                    orient: 'vertical',
                    left: 'left'
                },
                series: [
                    {
                        type: 'pie',
                        name: 'test1',
                        radius: '50%',
                        data: this.dataObject
                    }
                ]
            }
        }
    }
}
</script>