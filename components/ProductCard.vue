<template>
  <div class="row row-cols-xl-5 row-cols-lg-3 row-cols-md-3 row-cols-2 g-3 ms-lg-2">
    <div v-for="item in category" :key="item.id" class="col">
      <div class="card product_card rounded-1 overflow-hidden h-100 border-0">
        <a href="#" class="text-decoration-none text-dark" @click.prevent="getProductData(item.id)">
          <img :src="item.imageUrl" class="card-img-top" alt="clock">
          <div class="card-body py-1">
            <h3 class="card-text fs-6">{{ item.title }}</h3>
            <div class="d-flex align-items-center justify-content-between">
              <p class="text-secondary mb-0 ogPrice">原價NT${{ item.origin_price }}</p>
              <p class="text-myred mb-0">NT${{ item.price }}</p>
            </div>
          </div>
        </a>
        <!-- <button
          type="button"
          :disabled="loadingItem == item.id"
          class="btn btn-outline-secondary m-2 py-1 mt-auto"
          @click="addCart(item.id)"
        >
          <div
            v-if="loadingItem == item.id"
            class="spinner-border spinner-border-sm text-mygrey"
            role="status"
          >
            <span class="visually-hidden">Loading...</span>
          </div>
          加入購物車
        </button> -->
        <button
          type="button"
          class="btn btn-outline-secondary m-2 py-1 mt-auto"
          @click="addCart(item.id)"
        >
          加入購物車
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['category']
}
</script>

<style lang="scss" scoped>
  .product_card {
  transition: 0.3s;
  &:hover {
    transform: scale(105%);
  }
  }
  .ogPrice {
    font-size: 12px;
    text-decoration: line-through;
  }
</style>
