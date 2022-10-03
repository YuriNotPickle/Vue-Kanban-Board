<template>
  <div id="app">
    <app-kanban />
  </div>
</template>

<script>
import AppKanban from "./components/KanbanBoard.vue";
export default {
  name: "App",
  components: {
    AppKanban,
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 60px;
}
</style>
