<template>
<v-container fluid>
  <uieditor ref="ui"></uieditor>
  <v-navigation-drawer
      stateless
      right
      v-if="$store.getters.getDrawerRight"
      clipped
      permanent
      hide-overlay
      app
      class="pa-2"
      width='220'
    >
      <!-- v-if="$store.getters.getDrawerRight" -->
      <toolspanel @createElement="addElement($event)"></toolspanel>
    </v-navigation-drawer>
   <v-btn
      v-if="$route.name === 'create' && !$store.getters.getDrawerRight" 
      @click.prevent="$store.dispatch('setDrawerRight')"
      v-show="!hidden"
      color="grey darken-2"
      dark
      absolute
      bottom
      right
      fab
    >
      <v-icon>fa-edit</v-icon>
    </v-btn>
</v-container>
</template>
<script src="./container.js"></script>