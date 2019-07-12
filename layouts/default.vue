<template>
  <v-app v-bind:dark="dark">
    <NavBar v-on:selection="fromChild" />
    <v-content>
      <nuxt />
    </v-content>
  </v-app>
</template>

<script>
import NavBar from "~/components/NavBar.vue";
export default {
  components: {
    NavBar
  },
  data: () => ({
    dark: false
  }),
  methods: {
    fromChild(selected) {
      this.dark = selected;
    }
  }
};
</script>

<style>
</style>
