<template>
  <div>
    <v-layout hidden-md-and-up justify-left class="ml-2 mt-2">
      <font-awesome-icon class="headline" icon="bars" @click.stop="drawer = !drawer"></font-awesome-icon>
    </v-layout>
    <v-navigation-drawer v-model="drawer" app mobile-break-point="769">
      <v-container fill-height>
        <v-layout align-center >
        <v-list>
          <v-list-tile v-for="item in items" :key="item.title">
            <v-list-tile-action>
              <font-awesome-icon v-bind:icon="item.icon"></font-awesome-icon>
            </v-list-tile-action>

            <v-list-tile-content>
              <v-list-tile-title class="body-2">
                <nuxt-link :to="item.url">{{ item.title }}</nuxt-link>
              </v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
        </v-layout>

              <v-layout align-end justify-start>
        <v-switch v-model="darkSwitch" v-on:change="emitSelection" label="Dark Mode"></v-switch>
      </v-layout>
      </v-container>

    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  name: "NavBar",
  data: () => ({
    items: [
      { title: "Home", url: "/", icon: "home" },
      { title: "Projects", url: "projects", icon: "briefcase" },
      { title: "Resume", url: "resume", icon: "file" }
    ],
    drawer: null,
    darkSwitch: false
  }),
  methods: {
    emitSelection() {
      this.$emit("selection", this.darkSwitch);
    }
  }
};
</script>

<style scoped>
.v-list a {
  text-decoration: none;
  color: black;
}
</style>
