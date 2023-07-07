<template>
  <v-main>
    <v-container>
      <v-row>
        <Project v-for="project in projects" :project="project" />
      </v-row>
      <v-btn class="tasks-btn">
        <router-link to="/tasks">Todo</router-link>
      </v-btn>
    </v-container>
  </v-main>
</template>

<script>
import Project from "@/components/project/Project.vue";
export default {
  components: {
    Project,
  },
  data: () => ({
    projects: [],
  }),
  mounted() {
    this.fetchTodo();
  },
  methods: {
    fetchTodo() {
      console.log(this);
      this.axios
        .get(
          "https://raw.githubusercontent.com/DariaGrekova/db_projects/main/db.json"
        )
        .then((response) => {
          this.projects = response.data;
        });
    },
  },
};
</script>

<style scoped lang="scss">
.v-btn {
  &.tasks-btn {
    background-color: #e9cfff;

    a {
      color: rgb(87, 0, 138);
      text-decoration: none;
      font-weight: 700;
      display: block;
      width: 100%;
      height: 100%;
    }
  }
}
</style>