<script setup>

const props = defineProps(["groupName"])
const emits = defineEmits(["action"])
const clickHandler = () => emits("action")
</script>

<template>
    <div>
        <h1>{{props.groupName}}</h1>
        <button @click="clickHandler">Select</button>
    </div>
</template>

<style scoped>
div{
    width: 250px;
    height: 200px;
    float: left;
    margin: 10px;
    padding: 10px;
    background-color: aqua;
    border: 2px solid red;
}

h1{
    width: 25px;
    height: auto;
    margin-left: 35px;
}

button{
    width: 80px;
    height: 50px;
    background-color: bisque;
    margin-left: 70px;
    margin-top: 40px;
}
</style>