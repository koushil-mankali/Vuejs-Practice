<script lang="ts">
    export default{
        name: 'Slot',
        data(){
            return{
                list: ["Card1", "Card2", "Card3"]
            }
        }
    }
</script>

<template>
    <div>
        <slot>Default slot content</slot>
    </div>
    <div>
        <slot name="txtSlot"></slot>
    </div>
    <div>
        <slot name="bdy"></slot>
    </div>
    <div v-for="item in list">
        <slot name="crds" :item="item"></slot>
    </div>
</template>

<style scoped>

</style>