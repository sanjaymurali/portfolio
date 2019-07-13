<template>
  <v-container fill-height>
    <div>
      <div id="hello">Hello!</div>

      <div class="headline mb-2">I'm Sanjay Murali, a Software Developer and I love building for the web.</div>

      <v-list dense class="d-inline-flex">
        <v-list-tile class="home-v-list__first">
          <a aria-label="Sanjay's LinkedIn" rel="noopener" class="headline" href="https://www.linkedin.com/in/sanjaymurali" target="_blank">
            <span class="fab fa-linkedin"></span>
          </a>
        </v-list-tile>
        <v-list-tile>
          <a aria-label="Sanjay's GitHub" rel="noopener" class="headline" href="https://github.com/sanjaymurali" target="_blank">
            <span class="fab fa-github"></span>
          </a>
        </v-list-tile>
        <v-list-tile>
          <a aria-label="Sanjay's Resume" rel="noopener" class="headline" href="Sanjay_Murali-Resume.pdf" target="_blank">
            <span class="fas fa-file"></span>
          </a>
        </v-list-tile>
        <v-list-tile>
          <a aria-label="My Email Address" rel="noopener" class="headline" href="mailto:murali.s@husky.neu.edu" target="_blank">
            <span class="fas fa-envelope"></span>
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
