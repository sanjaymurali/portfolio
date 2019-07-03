<template>
  <v-container fill-height>
    <v-layout align-start justify-center column>
      <div class="my-3" v-for="(project, i) in projects" v-bind:key="i">
        <div class="display-1 mb-2">
          <a v-bind:href="project.url" target="_blank">
            {{project.name}}
            <font-awesome-icon class="headline" v-bind:icon="'arrow-right'"></font-awesome-icon>
          </a>
        </div>
        <div class="subheading">{{project.description}}</div>

        <div class="d-inline-flex mr-2 mt-2" v-for="(tag,j) in project.tags" v-bind:key="j">
          <v-chip label outline color="secondary">
            <a :href="tags_lookup[tag]" target="_blank">{{tag}}</a>
          </v-chip>
        </div>
      </div>
    </v-layout>
  </v-container>
</template>

<script>
import projects from "~/assets/data/projects.json";
import tags from "~/assets/data/tags.json";
export default {
  name: "Projects",
  data: () => ({
    projects: projects,
    tags_lookup: tags
  })
};
</script>

<style scoped>
a {
  text-decoration: none;
}

.v-list {
  background: transparent;
}

.v-list >>> .project-v-list__0 .v-list__tile {
  padding-left: 0;
}

.v-list >>> .v-list__tile {
  padding: 0 5px;
}

.project-v-list__margin {
  margin: 60px 0;
}

.v-chip {
  margin: 0;
}
</style>
