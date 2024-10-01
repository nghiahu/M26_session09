<template>
  <div class="add-product-form">
    <h2>Đăng kí tài khoản</h2>
    <form @submit.prevent="handleSubmit">
      <div class="form-group">
        <label>Tên sinh viên</label>
        <input type="text" v-model="userRegiter.userName" ref="inputName" />
        <label for="" class="error" v-if="errorName">Tên sinh viên không được để trống</label>
      </div>
      <div class="form-group">
        <label>Email</label>
        <input type="text" v-model="userRegiter.userEmail" />
        <label for="" class="error" v-if="errorEmail">Email không được để trống</label>
      </div>
      <div class="form-group">
        <label>Mật khẩu</label>
        <input type="password" v-model="userRegiter.password" />
        <label for="" class="error" v-if="errorPass">Mật khẩu không được để trống</label>
      </div>
      <div class="form-group">
        <label>Số điện thoại</label>
        <input type="number" v-model="userRegiter.phoneNumber" />
        <label for="" class="error" v-if="errorPhone">Số điện thoại không được để trống</label>
      </div>
      <button type="submit" class="submit-btn">Đăng kí</button>
    </form>
  </div>
</template>

<script setup>
import { reactive, ref } from 'vue';
const userRegiter = reactive({
  userName: '',
  userEmail: '',
  password: '',
  phoneNumber: '',
});
const inputName = ref(null)
const errorName = ref(false);
const errorEmail = ref(false);
const errorPass = ref(false);
const errorPhone = ref(false);
const handleSubmit = () => {
  errorName.value = false;
  errorEmail.value = false;
  errorPass.value = false;
  errorPhone.value = false;

  if (userRegiter.userName && userRegiter.userEmail && userRegiter.password && userRegiter.phoneNumber) {
    localStorage.setItem('RegisterUser', JSON.stringify(userRegiter));

    userRegiter.userName = '';
    userRegiter.userEmail = '';
    userRegiter.password = '';
    userRegiter.phoneNumber = '';
    alert("Đăng ký thành công")
    inputName.value.focus();
    return 0;
  }

  if (userRegiter.userName === '') {
    errorName.value = true;
  }
  if (userRegiter.userEmail === '') {
    errorEmail.value = true;
  }
  if (userRegiter.password === '') {
    errorPass.value = true;
  }
  if (userRegiter.phoneNumber === '') {
    errorPhone.value = true;
  }
};
</script>

<style scoped>
.add-product-form {
  width: 400px;
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

.error {
  font-weight: 500;
  color: red;
}
</style>
