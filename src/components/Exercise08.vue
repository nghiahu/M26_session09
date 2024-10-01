<template>
  <div class="add-product-form">
    <h2>Thêm mới tài khoản</h2>
    <form @submit.prevent="handleSubmit">
      <div class="form-group">
        <label>Họ và tên</label>
        <input type="text" v-model="userInfo.userName" required/>
      </div>
      <div class="form-group">
        <label>Email</label>
        <input type="text" v-model="userInfo.userEmail" required/>
      </div>
      <div class="form-group">
        <label>Mật khẩu</label>
        <input type="password" v-model="userInfo.password" required/>
      </div>
      <div class="form-group">
        <label>Nhập lại mật khẩu</label>
        <input type="password" v-model="userInfo.rePassword" required/>
      </div>
      <button type="submit" class="submit-btn" @click="handleSubmit">Thêm mới</button>
    </form>
  </div>
</template>

<script setup>
import { reactive } from 'vue';
    const userInfo = reactive({
      userName: '',
      userEmail: '',
      password: "",
      rePassword: "",
    });

    const handleSubmit = () => {
      console.log(userInfo);
    };
</script>

<style scoped>
.add-product-form {
  width: 300px;
  margin: 0;
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 5px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

h2 {
  text-align: center;
  margin-bottom: 20px;
}

.form-group {
  margin-bottom: 15px;
}

label {
  display: block;
  margin-bottom: 5px;
  font-weight: bold;
}

input,
select {
  width: 100%;
  padding: 8px;
  margin-top: 5px;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 14px;
}

.submit-btn {
  width: 100%;
  padding: 10px;
  background-color: blue;
  color: white;
  font-size: 16px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.submit-btn:hover {
  background-color: darkblue;
}
</style>
