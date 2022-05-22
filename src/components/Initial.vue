<template>
  <div>
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
      <h2>Ask A Question</h2>
      <input
        type="text"
        name="question"
        id="question"
        class="p-6"
        style="min-width: 140px"
        v-model="question"
      />
      <p>
        <button
          class="m-auto bg-brand-teal text-color no-border p-8"
          style="min-width: 190px"
          v-if="question"
          @click.prevent="handleNext"
        >
          Next
        </button>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      question: "",
    };
  },
  methods: {
    handleNext() {
      this.$emit("goto", 1);
      this.$emit("question", this.question);
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