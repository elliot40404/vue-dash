<template>
  <div class="bg">
    <h1>DASHBOARD</h1>
    <div class="grid">
      <div class="box box_one">
        <apexchart
          width="400"
          type="donut"
          :options="graph1.options"
          :series="graph1.series"
        ></apexchart>
        <apexchart
          width="400"
          type="radialBar"
          :options="graph1.options"
          :series="graph1.series"
        ></apexchart>
      </div>
      <div class="box box_two">
        <apexchart
          width="800"
          height="350"
          type="bar"
          :options="graph2.options"
          :series="graph2.series"
        ></apexchart>
      </div>
      <div class="box box_three">
        <apexchart
          width="1700"
          height="350"
          type="line"
          :options="graph2.options"
          :series="graph3.series"
        ></apexchart>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Main",
  data() {
    return {
      graph1: {
        options: {},
        series: [44, 55, 41, 17, 15],
      },
      graph2: {
        options: {},
        series: [
          {
            data: [10, 20, 30, 40, 50, 60],
          },
        ],
      },
      graph3: {
        series: [
          {
            data: [11, 52, 30, 90, 29, 69],
          },
        ],
      }
    };
  },
  methods: {
    add() {
      this.graph1.series[Math.floor((Math.random() * 10) / 2)] = Math.floor(
        (Math.random() * 100) / 2
      );
    },
    add2() {
      this.graph2.series[0].data[
        Math.floor((Math.random() * 10) / 2)
      ] = Math.floor((Math.random() * 100) / 2);
    },
  },
};
</script>

<style scoped lang="scss">
.bg {
  background: #171721;
  height: 100vh;
  width: calc(100vw - 100px);
  display: flex;
  flex-direction: column;
}
h1 {
  color: cyan;
  padding: 1em;
}
.grid {
  height: 85%;
  width: 95%;
  align-self: center;
  justify-self: center;
  display: grid;
  padding: 10px;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 1fr 1fr;
  gap: 20px;
}
.box {
  border-radius: 10px;
  background: rgba(0, 0, 0, 0.192);
  padding: 10px;
}
.box_one {
  display: flex;
  justify-content: center;
  align-items: center;
}
.box_two {
  padding: 10px;
}
.box_three {
  grid-column: 1 / -1;
}
</style>
