<template>
  <div class="wrapper pt-5">
    <section class="py-5">
      <div class="container">
        <h2 class="text-center d-lg-none">
          產品項目
        </h2>
        <div class="row">
          <div class="col-lg-2 pt-md-5">
            <ul
              class="list-unstyled d-flex flex-lg-column text-nowrap overflow-auto product-list-group"
            >
              <li>
                <a
                  href="#"
                  class="list-item px-4 px-lg-5 py-2 d-block
                text-decoration-none text-center border-top"
                  :class="{ 'list-active': category === '全部商品' }"
                  @click.prevent="getCategory('全部商品')"
                >全部商品
                </a>
              </li>
              <li>
                <a
                  href="#"
                  class="list-item px-4 px-lg-5 py-2 d-block text-decoration-none text-center"
                  :class="{ 'list-active': category === '特價' }"
                  @click.prevent="getCategory('特價')"
                >特價
                </a>
              </li>
              <li>
                <a
                  href="#"
                  class="list-item px-4 px-lg-5 py-2 d-block text-decoration-none text-center"
                  :class="{ 'list-active': category === '流行炫彩' }"
                  @click.prevent="getCategory('流行炫彩')"
                >流行炫彩
                </a>
              </li>
              <li>
                <a
                  href="#"
                  class="list-item px-4 px-lg-5 py-2 d-block text-decoration-none text-center"
                  :class="{ 'list-active': category === '超級號碼' }"
                  @click.prevent="getCategory('超級號碼')"
                >超級號碼
                </a>
              </li>
              <li>
                <a
                  href="#"
                  class="list-item px-4 px-lg-5 py-2 d-block text-decoration-none text-center"
                  :class="{ 'list-active': category === '四數大字' }"
                  @click.prevent="getCategory('四數大字')"
                >四數大字
                </a>
              </li>
              <li>
                <a
                  href="#"
                  class="list-item px-4 px-lg-5 py-2 d-block text-decoration-none text-center"
                  :class="{ 'list-active': category === '經典鬧鐘' }"
                  @click.prevent="getCategory('經典鬧鐘')"
                >經典鬧鐘
                </a>
              </li>
              <li>
                <a
                  href="#"
                  class="list-item px-4 px-lg-5 py-2 d-block text-decoration-none text-center"
                  :class="{ 'list-active': category === '其他' }"
                  @click.prevent="getCategory('其他')"
                >其他
                </a>
              </li>
            </ul>
          </div>
          <div class="col-lg-10">
            <h3>
              {{ category }}
              <hr class="ms-lg-2">
            </h3>
            <ProductCard :category="filterCategory" />
          </div>
        </div>
      </div>
    </section>
    <FrontFooter />
  </div>
</template>

<script>
export default {
  data () {
    return {
      products: [],
      category: ''
    }
  },
  computed: {
    filterCategory () {
      // return this.products.filter(item => item.category === this.category)
      if (this.category === '全部商品') {
        return this.products
      }
      return this.products.filter(item => item.category === this.category)
    }
  },
  created () {
    this.category = this.$route.params.category
    this.getProduct()
  },
  methods: {
    getProduct () {
      const apiUrl = 'https://vue3-course-api.hexschool.io/api/chienyu-api/products/all'
      this.$axios.$get(apiUrl)
        .then((res) => {
          this.products = res.products
        })
    },
    getCategory (i) {
      this.category = i
    }
  }
}
</script>

<style lang="scss" scoped>
  .wrapper{
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    // overflow: auto;
  }
  .list-item {
  color: #777;
  border-bottom: 1px solid #dee2e6;
  &:hover {
    background: #ddd;
    color: #fff;
  }
  }
  .list-active {
    background: #ccc;
    color: #fff;
  }
  .product-list-group {
    @media (min-width: 992px) {
      position: fixed;
    }
  }
</style>
