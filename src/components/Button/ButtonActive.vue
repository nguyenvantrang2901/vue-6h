<script setup>
import { reactive, ref } from 'vue'
const isActive = ref(true)
const hasError = ref(true)

const objectAttribute = reactive({
    'active': isActive,
    'has-error' : hasError
})
</script>
<template>
    <button class="button" :class="objectAttribute">Active</button>
</template>


<style scoped>
.active {
    font-size: 30px;
}
.has-error {
    font-style: italic;
}
.button {
    font-weight: bold;
    width: 130px;
    height: 50px;
    border: none;
    background: #8b5cf6;
    color: #ede9fe;
    padding: 10px 14px;
    border-radius: 10px;
    cursor: pointer;
    &:hover {
        background: #818cf8;
    }
}
</style>
