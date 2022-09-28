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
    css: "white",
    isGreen: false,
    green: "green",
    red: "red",
    bold: "bold",
    italic: true,
    style1: {
      color: "orange",
      "font-weight": "bold",
      "font-style": "italic",
    },
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
    <div class="dcss" v-bind:class="css">Test CSS</div>
    <div v-bind:class="isGreen ? green : red">Test CSS 1</div>
    <div v-bind:class="[isGreen ? green : red, bold]">Test CSS 2</div>
    <div
      v-bind:class="{
        green: isGreen,
        red: !isGreen,
        italic: italic,
      }"
    >
      Test CSS 3
    </div>
    <h2 v-bind:style="{ color: 'pink', fontWeight: bold }">
      H2 CSS Test with Style
    </h2>
    <h2 v-bind:style="[style1, 'color: hotpink']">H2 CSS Test with Style 2</h2>
  </div>
</template>

<style scoped>
.test {
  color: red;
}
.test1 {
  background-color: orange;
}
.dcss {
  background-color: red;
}
.white {
  color: white;
  font-weight: bold;
  font-size: 1.2rem;
}
.bold {
  font-weight: bold;
  font-size: 1.2rem;
}

.italic {
  font-style: italic;
}
.green {
  color: green;
}
.red {
  color: red;
}
</style>
