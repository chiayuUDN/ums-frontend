<!-- 折線圖 -->
<template>
    <div ref="lineChart" style="width: 500px; height: 400px;"></div>
</template>
<script>
import * as echarts from 'echarts';

export default {
    methods: {
        lineChart() {
            const chart = echarts.init(this.$refs.lineChart);
            chart.setOption({
                xAxis: {
                    type: "category",
                    data: ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"]
                },
                yAxis: {
                    type: "value"
                },
                series: [
                    {
                        data: [120, 200, 150, 80, 70, 110, 130],
                        type: "line",
                        showBackground: true,
                        backgroundStyle: {
                            color: "rgba(180, 180, 180, 0.2)"
                        }
                    }
                ]
            });
        }
    },
    mounted() {
        this.lineChart();
    },
    created() {
        // this.lineChart();
    }
}
</script>