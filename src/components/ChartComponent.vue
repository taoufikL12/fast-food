<template>
    <div>
        <h2>ChartJs</h2>
        <div class="card">
            <canvas id="myChart" class="h-30rem"></canvas>
        </div>
    </div>
</template>

<script>
import { Chart } from 'chart.js/auto';

export default {
    data() {
        return {
            chartData: null,
            chartOptions: null
        };
    },
    mounted() {
        const ctx = this.$el.querySelector('#myChart');
        this.chartData = this.setChartData();
        this.chartOptions = this.setChartOptions();

        new Chart(ctx, {
            type: 'bar',
            data: this.chartData,
            options: this.chartOptions
        });
    },
    methods: {
        setChartData() {
            const documentStyle = getComputedStyle(document.documentElement);

            return {
                labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
                datasets: [
                    {
                        label: 'My First dataset',
                        backgroundColor: documentStyle.getPropertyValue('--blue-500'),
                        borderColor: documentStyle.getPropertyValue('--blue-500'),
                        data: [65, 59, 80, 81, 56, 55, 40]
                    },
                    {
                        label: 'My Second dataset',
                        backgroundColor: documentStyle.getPropertyValue('--pink-500'),
                        borderColor: documentStyle.getPropertyValue('--pink-500'),
                        data: [28, 48, 40, 19, 86, 27, 90]
                    }
                ]
            };
        },
        setChartOptions() {
            const documentStyle = getComputedStyle(document.documentElement);
            const textColor = documentStyle.getPropertyValue('--text-color');
            const textColorSecondary = documentStyle.getPropertyValue('--text-color-secondary');
            const surfaceBorder = documentStyle.getPropertyValue('--surface-border');

            return {
                maintainAspectRatio: false,
                aspectRatio: 0.8,
                plugins: {
                    legend: {
                        labels: {
                            fontColor: textColor
                        }
                    }
                },
                scales: {
                    x: {
                        ticks: {
                            color: textColorSecondary,
                            font: {
                                weight: 500
                            }
                        },
                        grid: {
                            display: false,
                            drawBorder: false
                        }
                    },
                    y: {
                        ticks: {
                            color: textColorSecondary
                        },
                        grid: {
                            color: surfaceBorder,
                            drawBorder: false
                        }
                    }
                }
            };
        }
    }
}
</script>

<style scoped>
.h-30rem {
    height: 60rem;
}
</style>

