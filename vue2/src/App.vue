<script lang="ts">
import TabA from "./components/TabA.vue";
import TabB from "./components/TabB.vue";
import TabC from "./components/TabC.vue";

export default {
  name: "App",
  data(){
    return{
      activeTab: "TabA",
    }
  },
  components: {
    TabA,
    TabB,
    TabC,
  },
};
</script>

<template>
  <h1>Hi from Vue!</h1>
  <button @click="activeTab = 'TabA'">TabA</button>
  <button @click="activeTab = 'TabB'">TabB</button>
  <button @click="activeTab = 'TabC'">TabC</button>

  <keep-alive>
    <component :is="activeTab" />
  </keep-alive>
</template>

<style>
body {
  height: 100vh;
  background-color: #42b883;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
