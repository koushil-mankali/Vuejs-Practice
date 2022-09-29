<script lang="ts">
export default {
  name: "Home",
  props: {
    name: String,
  },
  data() {
    return {
      txt: "Home Component",
    };
  },
};
</script>

<template>
  <h1>{{ txt }} - {{name}}</h1>
</template>

<style scoped></style>
