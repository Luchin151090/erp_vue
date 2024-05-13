<template>
  <v-row justify="start">
    <v-col cols="12" sm="8" md="6" lg="4" align="center">
      <div>
        <canvas ref="chartCanvas"></canvas>
      </div>
    </v-col>
  </v-row>
</template>

<script>
import Chart from 'chart.js/auto'; 
export default {
  name: 'HelloWorld',

  mounted() {
    //const ctx = document.getElementById('chartCanvas').getContext('2d');
    const ctx = this.$refs.chartCanvas.getContext('2d');
    new Chart(ctx, {
      type: 'bar',
      data: {
        labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'],
        datasets: [{
          label: '# of Votes',
          data: [12, 19, 3, 5, 2, 3],
          borderWidth: 1
        }]
      },
      options: {
        scales: {
          y: {
            beginAtZero: true
          }
        }
      }
    });
  }
};
</script>

<style scoped>
/* Estilos opcionales */

</style>
