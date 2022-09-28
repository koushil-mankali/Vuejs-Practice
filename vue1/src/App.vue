<script lang="ts">
function inc(this: { count: number }, event: Event, incVal: number) {
  console.log(event, "Event");
  return (this.count += incVal || 1);
}

function dec(this: { count: number }) {
  if (this.count === 0) {
    return alert("Count reached minimum value!");
  }
  this.count -= 1;
}

function submitForm(
  this: {
    formValues: {
      name: string;
      about: string;
      graduate: boolean;
      education: [];
      exp: string;
    };
  },
  e: Event
) {
  e.preventDefault();
  console.log(this.formValues, "values");
}

export default {
  data: () => {
    return {
      count: 0,
      formValues: {
        name: "",
        about: "",
        graduate: false,
        education: [],
        exp: "",
      },
    };
  },
  methods: {
    inc,
    dec,
    submitForm,
  },
};
</script>

<!-- <template>
  <div>
    <div class="m1">Welcome to Vue!</div>
    <div class="m1 crimson">Count {{ count }}</div>
    <button class="button" @:click="inc($event)">Inc</button>
    <button class="button" @:click="dec()">dec</button>
    <button class="button" @:dblclick="inc($event, 5)">Inc</button>
  </div>
 
</template> -->

<template>
  <div>
    <div>
      <div class="m1">Welcome to Vue!</div>
      <div class="m1 crimson">Count {{ count }}</div>
      <button class="button" @:click="inc($event)">Inc</button>
      <button class="button" @:click="dec()">dec</button>
      <button class="button" @:dblclick="inc($event, 5)">Inc</button>
    </div>
    <form @submit="submitForm" class="form">
      <div>
        <label for="name">Name</label>
        <input type="text" name="name" id="name" v-model="formValues.name" />
      </div>
      <div>
        <label for="about">About</label>
        <textarea name="about" id="about" v-model="formValues.about" />
      </div>
      <div>
        <label for="graduate">Graducate</label>
        <input
          type="checkbox"
          name="graduate"
          id="graduate"
          v-model="formValues.graduate"
        />
      </div>
      <div>
        <label for="education">Education</label>
        <div>
          <input
            type="checkbox"
            name="ssc"
            id="ssc"
            value="SSC"
            v-model="formValues.education"
          />
          <label for="ssc">SSC</label>
          <input
            type="checkbox"
            name="inter"
            id="inter"
            value="Inter"
            v-model="formValues.education"
          />
          <label for="inter">Inter</label>
          <input
            type="checkbox"
            name="btech"
            id="btech"
            value="BTECH"
            v-model="formValues.education"
          />
          <label for="btech">BTECH</label>
        </div>
      </div>
      <div>
        <label for="exp">Experience:</label>
        <div>
          <input
            type="radio"
            name="1"
            id="1"
            v-model="formValues.exp"
            value="1"
          />
          <label for="1">1 Year</label>

          <input
            type="radio"
            name="2"
            id="2"
            v-model="formValues.exp"
            value="2"
          />
          <label for="2">2 Year</label>

          <input
            type="radio"
            name="3"
            id="3"
            v-model="formValues.exp"
            value="3"
          />
          <label for="3">3 Year</label>
        </div>
      </div>
      <button>Submit</button>
    </form>
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

.form {
  width: 300px;
  height: 300px;
  margin: auto;
  padding: 10px;
  border: 1px solid white;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
}
</style>
