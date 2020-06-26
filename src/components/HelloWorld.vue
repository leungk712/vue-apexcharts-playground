<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="6">
        <v-card>
          <v-card-title>
            Basic Bar Graph
          </v-card-title>
          <v-card-text>
            <apexchart
              width="100%"
              :options="barOptions"
              :series="barOptions.series"
            />
          </v-card-text>
        </v-card>
      </v-col>

      <v-col cols="6">
        <v-card>
          <v-card-title>
            Basic Line Graph
          </v-card-title>
          <v-card-text>
            <apexchart
              width="100%"
              :options="lineOptions"
              :series="lineOptions.series"
            />
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>

    <v-row>
      <v-col cols="6">
        <v-card>
          <v-card-title>
            Basic Donut
          </v-card-title>
          <v-card-text>
            <apexchart
              width="100%"
              :options="donutOptions"
              :series="donutOptions.series"
            />
          </v-card-text>
        </v-card>
      </v-col>

      <v-col cols="6">
        <v-card>
          <v-card-title>
            Basic Heatmap
          </v-card-title>
          <v-card-text>
            <apexchart
              width="100%"
              :options="heatOptions"
              :series="heatOptions.series"
            />
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "HelloWorld",

  data() {
    return {
      barOptions: {
        series: [
          {
            name: "yearly revenue",
            data: [
              300000,
              450000,
              525000,
              815000,
              938414,
              1265783,
              1567892,
              1777123,
              1923400
            ]
          }
        ],
        chart: {
          id: "revenue-yearly",
          type: "bar"
        },
        plotOptions: {
          bar: {
            horizontal: true
          }
        },
        xaxis: {
          categories: [
            2016,
            2017,
            2018,
            2019,
            2020,
            2021,
            2022,
            2023,
            2024,
            2025
          ]
        }
      },

      lineOptions: {
        series: [
          {
            name: "yearly revenue",
            data: [
              300000,
              450000,
              525000,
              815000,
              938414,
              1265783,
              1567892,
              1777123,
              1923400
            ]
          }
        ],
        chart: {
          id: "revenue-yearly",
          type: "line"
        },
        xaxis: {
          categories: [
            2016,
            2017,
            2018,
            2019,
            2020,
            2021,
            2022,
            2023,
            2024,
            2025
          ]
        }
      },

      donutOptions: {
        series: [33, 17, 48, 63, 88, 71],
        chart: {
          type: "donut"
        },
        labels: [
          "Groceries",
          "Supplies",
          "Clothes",
          "Bills",
          "Misc 1",
          "Misc 2"
        ],
        responsive: [
          {
            breakpoint: 480,
            options: {
              chart: {
                width: 200
              },
              legend: {
                position: "bottom"
              }
            }
          }
        ]
      },

      heatOptions: {
        series: [
          {
            name: "Series 1",
            data: [
              {
                x: "W1",
                y: 22
              },
              {
                x: "W2",
                y: 29
              },
              {
                x: "W3",
                y: 13
              },
              {
                x: "W4",
                y: 32
              }
            ]
          },
          {
            name: "Series 2",
            data: [
              {
                x: "W1",
                y: 50
              },
              {
                x: "W2",
                y: 88
              },
              {
                x: "W3",
                y: 1
              },
              {
                x: "W4",
                y: 9
              }
            ]
          },
          {
            name: "Series 3",
            data: [
              {
                x: "W1",
                y: 45
              },
              {
                x: "W2",
                y: 53
              },
              {
                x: "W3",
                y: 78
              },
              {
                x: "W4",
                y: 88
              }
            ]
          }
        ],
        chart: {
          height: 350,
          type: "heatmap"
        },
        dataLabels: {
          enabled: false
        },
        plotOptions: {
          heatmap: {
            colorScale: {
              ranges: [
                {
                  from: 0,
                  to: 25,
                  color: "#CACFD2",
                  name: "low"
                },
                {
                  from: 26,
                  to: 50,
                  color: "#C0392B",
                  name: "medium"
                },
                {
                  from: 51,
                  to: 75,
                  color: "#F5B041",
                  name: "medium-high"
                },
                {
                  from: 76,
                  to: 100,
                  color: "#52BE80",
                  name: "high"
                }
              ]
            }
          }
        },
        title: {
          text: "HeatMap Chart (Single color)"
        }
      }
    };
  }
};
</script>
