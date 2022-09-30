<script lang="ts">
    export default{
        name: 'Portal',
    }
</script>

<template>
    <div class="modal">This is Modal</div>
</template>

<style scoped>
    .modal{
        width: 300px;
        height: 300px;
        display: flex;
        justify-content: center;
        align-items: center;
        color: whitesmoke;
        font-weight: 600;
        font-size: 1.2rem;
        letter-spacing: 0.5px;
        background-color: rgba(255, 255, 255, 0.4);
    }
</style>