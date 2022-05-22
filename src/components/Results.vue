<template>
  <div
    class="
      inline-block
      p-15
      m-10
      justify-between
      align-center
      bg-white
      rounded-border
    "
  >
    <h3>Your Answer is:</h3>
    <h5>{{ results }}</h5>
    <div>
      <div class="m-5 mb-3">
        <button
          class="m-auto bg-brand-teal text-color no-border p-8"
          style="min-width: 190px"
          @click.prevent="startOver"
        >
          start Over
        </button>
      </div>
      <div>
        <button
          class="m-auto bg-brand-teal text-color no-border p-8"
          style="min-width: 190px"
          @click.prevent="getResults"
        >
          Decide again
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["results"],
  components: {},
  mounted() {
    this.$emit("showResults");
    this.getResults();
  },
  methods: {
    startOver() {
      this.$emit("startOver");
    },
    getResults() {
      this.$emit("showResults");
    },
  },
};
</script>

<style scoped>
.flex {
  display: flex;
}
.inline-block {
  display: inline-block;
}
.p-15 {
  padding: 15px;
}
.m-10 {
  margin: 10px;
}
m-5 {
  margin: 5px;
}
.mb-3 {
  margin-bottom: 5px;
}
.justify-between {
  justify-content: space-between;
}
.align-center {
  align-items: center;
}
.bg-white {
  background-color: white;
}
.rounded-border {
  border-radius: 4px;
}
.m-auto {
  margin: auto;
}
.bg-brand-teal {
  background-color: teal;
}
.text-color {
  color: black;
}
.p-8 {
  padding: 8px;
}
.p-6 {
  padding: 6px;
}
min-60 {
  min-width: 60px;
}
.no-border {
  border: none;
}
.text-red {
  color: red;
}
</style>