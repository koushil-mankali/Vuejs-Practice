<script lang="ts">
    export default{
        name: "Posts",
        props: {
            post: Object,
        }
    }
</script>

<template>
    <div class="card">
        <h1>{{post.id}}. {{post.title}}</h1>
        <p>{{post.body}}</p>
    </div>
</template>

<style scoped>
    .card{
        width: 90%;
        height: 200px;
        padding: 10px;
        margin: 0.5rem;
        border-radius: 5px;
        border: 1px solid #eee;
        box-shadow: 2px 2px 2px #eee;
    }
</style>