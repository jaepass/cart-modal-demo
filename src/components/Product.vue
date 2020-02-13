<template>
  <div class="card my-5" style="height:41rem;">
    <div class="card-body">
      <img :src="product.media.source" :alt="product.name" class="card-img-top">
      <h4 class="title text-center card-title display-5">{{product.name}}</h4>
      <p class="description text-center card-text display-5" v-html="product.description"></p>
      <p
        class="text-center text-muted card-subtitle display-5 price"
      >{{product.price.formatted_with_symbol}}</p>
      <button @click="$emit('add-to-cart', product)">Quick Add</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["product"]
};
</script>

<style>
.card h4 {
  padding-top: 20px;
  font-size: 20px;
  font-weight: 700;
  letter-spacing: 3.85px;
  line-height: 32px;
}

.card p {
  letter-spacing: 2.4px;
  padding-top: 5px;
}

button {
  background-color: transparent;
  text-decoration: underline;
  border: none;
  color: rgb(60, 60, 60);
  transition: all 0.3s ease-in-out;
}
button:hover {
  text-decoration: none;
  background-color: transparent;
  color: #DBA28B;
}

button img {
  padding-right: 7px;
}

@media only screen and (max-width: 400px) {
  .card {
    height: 48rem;
  }
}
</style>