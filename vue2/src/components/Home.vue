<script lang="ts">
  import Comp1 from './Comp1.vue';
export default {
  name: "Home",
  components:{
    Comp1,
  },
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
      propedValue: "Proped Vlaue",
    };
  },
  inheritAttrs: false,
  provide(this: {propedValue: String}) {
    return{
      propedValue: this.propedValue,
    }
  }
}; 
</script>

<template>
  <div>
    <Comp1 />
    <h1 :="$attrs">{{ txt }} - {{name}} - num: {{num}} - isMainPage {{isMainPage ? "Yes" : "No"}}</h1>
  </div>
</template>

<style scoped></style>
