<template>
  <v-app
    :style="{ background: '#282844' }"
  >
    <SideBar />
    <SideBarRight />
    <v-container>

      <v-toolbar color="rgba(0,0,0,0)" flat class="pt-4">
        <v-btn-toggle v-model="toggle_exclusive" tile group color="#A4BEF3">
          <v-btn text>
            <v-icon class="white--text">fas fa-arrow-left</v-icon>
          </v-btn>
          <v-btn text>
            <v-icon class="white--text">fas fa-arrow-right</v-icon>
          </v-btn>
        </v-btn-toggle>
        <v-spacer></v-spacer>
        <v-btn color="#A4BEF3" rounded dark> finish sprint </v-btn>
      </v-toolbar>

      <v-toolbar color="rgba(0,0,0,0)" flat class="pt-6">
        <v-toolbar-title class="white--text">Sprint overview</v-toolbar-title>
        <v-btn color="#A4BEF3" text class="ml-5"> last sprint </v-btn>
      </v-toolbar>

      <v-item-group mandatory class="mt-5">
        <v-container>
          <v-row justify="center" class="space">

            <v-col cols="12" md="3">
              <v-item v-slot="{ toggle }">
                <v-card
                  :color="'#F683A0'"
                  class="d-flex align-center rounded-xl"
                  height="150"
                  @click="toggle"
                >
                  <v-row justify="center" align="center" >
                    <v-col cols="12" sm="5">
                      <v-list-item three-line class="mt-5">
                        <v-list-item-content>
                          <v-list-item-title
                            class="headline"
                            :class="'white--text'"
                          >
                            <strong>52</strong>
                            <v-icon
                              large
                              :color="'white'"
                              class="ml-3"
                              >fas fa-chart-bar</v-icon
                            >
                          </v-list-item-title>
                          <v-list-item-subtitle
                            :class="'white--text'"
                            >Team velocity</v-list-item-subtitle
                          >
                        </v-list-item-content>
                      </v-list-item>
                    </v-col>

                  </v-row>
                </v-card>
              </v-item>
            </v-col>

            <v-col cols="12" md="3">
              <v-item v-slot="{ toggle }">
                <v-card
                  :color="'#A57CED'"
                  class="d-flex align-center rounded-xl"
                  height="150"
                  @click="toggle"
                >
                  <v-row justify="center" align="center" >
                    <v-col cols="12" sm="5">
                      <v-list-item three-line class="mt-5">
                        <v-list-item-content>
                          <v-list-item-title
                            class="headline"
                            :class="'white--text'"
                          >
                            <strong>12</strong>
                            <v-icon
                              large
                              :color="'white'"
                              class="ml-3"
                              >far fa-user</v-icon
                            >
                          </v-list-item-title>
                          <v-list-item-subtitle
                            :class="'white--text'"
                            >Team members</v-list-item-subtitle
                          >
                        </v-list-item-content>
                      </v-list-item>
                    </v-col>

                  </v-row>
                </v-card>
              </v-item>
            </v-col>

            <v-col cols="12" md="3">
              <v-item v-slot="{ toggle }">
                <v-card
                  :color="'#F0C25B'"
                  class="d-flex align-center rounded-xl"
                  height="150"
                  @click="toggle"
                >
                  <v-row justify="center" align="center" >
                    <v-col cols="12" sm="5">
                      <v-list-item three-line class="mt-5">
                        <v-list-item-content>
                          <v-list-item-title
                            class="headline"
                            :class="'white--text'"
                          >
                            <strong>23</strong>
                            <v-icon
                              large
                              :color="'white'"
                              class="ml-3"
                              >fa fa-search</v-icon
                            >
                          </v-list-item-title>
                          <v-list-item-subtitle
                            :class="'white--text'"
                            >Spykes delivered</v-list-item-subtitle
                          >
                        </v-list-item-content>
                      </v-list-item>
                    </v-col>

                  </v-row>
                </v-card>
              </v-item>
            </v-col>

          </v-row>
        </v-container>
      </v-item-group>


      <v-row justify="center" >
        <v-col cols="5">
          <v-card
            :color="'#3D366A'"
            class="d-flex align-center rounded-xl"
            height="550"
            width="550"
            @click="toggle"
          >
            <v-chart class=""  :option="bar" />
          </v-card>
      </v-col>
      </v-row>

    </v-container>
  </v-app>
</template>

<script>
import SideBar from "../components/SideBar";
import SideBarRight from "../components/SideBarRight";

import { use } from "echarts/core";
import { CanvasRenderer } from "echarts/renderers";
import { BarChart } from "echarts/charts";
import {
  TitleComponent,
  TooltipComponent,
  LegendComponent,
} from "echarts/components";
import VChart, { THEME_KEY } from "vue-echarts";
use([
  CanvasRenderer,
  BarChart,
  TitleComponent,
  TooltipComponent,
  LegendComponent,
]);
export default {
  name: "Home",
  data: () => ({
    toggle_exclusive: 1,
    bar : {
      dataset: {
        dimensions: ["Product", "2015", "2016", "2017"],
        source: [
          {
            Product: "Team velocity",
            2015: 1113,
            2016: 715,
            2017: 857
          },
          {
            Product: "Team members",
            2015: 834,
            2016: 635,
            2017: 425,
          },
          {
            Product: "Spikes delivered",
            2015: 956,
            2016: 1064,
            2017: 723
          }
        ],
      },
      xAxis: { type: "category" },
      yAxis: {},
      series: [{ type: "bar" }, { type: "bar" }, { type: "bar" }],
      emphasis: {
        itemStyle: {
          shadowBlur: 10,
          shadowOffsetX: 0,
          shadowColor: "rgba(255, 255, 255, .6)",
        },
      },
    }
  }),
  components: {
    SideBar,
    SideBarRight,
    VChart,
  },
  provide: {
    [THEME_KEY]: "green",
  },
};
</script>

<style>
.space {
  margin-left: -100px;
  margin-right: -100px;
}

</style>
