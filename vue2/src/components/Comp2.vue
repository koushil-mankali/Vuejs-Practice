<script lang="ts">
export default {
  inject: ['propedValue'],
  data() {
    return {
      name: "Comp2",
    };
  },
};
</script>

<template>
  <div>Name: {{ name }} - :prop: {{ propedValue }}</div>
</template>
