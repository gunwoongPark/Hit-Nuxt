<template>
  <div class="container">
    <h1 class="list-title">카트 페이지</h1>
    <div class="list-wrapper">
      <ul>
        <li
          v-for="cartItem in cartItems"
          :key="cartItem.id"
          class="list-item"
        >
          <img
            class="thumbnail"
            :src="cartItem.imageUrl"
            :alt="cartItem.name"
          >
          <div class="description">
            <p>{{cartItem.name}}</p>
            <span>{{cartItem.price}}</span>
          </div>

        </li>
      </ul>
    </div>
    <div class="extra-panel">
      <button>구매하기</button>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  async asyncData () {
    const response = await axios.get('http://localhost:3000/carts');
    const cartItems = response.data.map((item) => ({
      ...item,
      imageUrl: `${item.imageUrl}?random=${Math.random()}`
    }));
    return { cartItems }
  }
}
</script>

<style scoped>
.container {
  margin: 2rem 10rem;
}
.list-title {
  font-weight: 700;
  font-size: 1.4rem;
}
.list-wrapper {
  margin: 0.4rem 0;
}
.list-item {
  display: flex;
}
.thumbnail {
  width: 100px;
  height: 100px;
}
.description {
  padding: 2rem 1rem;
}
.extra-panel {
  text-align: right;
  padding: 0.2rem 0;
}
</style>