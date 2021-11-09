<template>
  <div>
    <home></home>
    <project-view></project-view>
  </div>
</template>

<script>
import json from "./assets/projects.json";
import Home from "./components/Home.vue";
import ProjectView from "./components/ProjectView.vue";

export default {
  name: "App",
  components: { Home, ProjectView },
  data() {
    return {
      json: json,
    };
  },
};
</script>
