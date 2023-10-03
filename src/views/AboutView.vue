<template>
  <div>
    <canvas ref="revenueChartCanvas" width="400" height="200"></canvas>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue';
import Chart from 'chart.js/auto';

export default {
  setup() {
    const chartRef = ref(null);

    onMounted(() => {
      const canvas = chartRef.value;
      setTimeout(() => {
        if (!canvas) {
          console.log('ljlkdsjfldsf')
        const ctx = canvas.getContext('2d');
        const revenueChart = new Chart(ctx, {
          type: 'line',
          data: {
            labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May'],
            datasets: [
              {
                label: 'Revenue 2021',
                data: [1000, 1200, 1300, 1100, 1400],
                borderColor: 'rgba(75, 192, 192, 1)',
                borderWidth: 2,
                fill: false,
              },
              // Add more datasets for comparisons
            ],
          },
          options: {
            responsive: true,
            plugins: {
              legend: {
                display: true,
                position: 'top',
              },
            },
          },
        });
      }
      }, 3000)
      
    });

    return {
      chartRef,
    };
  },
};
</script>
