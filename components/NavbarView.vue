<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-light bg-light p-3 shadow-sm fixed-top">
      <div class="container">
        <h1 class="m-0">
          <router-link to="/" class="navbar-brand p-0 d-block">
            <img src="../assets/img/fakeLogo05.png" alt="logo" height="40">
          </router-link>
        </h1>
        <button
          ref="navbarBtn"
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNav"
          aria-controls="navbarNav"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon" />
        </button>
        <div id="navbarNav" ref="navbar" class="collapse navbar-collapse justify-content-end">
          <ul class="navbar-nav">
            <li class="nav-item">
              <router-link
                to="/"
                class="nav-link"
              >
                首頁
              </router-link>
            </li>
            <li class="nav-item">
              <router-link
                to="/ProductList/全部商品"
                class="nav-link"
              >
                購物
              </router-link>
            </li>
            <li class="nav-item">
              <router-link
                to="/order_search"
                class="nav-link"
              >
                訂單查詢
              </router-link>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">
                購物車
                <i class="bi bi-cart-fill position-relative">
                  <span
                    class="position-absolute top-0 start-100
                  translate-middle badge badge_txt rounded-circle bg-myorange"
                  />
                </i>
              </a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  data () {
    return {
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
