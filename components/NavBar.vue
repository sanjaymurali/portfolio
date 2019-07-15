<template>
  <div>
    <v-layout hidden-md-and-up justify-left class="ml-2 mt-2">
      <span class="headline" @click.stop="drawer = !drawer"><i class="fas fa-bars"></i></span>
    </v-layout>

    <v-navigation-drawer v-model="drawer" app mobile-break-point="769">
      <v-container fill-height>
        <v-list>
          <v-list-tile v-for="item in items" :key="item.title">
            <v-list-tile-action>
              <span v-bind:class="item.icon"></span>
            </v-list-tile-action>

            <v-list-tile-content>
              <v-list-tile-title class="body-2">
                <nuxt-link :to="item.url">{{ item.title }}</nuxt-link>
              </v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
          <div class="align-bottom">
            <v-switch @change="emitSelection()" :label="'Dark Mode'"></v-switch>
          </div>
        </v-list>
      </v-container>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  name: "NavBar",
  data: () => ({
    items: [
      { title: "Home", url: "/", icon: "fas fa-home" },
      { title: "Projects", url: "projects", icon: "fas fa-briefcase" },
      { title: "Resume", url: "resume", icon: "fas fa-file" }
    ],
    drawer: null,
    darkSwitch: false
  }),
  methods: {
    emitSelection() {
      this.darkSwitch = !this.darkSwitch;
      this.$emit("selection", this.darkSwitch);
    }
  }
};
</script>

<style scoped>
.align-bottom {
  bottom: 0;
  position: absolute;
  margin-left: 20px;
}
</style>
