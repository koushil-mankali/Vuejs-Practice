<script lang="ts">
let state = () => {
  let btnTxt: string = "Click Me";
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
    displayElement: false,
    num: 0,
    list1: ["koushil", "mankali"],
    list2: [
      { first: "koushil", last: "mankali" },
      { first: "Nani", last: "Dinesh" },
    ],
    list3: [
      {
        name: "koushil",
        det: { job: "Software Developer", cmpy: "ITalentDigital" },
      },
      { name: "nani", det: { job: "Software Developer", cmpy: "XYZ cmpy" } },
    ],
    list4: {
      first: "koushil",
      last: "Mankali",
    },
  };
};
let add = (a: number, b: number): number => {
  return a + b;
};
let mul = (a: number, b: number): number => {
  return a * b;
};
export default {
  data: state,
  methods: {
    add,
    mul,
  },
};
</script>

<template>
  <div>
    <div>{{ greet }} {{ subject }}</div>
    <div>Add: {{ add(10, 10) }}</div>
    <div>Mul: {{ mul(10, 10) }}</div>
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
    <div v-show="displayElement" v-bind:style="[style1, 'color: yellow']">
      Show Me Or Hide Me
    </div>
    <div v-if="num > 1">The number is greater than 1</div>
    <div v-else-if="num < -1">The number is lessthan than -1</div>
    <div v-else>The number is 0</div>
    <template v-for="item in list1" :key="item">
      <h1>{{ item }}</h1>
    </template>
    <div v-for="item in list2" :key="item.first">
      <span>{{ item.first }}</span>
      <span>&nbsp;</span>
      <span>{{ item.last }}</span>
    </div>
    <hr />
    <div v-for="(item, index) in list3" :key="index">
      <div>Name: {{ item.name }}</div>
      <div>Job: {{ item.det.job }}</div>
      <div>Company: {{ item.det.cmpy }}</div>
      <hr />
    </div>
    <div v-for="(list, id) in list4" :key="id">{{ id }}: {{ list }}</div>
    <hr />
    <template v-for="(item, index) in list3">
      <div v-if="item.name === 'koushil'" :key="index">
        <div>Name: {{ item.name }} show</div>
        <div>Job: {{ item.det.job }}</div>
        <div>Company: {{ item.det.cmpy }}</div>
        <hr />
      </div>
    </template>
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
