<script lang="ts">
  import Slot from './components/Slot.vue';

  export default{
    components:{
      Slot,
    }
  }
</script>

<template>
    <h1>Hello vue!</h1>
    <Slot #txtSlot>Hello from slot</Slot>
    <Slot #bdy>
      <div class="card">
          This is Card!
      </div>
    </Slot>
    <Slot #crds="slotProps">
      <div class="card">
          {{slotProps.item}}
      </div>
    </Slot>
</template>

<style>
  body{
    height: 100vh;
    background-color: #42B883;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .card{
    width: 100px;
    height: 100px;
    border-radius: 5px;
    border: 1px solid #eee;
    background-color: aliceblue;
    display: flex;
    justify-content: center;
    align-items: center;
    box-shadow: 3px 3px 1px #eee;
    margin: 1rem;
  }
</style>