<script setup>
import { ref } from 'vue'

const myChannel = "https://www.youtube.com/watch?v=FN7ALfpGxiI"
const myImage = 'https://i.ytimg.com/vi/FN7ALfpGxiI/hqdefault.jpg?sqp=-oaymwEnCNACELwBSFryq4qpAxkIARUAAIhCGAHYAQHiAQoIGBACGAY4AUAB&rs=AOn4CLCBitBHhvsVYOot-1_N6mJyCrthTw'
const myAlt = "Image information"
const imageHeight = 200
const imageWidth = 300

</script>
<template>
    <h1>Home component</h1>    
    <a v-bind:href="myChannel">My Channel</a>
    <img :src="myImage" :alt="myAlt" :height="imageHeight" :width="imageWidth" />
</template>

<style scoped>

</style>
