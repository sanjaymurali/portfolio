<template>
  <div class="mt-3">
    <div class="my-4" v-for="(work, i) in information" v-bind:key="i">
      <h3>{{work.name.toUpperCase()}}</h3>
      <div class="subheading font-weight-light mb-1">
        <span class="font-italic mr-3">{{work.position}}</span>
        <span>{{work.time}}</span>
      </div>
      <ul>
        <li v-for="(item, j) in work.description" v-bind:key="j">{{item}}</li>
      </ul>
    </div>
  </div>
</template>

<script>
import information from "~/assets/data/work.json";
export default {
  name: "Work",
  data: () => ({
    information: information
  })
};
</script>

<style>
</style>
