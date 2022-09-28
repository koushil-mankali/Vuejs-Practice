<script lang="ts">
function inc(this: { count: number }, event: Event, incVal: number) {
  return (this.count += incVal || 1);
}

function dec(this: { count: number }) {
  if (this.count === 0) {
    return alert("Count reached minimum value!");
  }
  this.count -= 1;
}

export default {
  data: () => {
    return {
      count: 0,
    };
  },
  methods: {
    inc,
    dec,
  },
};
</script>

<template>
  <div>
    <div class="m1">Welcome to Vue!</div>
    <div class="m1 crimson">Count {{ count }}</div>
    <button class="button" @:click="inc($event)">Inc</button>
    <button class="button" @:click="dec()">dec</button>
    <button class="button" @:dblclick="inc($event, 5)">Inc</button>
  </div>
</template>

<style scoped>
.m1 {
  margin: "1rem";
}

.crimson {
  color: crimson;
}

.button {
  padding: 10px;
  border-radius: 5px;
  background-color: yellow;
  margin: 5px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
}
</style>
