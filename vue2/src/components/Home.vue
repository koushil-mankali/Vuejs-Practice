<script lang="ts">
export default {
  name: "Home",
  props: {
    name: String,
    num: {
      type: Number,
      default: 111,
      required: true,
    },
    isMainPage: {
      type: Boolean,
      default: false,
      required: true,
    }
  },
  data() {
    return {
      txt: "Home Component",
    };
  },
  inheritAttrs: false,
};
</script>

<template>
  <div>
    <h1 :="$attrs">{{ txt }} - {{name}} - num: {{num}} - isMainPage {{isMainPage ? "Yes" : "No"}}</h1>
  </div>
</template>

<style scoped></style>
