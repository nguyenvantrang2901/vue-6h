<script setup>
import { ref } from 'vue'
const title = ref("Viet Nam")
const handleInput = (e) => {
    // console.log(e.target.value)
    title.value = e.target.value
}

const checked = ref("true")
const checkedNames = ref([])

const picked = ref("")

const selected = ref("")
</script>
<template>
    <div class="container">
        <h1>Form Event Handler</h1>
        <p>{{ title }}</p>
        <input type="text" @input="handleInput">
        <br>
        <!--Cách khác : Sử dụng V-Model-->
        <input type="text" v-model="title">
        <br>
        <hr>
        <input type="checkbox" v-model="checked">
        <label for="checkbox">{{ checked }}</label>
        <br>
        <hr>
        <div>Array name : {{ checkedNames }}</div>
        <input type="checkbox" id="jack" value="Jack" v-model="checkedNames" />
        <label for="jack">Jack</label><br>
        <input type="checkbox" id="john" value="John" v-model="checkedNames" />
        <label for="john">John</label><br>
        <input type="checkbox" id="alice" value="Alice" v-model="checkedNames" />
        <label for="alice">Alice</label>
        <br>
        <hr>
        <p>Radio Input</p>
        <div>Picked : {{ picked }}</div>
        <input type="radio" id="one" value="One" v-model="picked">
        <label for="one">One</label>
        <input type="radio" id="two" value="Two" v-model="picked">
        <label for="two">Two</label><br><hr>
        <p>Select Option</p>
        <div>Select value :  {{ selected }}</div>
        <select v-model="selected">
            <option value="" disabled>Select One value</option>
            <option value="Vue">Vue</option>
            <option value="React">React</option>
            <option value="Machine Learning">Machine Learning</option>
        </select>
    </div>
</template>


<style scoped>
.container {
    font-weight: bold;
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
    font-size: 14px;
}
</style>
