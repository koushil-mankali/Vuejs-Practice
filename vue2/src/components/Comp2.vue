<script lang="ts">
export default {
  props: {
    toggleVal: Boolean,
  },
  inject: ["propedValue"],
  data() {
    return {
      name: "Comp2",
      compVal: "Value came from comp2 from emits",
    };
  },
  emits: {
    toggle: (prop: string) => {
      if(prop){
        return true;
      }
      return false;
    }
  },
};
</script>

<template>
  <div v-show="toggleVal">Name: {{ name }} - :prop: {{ propedValue }}</div>
  <button @click="$emit('toggle', compVal)">Toggle</button>
</template>
