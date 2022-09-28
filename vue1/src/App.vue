<script lang="ts">
function state() {
  return {
    firstName: "First Name",
    lastName: "Lsat Name",
  };
}

function fullname(this: { firstName: string; lastName: string }) {
  console.log("Called method");
  return this.firstName + " " + this.lastName;
}
function fullnamec(this: { firstName: string; lastName: string }) {
  console.log("Called computed");
  return this.firstName + " " + this.lastName;
}

export default {
  data: state,
  methods: {
    fullname,
  },
  computed: {
    fullnamec,
  },
};
</script>

<template>
  <div>Mushtash: {{ firstName }} {{ lastName }}</div>
  <div>Method: {{ fullname() }}</div>
  <div>computed: {{ fullnamec }}</div>
</template>

<style scope></style>
