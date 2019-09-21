<template>
  <q-layout view="hHh Lpr fff">
    <q-header reveal elevated class="bg-deep-purple-8 text-white">
      <q-toolbar>
        <q-toolbar-title>
          Linked Market - CMS
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer bordered class="bg-blue-grey-10 text-white">
      <q-toolbar>
        <q-toolbar-title class="text-subtitle2" style="text-align:right;">
          Copyright © 2019 트라이패스㈜
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>
  </q-layout>
</template>

<script>
export default {
  name: 'LoginLayout'
}
</script>

<style>
</style>
