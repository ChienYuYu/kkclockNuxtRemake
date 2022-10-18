<template>
  <div class="wrapper">
    <HomeCarousel />
    <CouponBanner />
    <HotProduct />
    <MonthFeatured />
    <ProductCardDiscount :products="products" />
    <FrontFooter />
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data () {
    return {
      products: []
    }
  },
  mounted () {
    this.getDiscountedProduct()
  },
  methods: {
    // async getDiscountedProduct () {
    //   const apiUrl = 'https://vue3-course-api.hexschool.io/api/chienyu-api/products/all'
    //   const apiData = await this.$axios.$get(apiUrl)
    //   this.products = apiData.products.filter(item => item.category === '特價')
    // }
    getDiscountedProduct () {
      const apiUrl = 'https://vue3-course-api.hexschool.io/api/chienyu-api/products/all'
      this.$axios.$get(apiUrl)
        .then((res) => {
          this.products = res.products.filter(item => item.category === '特價')
        })
    }
  }
}
</script>

<style lang="scss">
</style>
