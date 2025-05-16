<script setup>
import { ref } from 'vue'
const isLogin = ref(true)
const handleChangeLogin = () => {
    isLogin.value = !isLogin.value
}

const userStatus = ref("online")

const handleChangeStatus = () => {
    if(userStatus.value == "") {
        userStatus.value = "online"
    }else if(userStatus.value == "online"){
        userStatus.value = "away"
    }else if(userStatus.value == "away"){
        userStatus.value = "busy"
    }else if(userStatus.value == "busy"){
        userStatus.value = "online"
    }
}

const isDisable = ref(true)
const handleDisable = () => {
    isDisable.value = !isDisable.value
}
</script>
<template>
    <div>
        <div>
            <h1 v-if="isLogin">Login</h1>
            <h2 v-else>Logout</h2>
            <button @click="handleChangeLogin">{{ isLogin ? "Muốn Đăng xuất ?" : "Quay lại Đăng nhập" }}</button>
        </div>

        <div>
            <button @click="handleChangeStatus">Thay đổi trạng thái</button>
            <h1 v-if="userStatus==='online'">Đang Online</h1>
            <h1 v-else-if="userStatus==='away'">Đang Họp</h1>
            <h1 v-else-if="userStatus==='busy'">Đang Bận</h1>
            <h1 v-else>Không xác định</h1>
        </div>
        
        <div>
            <button @click="handleDisable">
                {{ isDisable ? "Disable message" :"Show message" }}
            </button>
            <h1 v-show="isDisable">Show message</h1>
        </div>
    </div>
</template>


<style scoped>

</style>
