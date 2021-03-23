<template>
  <v-app dark>
    <v-navigation-drawer
      class="custom-dark-navigation-drawer pt-16 px-12"
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <div class="wrapper-container logo mb-12">
        <img
          width="30px"
          :src="logo"
        >
        <div>
          <h2 class="text-uppercase title-logo font-weight-bold">Gemnote</h2>
        </div>
      </div>
      <div class="wrapper-container mb-8">
        <h4 class="font-weight-medium">Ashley Wong</h4>
      </div>
      <div class="spacer mb-8"></div>
      <v-list class="font-weight-medium custom-dark-navigation-drawer" >
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          class="pa-0"
          style="cursor: pointer"
        >
          <v-list-item-content class="custom-dark-navigation-drawer">
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-main>
      <v-container 
      :class="{
        'px-0': $vuetify.breakpoint.mdAndUp
      }">
        <nuxt />
      </v-container>
    </v-main>
    <v-navigation-drawer
      v-model="rightDrawer"
      :right="right"
      temporary
      fixed
    >
      <v-list>
        <v-list-item @click.native="right = !right">
          <v-list-item-action>
            <v-icon light>
              mdi-repeat
            </v-icon>
          </v-list-item-action>
          <v-list-item-title>Switch drawer (click me)</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </v-app>
</template>

<script>
import GemnoteLogo from "@/static/img/gemnote-white-logo.svg";

export default {
  data () {
    return {
      clipped: false,
      drawer: true,
      fixed: false,
      logo: GemnoteLogo,
      items: [
        {
          title: 'Dashboard',
          to: '/'
        },
        {
          title: 'Orders',
          to: '/orders'
        },
        {
          title: 'Send a gift',
          to: '/gift'
        },
        {
          title: 'Users',
          to: '/users'
        },
        {
          title: 'Integration',
          to: '/integration'
        },
        {
          title: 'Setting',
          to: '/setting'
        },
        {
          title: 'Logout',
          to: '/logout'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  }
}
</script>

<style lang="scss" scoped>

.v-application {
  font-family: 'Poppins', sans-serif
}

.custom-dark-navigation-drawer
{
  background:#24292c;
  color: #ebecec;
}

.wrapper-container  {
  display: flex;
  justify-content: flex-start;
  align-items: flex-start;
  &.logo {
    cursor: pointer;
    gap: 8px;
    justify-content: flex-start;
    align-items: center;
  }
}

.title-logo{
  letter-spacing: .2rem;
  font-size: 1.3rem;
}

.spacer{
  width: 100%;
  height: 1px;
  background-color: #3a3e41;
}
</style>