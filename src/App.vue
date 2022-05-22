<template>
  <div>
    <component
      :is="screens[position]"
      :results="results"
      @goto="handleGoTo"
      @question="handleQuestion"
      @showResults="showResults"
      @startOver="startOver"
      :question="question"
    />
  </div>
</template>

<script>
import Initial from "./components/Initial.vue";
import Confirm from "./components/Confirm.vue";
import Results from "./components/Results.vue";
export default {
  name: "App",
  components: {
    Initial,
    Confirm,
    Results,
  },
  data() {
    return {
      lists: ["yes", "no", "maybe", "call police", "ask friend"],
      screens: ["Initial", "Confirm", "Results"],
      position: 0,
      question: "",
      results: "",
    };
  },
  methods: {
    handleGoTo(position) {
      this.position = position;
    },
    handleQuestion(question) {
      this.question = question;
    },
    getRandom() {
      return this.lists[Math.floor(Math.random() * this.lists.length)];
    },
    generateResults() {
      let rand = this.getRandom();
      if (this.results !== "") {
        while (rand === this.results) {
          rand = this.getRandom();
        }
      }
      this.results = rand;
    },
    showResults() {
      this.generateResults();
    },
    startOver() {
      (this.position = 0), (this.question = ""), (this.results = "");
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  display: flex;
  flex-direction: column;
  color: #2c3e50;
  margin-top: 60px;
}
body {
  margin: 0;
  padding: 0;
  background-color: bisque;
}
</style>
