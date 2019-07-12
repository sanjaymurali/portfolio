<template>
  <div>
    <v-layout hidden-md-and-up justify-left class="ml-2 mt-2">
      <font-awesome-icon class="headline" icon="bars" @click.stop="drawer = !drawer"></font-awesome-icon>
    </v-layout>

    <v-navigation-drawer v-model="drawer" app mobile-break-point="769">
      <v-container fill-height>
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
      { title: "Home", url: "/", icon: "home" },
      { title: "Projects", url: "projects", icon: "briefcase" },
      { title: "Resume", url: "resume", icon: "file" }
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
.v-list a {
  text-decoration: none;
  color: black;
}

.theme--dark .v-list a {
  text-decoration: none;
  color: white;
}

.align-bottom {
  bottom: 0;
  position: absolute;
  margin-left: 20px;
}
</style>
