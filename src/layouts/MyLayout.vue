<template>
  <q-layout view="lHh Lpr lFf">
    <q-layout-header>
      <q-toolbar
        color="primary"
        :glossy="$q.theme === 'mat'"
        :inverted="$q.theme === 'ios'"
      >
        <q-btn
          flat
          dense
          round
          @click="leftDrawerOpen = !leftDrawerOpen"
          aria-label="Menu"
        >
          <q-icon name="menu" />
        </q-btn>

        <q-toolbar-title>
          Quasar App
          <div slot="subtitle">Running on Quasar v{{ $q.version }}</div>
        </q-toolbar-title>
      </q-toolbar>
    </q-layout-header>

      <q-page padding>
       <menu-component></menu-component>
      </q-page>

    <!--<q-page-container>
      <router-view />
    </q-page-container>
    -->
  </q-layout>
</template>

<script>
import { openURL } from 'quasar'
import ListadoComponent from '../components/menuComponent'

export default {
  name: 'MyLayout',
   components: {
    'menu-component': ListadoComponent
  },
  data () {
    return {
      leftDrawerOpen: this.$q.platform.is.desktop
    }
  },
  methods: {
    openURL
  }
  
}
</script>

<style>
</style>
