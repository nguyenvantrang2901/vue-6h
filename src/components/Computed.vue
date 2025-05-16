<script setup>
import { computed, reactive, ref } from 'vue'

const books = reactive({
    name : "Book 1",
    chapter: []
});
const addChapters = () => {
    books.chapter.push("Chapter 1")
};

//Computed : Component chỉ render khi các phụ thuộc của nó bị thay đổi
const isPublish = computed(()=> {
    return books.chapter.length > 0 ? "Đã xuất bản" : "Chưa xuất bản";
});

const firstName = ref('Nguyen');
const lastName = ref('Van A');

const fullName = computed({
    //getter
    get() {
        return firstName.value + " " + lastName.value
    },
    set(newValue){
        [firstName.value, lastName.value] = newValue.split(',');
    }
})
const handleChangeName = ()=>{
    fullName.value = "Thi Thuy,Ha";
}

</script>

<template>
    <div>
        <h1>Computed</h1>
        <div>Tên sách : {{ books.name }}</div>
        <p>Danh sách chapter: </p>
        <ul v-for="ct in books.chapter">
            <li>{{ ct }}</li>
        </ul>
        <div>Trạng thái :  {{ isPublish  }}</div>
        <button @click="addChapters">Add chapter</button>
        <hr>
        <div>Full name : {{ firstName + " "+ lastName }}</div>
        <div>Update Name : {{ fullName }}</div>
        <button @click="handleChangeName">Change full name</button>
    </div>
</template>


<style scoped>

</style>
