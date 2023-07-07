<template>
  <v-col cols="12">
    <v-card>
      <v-card-title>{{ project.title }}</v-card-title>
      <v-col cols="6">
        <v-card-text>
          <v-img width="400" height="400" :src="project.path" />
        </v-card-text>
        <v-card-text>
          <ul>
            <li>888</li>
            <li>888</li>
          </ul>
        </v-card-text>
      </v-col>
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
</style>