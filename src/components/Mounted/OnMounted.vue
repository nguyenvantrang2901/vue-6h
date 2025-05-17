<script setup>
import { onMounted, onUnmounted, ref } from 'vue'
onMounted(()=> {
    console.log("Component đã được mount")
})

const interval = setInterval(()=> {
    console.log("App đang chạy......")
}, 1000)

onUnmounted(()=> {
    console.log("Component sắp bị unmount......")
    clearInterval(interval)
})
</script>
<template>
    <div class="container">
        <h1>Onmounted đc gọi khi component đã được gắn vào DOM : Sau khi render lần đầu tiên</h1>
        <h2>Thường được gọi để thực hiện</h2>
        <ul>
            <li>Gọi API lấy dữ liệu</li>
            <li>Thiết lập sự kiện : Event listener</li>
            <li>Khởi tạo thư viện bên thứ 3 : list, map</li>
        </ul>
        <hr>
        <h1>OnUnmounted đc gọi khi component sắp bị gỡ khỏi DOM</h1>
        <h2>Thường đc dùng để dọn dẹp</h2>
        <ul>
            <li>Hủy timer</li>
            <li>Dọn dẹp bộ nhớ</li>
            <li>Gỡ Event listener</li>
        </ul>
        <a href="https://www.youtube.com/">Click me</a>
        <button @click="alert('Click 123')">Click meee</button>
    </div>
</template>


<style scoped>
.container {
    width: 100%;
}
</style>
