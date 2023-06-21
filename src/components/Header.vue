<template>
    <div>
      <v-container fluid>
      <v-app-bar 
      scroll-threshold="0"
      color="rgb(80 43 171)"
      >
        <v-spacer></v-spacer>
        <v-btn outlined class="main-btn">
          <router-link to="/">Главная</router-link> 
        </v-btn>
        <v-btn class="tasks-btn ml-3">
          <router-link to="/tasks">Задачи</router-link>
        </v-btn>
      </v-app-bar>
    </v-container>
    <router-view/>
    </div>
</template>

<script>
export default {
  name: 'Header',
}
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

  .v-btn.main-btn {
    border: 3px solid #e9cfff;

    a {
      color: #e9cfff;
      text-decoration: none;
      font-weight: 700;
    }
  }
  
</style>
