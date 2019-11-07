<template>
  <v-app>
    <navbar v-bind:drawer="drawer"  v-on:toolbarEvent="updateToolbar($event)"></navbar>
    <LeftDrawer v-bind:drawer="drawer" v-on:drawerEvent="updateDrawer($e)"></LeftDrawer>
    <v-content fluid fill-height class="grey darken-4">
      <v-container class="grey darken-2">
        <router-view></router-view>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
import navbar from '@/components/navbar'
import LeftDrawer from '@/components/LeftDrawer'
export default {
  name: 'App',
  components: {
    navbar,
    LeftDrawer
  },
  data () {
    return {
      drawer: false
    }
  },
  methods: {
    updateToolbar(parameter) {
      this.drawer = parameter;
    },

    updateDrawer(param) {
      this.drawer = param;
    },
    }

}
</script>
