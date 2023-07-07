<template>
  <v-col cols="12">
    <v-card>
      <v-card-title>{{ project.title }}</v-card-title>
      <v-row>
        <v-col cols="5" class="project-img">
          <v-card-text>
            <v-img :src="project.path" />
          </v-card-text>
        </v-col>
        <v-col cols="7" class="project-description">
          <v-card-text>
            <a :href="project.description.url" target="_blank">{{
              project.description.url
            }}</a>
          </v-card-text>
          <v-card-text>{{ project.description.stack }}</v-card-text>
          <v-card-text>{{ project.description.text }}</v-card-text>
        </v-col>
      </v-row>
    </v-card>
  </v-col>
</template>

<script>
export default {
  props: {
    project: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style>
.project-img {
  min-width: 320px;
}

@media (max-width: 768px) {
  .project-img,
  .project-description {
    flex: 100%;
    max-width: 1007%;
  }
}
</style>