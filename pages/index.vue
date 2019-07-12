<template>
  <v-container fill-height>
    <div>
      <div id="hello">Hello!</div>

      <div class="headline mb-2">
        I'm Sanjay Murali, a Software Developer and I love building for the web.
      </div>

      <v-list dense class="d-inline-flex">
        <v-list-tile class="home-v-list__first">
          <a href="https://www.linkedin.com/in/sanjaymurali" target="_blank">
            <font-awesome-icon :icon="['fab', 'linkedin']" class="headline"></font-awesome-icon>
          </a>
        </v-list-tile>
        <v-list-tile>
          <a href="https://github.com/sanjaymurali" target="_blank">
            <font-awesome-icon :icon="['fab', 'github']" class="headline"></font-awesome-icon>
          </a>
        </v-list-tile>
        <v-list-tile>
          <a href="Sanjay_Murali-Resume.pdf" target="_blank">
            <font-awesome-icon icon="file" class="headline"></font-awesome-icon>
          </a>
        </v-list-tile>
        <v-list-tile>
          <a href="mailto:murali.s@husky.neu.edu" target="_blank">
            <font-awesome-icon icon="envelope" class="headline"></font-awesome-icon>
          </a>
        </v-list-tile>
      </v-list>
    </div>
  </v-container>
</template>

<script>
export default {};
</script>

<style scoped>
#hello {
  font-family: "Kalam", cursive;
  font-size: 40px;
  margin-bottom: 5px;
}

.v-list {
  background-color: transparent;
}

.v-list a {
  color: black;
}

.theme--dark .v-list a {
  color: white;
}

.v-list >>> .home-v-list__first .v-list__tile {
  padding-left: 0;
}
</style>
