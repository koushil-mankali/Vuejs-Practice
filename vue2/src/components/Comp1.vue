<script lang="ts">
import Comp2 from "./Comp2.vue";

export default {
  components: {
    Comp2,
  },
  data() {
    return {
      name: "Comp1",
      toggleVal: true,
      compVal: 'Comp 1 Value',
    };
  },
  methods:{
      toggle(this: {toggleVal: boolean, compVal: string}, prop: string){
        console.log(this.toggleVal, 'tog');
        this.compVal = prop;
        return this.toggleVal = !this.toggleVal;
      },
    },
};
</script>

<template>
  <div>Name: {{ name }}</div>
  <div>{{compVal}}</div>
  <Comp2 @toggle="toggle" :toggleVal="toggleVal" />
</template>
