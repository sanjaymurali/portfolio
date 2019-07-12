<template>
  <div class="mt-3">
    <div class="my-4" v-for="(education,i) in information" v-bind:key="i">
      <h3>{{education.name.toUpperCase()}}</h3>
      <div class="subheading font-weight-light mb-1">
        <span class="font-italic mr-3">{{education.degree}}</span>
        <span>{{education.attended}}</span>
      </div>
      <div class="subheading mb-1"
        v-if="education.specialization !== undefined">
        Specializing in {{education.specialization}}
      </div>
      <div class="subheading" v-if="education.subjects !== undefined">
        Subjects:
        <span v-for="(subject, j) in education.subjects" v-bind:key="j">
          <a v-if="subject.url !== ''" :href="subject.url" target="_blank">{{subject.name}}</a>
          <span v-else>{{subject.name}}</span>
          {{appendComma(j, education.subjects.length)}}
        </span>
      </div>
    </div>
  </div>
</template>

<script>
import education from "~/assets/data/education.json";
export default {
  name: "Education",
  data: () => ({
    information: education
  }),
  methods: {
    appendComma(index, length) {
      if (index === length - 1) {
        return "";
      } else {
        return ", ";
      }
    }
  }
};
</script>

<style scoped>
a {
  text-decoration: none;
}
</style>
