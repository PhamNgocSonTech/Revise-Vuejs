<script setup>
import { ref } from 'vue';

const isLogged = ref(true)

const toggleLogin = () => {
  isLogged.value = !isLogged.value
}

const isVisible = ref(true)

const toggleVisible = () => {
  isVisible.value = !isVisible.value
}


const userStatus = ref('online')

const changeStatus = () => {
  if (userStatus.value === 'online') userStatus.value = 'away'
  else if (userStatus.value === 'away') userStatus.value = 'busy'
  else if (userStatus.value === 'busy') userStatus.value = 'online'
  else userStatus.value = 'Invalid Status Account'
}
</script>


<template>
  <div>
    <h1 v-if="isLogged">Bạn đã đăng nhập</h1>
    <h1 v-else>Bạn chưa đăng nhập</h1>
    <button @click="toggleLogin">{{ isLogged ? 'Logout' : 'Login' }}</button>
    <br>
    <h1 v-if="userStatus === 'online'">Đang online</h1>
    <h1 v-else-if="userStatus === 'away'">Đang vắng mặt</h1>
    <h1 v-else-if="userStatus === 'busy'">Đang bận</h1>
    <h1 v-else>Không rõ trạng thái</h1>
    <button @click="changeStatus">Thay đổi trạng thái (trạng thái hiện tại: {{ userStatus }})</button>
    <br>
    <h1 v-show="isVisible">HIỂN THỊ hoặc ẨN ĐI</h1>
    <button @click="toggleVisible">{{ isVisible ? 'Hide' : 'Show' }}</button>
  </div>

</template>

<style></style>