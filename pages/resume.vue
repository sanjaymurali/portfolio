<template>
  <v-container fill-height>
    <v-layout align-start row wrap>
      <v-flex xs12 sm5>
        <v-card>
          <div class="px-3 py-2 mb-0 text-xs-left">
            <span class="headline mr-2">
              <i class="fas fa-university"></i>
            </span>
            <span class="title">Education</span>
          </div>
        </v-card>
        <Education />
      </v-flex>
      <v-flex xs12 sm6 md6 offset-sm1>
        <v-card>
          <div class="px-3 py-2 mb-0 text-xs-left">
            <span class="headline mr-2">
              <i class="fas fa-laptop-code"></i>
            </span>
            <span class="title">Work</span>
          </div>
        </v-card>
        <Work />
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import Education from "~/components/Education";
import Work from "~/components/Work";
export default {
  name: "Resume",
  components: {
    Education,
    Work
  }
};
</script>

<style scoped>
</style>
