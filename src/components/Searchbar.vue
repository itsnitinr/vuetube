<template>
  <div>
    <input @input="onInput" placeholder="Search for videos" />
  </div>
</template>

<script>
export default {
  name: "Searchbar",
  methods: {
    onInput(event) {
      this.$emit("termChange", event.target.value);
    },
  },
};
</script>

<style scoped>
input {
  padding: 0.5rem 1rem;
  background: #181818;
  color: #eee;
  border: 1px solid #000000;
  outline: 1px solid #7a7a7a;
  font-size: 1.2rem;
}

@media (max-width: 700px) {
  input {
    margin-left: 1rem;
    padding: 0.5rem;
  }
}
</style>