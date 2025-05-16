<script setup>
import { ref } from 'vue'
const courses = ref([
    {id:1, title: "VueJS"},
    {id:2, title: "ReactJs"},
    {id:3, title: "React Native"},
    {id:4, title: "Java spring boot"},
])
const newCourse = ref("")
const handleAddNew = () => {
    if(newCourse.value.trim() == "") return alert("Invalid field")
    const course = {
        id: courses.value.length + 1,
        title: newCourse.value
    }
    courses.value.push(course)
    newCourse.value = ""
}

const handleDelete = (index) => {
    // return courses.value.splice(index, 1)
    // return courses.value = courses.value.filter((item, id) => id !== index)
    // _ ở đây biểu thị biến không cần dùng đến, Ko quan tâm => để là gì cũng đc.
    return courses.value = courses.value.filter((_, id) => id !== index)
}
</script>
<template>
    <div>
        <input type="text" v-model="newCourse" @keyup.enter="handleAddNew">
        <button @click="handleAddNew">Add new course</button>
        <p>List Courses: </p>
        <ul>
            <li v-for="(course, index) in courses" :key="course.index">
                {{ course.id }} -  {{ course.title }} 
                <button @click="handleDelete(index)">Delete</button>
            </li>
        </ul>
    </div>
</template>


<style scoped>

</style>
