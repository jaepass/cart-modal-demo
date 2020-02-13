<template>
  <div class="modal-backdrop">
    <div class="cart">
      <header class="cart-header">
        Shopping Cart
        <button type="button" class="btn-close" @click="close">X</button>
      </header>

      <div class="cart-body" v-for="item in items" :key="item.id">
        {{item.name}}
        {{ item.name }}
        <span class="text-center">{{ item.price.formatted_with_symbol }}</span>
        <!-- <button @click="$emit('remove-from-cart', item.id)"
        class="bg-transparent py-2 px-4 border hover:border-transparent rounded float-right">Remove</button>-->
      </div>
      <div class="cart-footer">
        <slot name="footer">
          Total:
          <button type="button" class="btn-close" @click="close">Close</button>
        </slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "cart-modal",

  props: ["items"],

  methods: {
    close() {
      this.$emit("close");
    }
  }
};
</script>

<style>
.modal-backdrop {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: rgba(0, 0, 0, 0.3);
  display: flex;
  justify-content: center;
  align-items: center;
}

.cart {
  border-radius: 11px;
  background: #ffffff;
  box-shadow: 2px 2px 20px 1px rgba(73, 73, 73, 0.493);
  overflow-x: auto;
  display: flex;
  flex-direction: column;
}

.cart-header,
.cart-footer {
  padding: 15px;
  display: flex;
}

.cart-header {
  border-bottom: 1px solid #eeeeee;
  color: black;
  justify-content: space-between;
}

.cart-footer {
  border-top: 1px solid #eeeeee;
  justify-content: flex-end;
}

.cart-body {
  position: relative;
  padding: 20px 10px;
}

.btn-close {
  border: none;
  font-size: 20px;
  padding: 20px;
  cursor: pointer;
  font-weight: bold;
  color: black;
  background: transparent;
}

.btn-green {
  color: white;
  background: black;
  border: 1px solid black;
  border-radius: 2px;
}
</style>