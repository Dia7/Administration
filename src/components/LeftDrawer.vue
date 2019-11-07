<template>
  <v-navigation-drawer class="cyan lighten-4" v-model="openDrawer">
      <p>test</p>
  </v-navigation-drawer>
</template>

<script>
import { bus } from '@/main'

export default {
  name: 'LeftDrawer',

  props: {
    drawer: {
        type: Boolean
    }
  },

  data () {
    return {
      openDrawer: this.drawer
    }
  },

  created () {
    bus.$on('action', (data) => {
      this.openDrawer = data
    })
  }

}
</script>
