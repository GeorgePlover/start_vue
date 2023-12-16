<template>
    <div>
      <h1>Records of Publications</h1>
      <canvas ref="myChartCanvas"></canvas>
    </div>
  </template>
  
  <script>
  import Chart from 'chart.js/auto';
  
  export default {
    mounted() {
      const yearsData = {
        labels: ['2019', '2020', '2021'],
        datasets: [
          {
            label: '作品数量',
            data: [20, 35, 50],
            backgroundColor: [
              'rgba(255, 99, 132, 0.2)',
              'rgba(54, 162, 235, 0.2)',
              'rgba(255, 206, 86, 0.2)',
            ],
            borderColor: [
              'rgba(255, 99, 132, 1)',
              'rgba(54, 162, 235, 1)',
              'rgba(255, 206, 86, 1)',
            ],
            borderWidth: 1,
          },
          {
            label: '又一个作品数量',
            data: [20, 35, 50],
            backgroundColor: [
              'rgba(255, 99, 132, 0.2)',
              'rgba(54, 162, 235, 0.2)',
              'rgba(255, 206, 86, 0.2)',
            ],
            borderColor: [
              'rgba(255, 99, 132, 1)',
              'rgba(54, 162, 235, 1)',
              'rgba(255, 206, 86, 1)',
            ],
            borderWidth: 1,
          },
        ],
      };
  
      const ctx = this.$refs.myChartCanvas.getContext('2d');
      new Chart(ctx, {
        type: 'bar',
        data: yearsData,
        options: {
          scales: {
            y: {
              beginAtZero: true,
            },
          },
        },
      });
    },
  };
  </script>
  
  <style>
  canvas {
    width: 400px; /* 固定宽度 */
    height: 400px; /* 固定高度 */
  }
  </style>
  