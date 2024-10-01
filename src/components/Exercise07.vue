<template>
  <div class="add-product-form">
    <h2>Thêm mới sản phẩm</h2>
    <form @submit.prevent="handleSubmit">
      <div class="form-group">
        <label>Mã sản phẩm</label>
        <input type="text" v-model="product.productCode" required/>
      </div>
      <div class="form-group">
        <label>Tên sản phẩm</label>
        <input type="text" v-model="product.productName" required/>
      </div>
      <div class="form-group">
        <label>Giá</label>
        <input type="number" v-model="product.price" required/>
      </div>
      <div class="form-group">
        <label>Số lượng</label>
        <input type="number" v-model="product.quantity" required/>
      </div>
      <button type="submit" class="submit-btn" @click="handleSubmit">Thêm mới</button>
    </form>
  </div>
</template>

<script setup>
import { reactive } from 'vue';
    const product = reactive({
      productCode: '',
      productName: '',
      price: 0,
      quantity: 0,
    });

    const handleSubmit = () => {
      console.log(product);
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
