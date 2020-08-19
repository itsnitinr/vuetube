<template>
  <div>
    <input @input="onInput" />
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
