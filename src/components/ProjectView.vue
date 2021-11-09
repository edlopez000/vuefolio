  <template>
  <div class="container">
    <button @click="previousIndex">Previous Project</button>
    <button @click="nextIndex">Next Project</button>
    <div>
      <h1>
        Project Title:
        {{ myJson[index].projectTitle }}
      </h1>
      <img :src="myJson[index].image" />
      <a :href="myJson[index].url"> {{ myJson[index].url }}</a>
      <p>{{ myJson[index].purpose }}</p>
      <p>{{ myJson[index].objective }}</p>
    </div>
  </div>
</template>

<script>
import json from "../assets/projects.json";

export default {
  name: "ProjectView",
  data() {
    return {
      myJson: json,
      index: 0,
    };
  },
  methods: {
    nextIndex() {
      this.index++;
      if (this.index === this.myJson.length) {
        this.index = 0;
        return this.index;
      }
      return this.index;
    },
    previousIndex() {
      if (this.index == 0) {
        this.index = this.myJson.length;
        return this.index--;
      }
      return this.index--;
    },
  },
};
</script>