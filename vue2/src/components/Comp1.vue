<script lang="ts">
import Comp2 from "./Comp2.vue";

export default {
  components: {
    Comp2,
  },
  data() {
    return {
      name: "Comp1",
    };
  },
};
</script>

<template>
  <div>Name: {{ name }}</div>
  <Comp2 />
</template>
