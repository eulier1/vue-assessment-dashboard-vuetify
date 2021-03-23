<template>
<div class="px-16">
  <!-- Heading -->
  <v-row align="center" class="pt-12">
    <v-col cols="12" sm="12" md="12" class="" >
      <div>
        <h1 >Welcome to Gemnote, Ashley!</h1>
       </div>
    </v-col>
  </v-row>
  <!-- Metrics row -->
  <v-row align="center" class="mt-8" >
    <v-col class=" fill-column" cols="12" sm="12" md="12" lg="6">
      <v-card elevation="0">
        <v-row class="ma-1 custom-card-outline" style="justify-content: center" >
          <v-col cols="12" sm="12" md="5" lg="5"
          :class="{
            'flex jc-center flex-wrap text-center' : $vuetify.breakpoint.mdAndDown
          }" >
            <v-card-title class="custom-subtitle pt-2 text-break"
            :class="{
              'pl-1' : $vuetify.breakpoint.mdAndDown,
              'custom-card-divider': $vuetify.breakpoint.lgAndUp
            }"
            style="letter-spacing: -1px;" >
            Total number of orders this month
            </v-card-title>
            <v-card-text class="pr-0"
            :class="{
              'pl-1' : $vuetify.breakpoint.mdAndDown,
              'custom-card-divider': $vuetify.breakpoint.lgAndUp
              }">
              <h1 :class="{
                'text-lg-h4': $vuetify.breakpoint.mdAndDown,
                'display-2 font-weight-regular': $vuetify.breakpoint.lgAndUp,
                'text-lg-h2': $vuetify.breakpoint.xl-only,
                'display-1 mb-2': $vuetify.breakpoint.smAndDown}"
                v-text="data.totalOrders"
              ></h1>
            </v-card-text>
          </v-col>
          <v-col cols="12" md="7" lg="7" align-self="center" class="pl-0"
          :class="{
            'flex jc-center flex-wrap text-center' : $vuetify.breakpoint.mdAndDown
          }"
          >
            <v-card-title 
            v-if="$vuetify.breakpoint.mdAndDown"
            class="h6 custom-subtitle pt-2 pr-0" >
              Average number of shipments/month 
            </v-card-title>
            <v-card-title 
            v-else
            class="h6 custom-subtitle pt-2 pr-0" >
              Average number of <br> shipments/month 
            </v-card-title>
            <v-card-text class="custom-subtitle pr-0">
              <v-row v-if="$vuetify.breakpoint.mdAndUp" align="center">
                <v-col cols="12" sm="6" lg="6" >
                  <h1 :class="{
                'text-lg-h4': $vuetify.breakpoint.mdAndDown,
                'display-2 font-weight-regular': $vuetify.breakpoint.lgAndUp,
                'text-lg-h2': $vuetify.breakpoint.xl-only,
                'display-1 mb-2': $vuetify.breakpoint.smAndDown}"
                  v-text="data.averageShipmentMonthly">
                  </h1>
                </v-col>
                <v-col cols="12" sm="5" lg="5" 
                  :class="{
                    'pl-4': $vuetify.breakpoint.mdAndDown,
                    'pl-0 pr-0' : $vuetify.breakpoint.mdAndUp
                  }"
                >
                  <v-btn
                    outlined
                    class="custom-button-outline pt-6 pb-6 pr-3 pl-3 text-transform__initial letter-spacing__normal"
                  >
                    View orders
                  </v-btn>                  
                </v-col>
              </v-row>
              <v-row v-else>
                <v-col cols="12" sm="12" class="flex gap-20" 
                :class="{'jc-center': $vuetify.breakpoint.mdAndDown }" >
                  <h1 :class="{
                  'text-lg-h4': $vuetify.breakpoint.mdAndDown,
                  'display-2 font-weight-regular': $vuetify.breakpoint.lgAndUp,
                  'text-lg-h2': $vuetify.breakpoint.xl-only,
                  'display-1': $vuetify.breakpoint.smAndDown}"
                    v-text="data.averageShipmentMonthly">
                  </h1>
                  <v-btn
                    outlined
                    class="custom-button-outline pt-6 pb-6 pr-3 pl-3 text-transform__initial letter-spacing__normal"
                  >
                    View orders
                  </v-btn>
                </v-col>
              </v-row>
            </v-card-text>
          </v-col>
        </v-row>
      </v-card>
    </v-col>

    <v-col class="fill-column" cols="12" sm="12" md="12" lg="6">
      <v-card elevation="0">
        <v-row class="ma-1 custom-card-outline" align="center">
          <v-col cols="12" sm="4" md="4" class="pa-5 flex jc-center">
            <div class="custom-image-placeholder"></div>
          </v-col>
          <v-col cols="12" sm="8" md="8" class="pl-0" >
            <v-card-title 
            class="h6 custom-subtitle pt-2" 
            :class="{
                'pr-0 pl-0': $vuetify.breakpoint.mdAndUp
                }">
              Current inventory
              <div class="visibility-hidden" ><br>;</div>
            </v-card-title>
            <v-card-text class="custom-subtitle flex gap-20 flex-wrap start ai-center "
              :class="{
                'pr-0 pl-0': $vuetify.breakpoint.mdAndUp
                }"
                >
                <h1  :class="{
                'text-lg-h4': $vuetify.breakpoint.mdAndDown,
                'display-2 font-weight-regular': $vuetify.breakpoint.lgAndUp,
                'text-lg-h2': $vuetify.breakpoint.xl-only,
                'display-1 mb-2': $vuetify.breakpoint.smAndDown}" 
                >400</h1>
              <v-btn
                outlined
                class="custom-button-outline pt-6 pb-6 text-transform__initial letter-spacing__normal"
              >
                Manage inventory
              </v-btn>
            </v-card-text>
          </v-col>
        </v-row>
      </v-card>
    </v-col>
  </v-row>
  <!-- Trending gifts row -->
  <v-row class="mt-8" align="center">
    <v-col class="fill-column" cols="12" sm="12" md="12" align="center" >
      <v-card elevation="0">
        <v-row class="ma-1 custom-card-outline">
          <v-col cols="12" sm="12" md="12" >
            <v-card-title class="h6 custom-subtitle pt-2 text-break" >
              Trending gifts in your store
            </v-card-title>
          </v-col>
          <v-col cols="12" sm="12" md="12" class="pa-4 pb-8">
            <v-row
            class=""
            no-gutters
            align="center"
            >
            <v-col
              v-for="n in [0,1,2,3,4]"
              :key="n"
              align="center"
            >
              <v-img
                contain
                v-if="n < 4"
                :lazy-src="data.trendingGiftStore[n].img"
                max-width="160"
                :src="data.trendingGiftStore[n].img"
              ></v-img>
              <v-btn
                v-if="n === 4"
                outlined
                class="custom-button-outline pt-6 pb-6 px-10 text-transform__initial letter-spacing__normal"
              >
                Send a gift
              </v-btn>
            </v-col>
        </v-row>
          </v-col>
        </v-row>
      </v-card>
    </v-col>
  </v-row>
  <!-- Graph row -->
    <v-row class="mt-8" align="center">
    <v-col class="fill-column" cols="12" sm="12" md="12" align="center" >
      <v-card elevation="0">
        <v-row class="ma-1 custom-card-outline">
          <v-col cols="12">
            <v-row >
              <v-col  >
                <v-card-title class="h6 custom-subtitle pt-2 text-break" >
                  Total gifts send this year
                </v-card-title>
              </v-col>
              <v-col class="text-right" v-if="$vuetify.breakpoint.smAndUp">
                <v-btn
                  outlined
                  class="custom-button-outline pt-6 pb-6 px-6 text-transform__initial letter-spacing__normal mt-6 mr-6"
                >
                  Download report
                </v-btn>
              </v-col>
            </v-row>
          </v-col>
          <v-col>
            <bar-chart :data="barChartData" :options="barChartOptions" :height="200" />
          </v-col>
            <v-col v-if="$vuetify.breakpoint.smAndDown" cols="12">
              <v-btn
                outlined
                class="custom-button-outline pt-6 pb-6 px-6 text-transform__initial letter-spacing__normal mt-6 mr-6 mb-6"
              >
                Download report
              </v-btn>
            </v-col>
        </v-row>
      </v-card>
    </v-col>
  </v-row>
</div>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'
import data from "../data";

export default {
  components: {
    Logo,
    VuetifyLogo
  },
  data() {
    return {
      data,
      barChartData: data.barCharData,
      barChartOptions: {
        responsive: true,
        legend: {
          display: false
        },
        title: {
          display: true,
          text: '',
          fontSize: 24,
          fontColor: '#6b7280'
        },
        tooltips: {
          backgroundColor: '#17BF62'
        },
        scales: {
          xAxes: [
            {
              gridLines: {
                display: false
              }
            }
          ],
          yAxes: [
            {
              ticks: {
                beginAtZero: true
              },
              gridLines: {
                display: false
              }
            }
          ]
        }
      }
    }
  }
}
</script>

<style lang="scss" scoped>
@import  '@/assets/utilities.scss'
</style>