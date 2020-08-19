<template>
  <div>
    <input />
  </div>
</template>

<script>
export default {
  name: "Searchbar",
  methods: {
    onInput: function (event) {
      console.log(event.target.value);
    },
  },
};
</script>
