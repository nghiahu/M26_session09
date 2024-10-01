<template>
  <div class="add-product-form">
    <h2>Đăng nhập</h2>
    <form @submit.prevent="handleSubmit">
        <label for="" class="error" v-if="errorLogin">Email hoặc mật khẩu không đúng</label>
      <div class="form-group">
        <label>Email</label>
        <input type="email" v-model="userLogin.userEmail" ref="inputName" />
        <label for="" class="error" v-if="errorEmail">Email không được để trống</label>
      </div>
      <div class="form-group">
        <label>Mật khẩu</label>
        <input type="password" v-model="userLogin.password" />
        <label for="" class="error" v-if="errorPass">password không được để trống</label>
      </div>
      <button type="submit" class="submit-btn">Đăng nhập</button>
    </form>
  </div>
</template>

<script setup>
import { reactive, ref } from 'vue';
const userLogin = reactive({
  userEmail: '',
  password: '',
});
const inputName = ref(null)
const errorEmail = ref(false);
const errorPass = ref(false);
const errorLogin = ref(false)
const localtUser = JSON.parse(localStorage.getItem("RegisterUser"))


const handleSubmit = () => {
  errorEmail.value = false;
  errorPass.value = false;
  errorLogin.value = false;

  if (userLogin.userEmail && userLogin.password) {
    if(userLogin.userEmail !== localtUser.userEmail ||  userLogin.password !== localtUser.password){
        errorLogin.value = true
        alert("Đăng nhập thất bại")
    }else{
        userLogin.userEmail = '';
        userLogin.password = '';
        inputName.value.focus();
        alert("Đăng nhập thành công")
    return 0;
    }
  }
  if (userLogin.userEmail === '') {
    errorEmail.value = true;
  }
  if (userLogin.password === '') {
    errorPass.value = true;
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
