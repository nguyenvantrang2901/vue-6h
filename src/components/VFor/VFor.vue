<script setup>
import { computed, ref } from 'vue'
const users = ref([
    {name : "Hoang Nam", age: 18, email: "nam@gmail.com"},
    {name : "Dinh Khanh", age: 21, email: "khanh@gmail.com"},
    {name : "Minh Trang", age: 28, email: "trang@gmail.com"},
    {name : "Quan Su", age: 30, email: "quansu@gmail.com"},
])

const numbers = ref([1,2,3,4,5,6,7,8])
const evenNumber = computed(()=>{
    return numbers.value.filter(n=>n%2==0)
})

const sets = ref([
  [1, 2, 3, 4, 5],
  [6, 7, 8, 9, 10]
])
const even = (nums)=> {
    return nums.filter((num) => num%2 == 1)
}
</script>
<template>
    <div>
        <h1>V-For</h1>
        <ul v-for="user in users">
            <li :key="item">{{ user.name }} - {{ user.age }} - {{ user.email }}</li>
        </ul>

        <p>Danh sách dãy số:
            <template v-for="num in numbers">{{ num }}</template>
        </p>
        <p>Số chẵn : 
            <ul>
                <li v-for="n in evenNumber"> {{ n }} </li>
            </ul>
        </p>
        <p>Dùng vòng for lồng nhau để tìm các số lẻ :</p>
        <ul v-for="nums in sets">
            <li v-for="n in even(nums)"> {{ n }}</li>
        </ul>
    </div>
</template>

<style scoped>

</style>
