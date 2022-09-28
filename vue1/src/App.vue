<script lang="ts">
let state = () => {
  let btnTxt = "Click Me";
  return {
    greet: "Hell",
    subject: "World!",
    buttonId: "button",
    classes: "test test1",
    isDisabled: true,
    test: "This app is beign developed with the help of Vue!",
    html: `<button onclick="alert('hi')">${btnTxt}</button>`,
  };
};
export default {
  data: state,
};
</script>

<template>
  <div>
    <div>{{ greet }} {{ subject }}</div>
    <div v-text="test"></div>
    <button v-bind:disabled="isDisabled">Disabled Button</button>
    <div v-html="html" v-bind:id="buttonId" v-bind:class="classes"></div>
  </div>
</template>

<style scoped></style>
