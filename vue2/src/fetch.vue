<script lang="ts">
import TabA from "./components/TabA.vue";
import TabB from "./components/TabB.vue";
import TabC from "./components/TabC.vue";
import Portal from "./components/Portal.vue";
import Posts from "./components/Posts.vue";

export default {
  name: "fetch",
  data() {
    return {
      activeTab: "TabA",
      posts: [],
      title: "",
      body: "",
      userId: "",
    };
  },
  components: {
    TabA,
    TabB,
    TabC,
    Portal,
    Posts,
  },
  created(this: { posts: [] }) {
    fetch("https://jsonplaceholder.typicode.com/posts")
      .then((res) => res.json())
      .then((res) => (this.posts = res));
  },
  methods: {
    submitForm(this: { title: string; body: string; userId: string }) {
      console.log("Form submited!", {
        title: this.title,
        body: this.body,
        userId: this.userId,
      });
      fetch("https://jsonplaceholder.typicode.com/posts", {
        method: "POST",
        body: JSON.stringify({
          title: this.title,
          body: this.body,
          userId: this.userId,
        }),
        headers: {
          "Content-type": "application/json; charset=UTF-8",
        },
      })
        .then((res) => res.json())
        .then((res) => console.log("Response:", res));
    },
  },
};
</script>

<template>
  <h1>Hi from Vue!</h1>
  <button @click="activeTab = 'TabA'">TabA</button>
  <button @click="activeTab = 'TabB'">TabB</button>
  <button @click="activeTab = 'TabC'">TabC</button>

  <form @submit.prevent="submitForm">
    <div>
      <label for="userId">ID:</label>
      <input type="text" id="userId" name="userId" v-model="userId" />
    </div>
    <div>
      <label for="title">Title:</label>
      <input type="text" id="title" name="title" v-model="title" />
    </div>
    <div>
      <label for="body">Body:</label>
      <input type="text" id="body" name="body" v-model="body" />
    </div>
    <button class="btn" type="submit">Submit</button>
  </form>

  <!-- <keep-alive>
    <component :is="activeTab" />
  </keep-alive>

  <teleport to="#modal">
    <Portal />
  </teleport> -->
  <div v-for="post in posts">
    <Posts :post="post" />
  </div>
</template>

<style>
body {
  height: 100%;
  background-color: #42b883;
  display: flex;
  justify-content: center;
  align-items: center;
}

form {
  width: 300px;
  height: 300px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  margin: auto;
  border-radius: 5px;
  border: 1px solid #eee;
  box-shadow: 2px 2px 2px #eee;
  background-color: aquamarine;

  color: crimson;
  font-weight: 700;
  font-size: 1rem;
}

.btn {
  width: 30%;
  margin: auto;
  cursor: pointer;
  background-color: crimson;
  color: white;
  border: none;
  border-radius: 5px;
  padding: 5px;
  font-weight: 700;
}
</style>
