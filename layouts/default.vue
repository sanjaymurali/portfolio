<template>
  <div>
    <v-layout justify-left class="ml-2 mt-2">
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
                <router-link :to="item.url">{{ item.title }}</router-link>
              </v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
      </v-container>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  data: ()  => ({
    items: [
      { title: "Home", url: "home", icon: "home" },
      { title: "Projects", url: "project", icon: "briefcase" },
      { title: "Resume", url: "resume", icon: "file" }
    ],
    drawer: null
  })
}
</script>
