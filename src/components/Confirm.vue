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
    <h3>Your question is:</h3>
    <h5>{{ question }}</h5>
    <div>
      <div class="m-5">
        <button
          class="m-auto bg-brand-teal text-color no-border p-8"
          style="min-width: 190px"
          @click.prevent="GoFoward"
        >
          Decide it
        </button>
      </div>
      <div>
        <button
          class="m-auto bg-brand-teal text-color no-border p-8"
          style="min-width: 190px"
          @click.prevent="goBack"
        >
          Ask A new Question
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["question"],
  data() {},
  methods: {
    GoFoward() {
      this.$emit("goto", 2);
    },
    goBack() {
      this.$emit("goto", 0);
      this.$emit("question", "");
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
.m-5 {
  margin: 5px;
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