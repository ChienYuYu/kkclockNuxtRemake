<template>
  <div
    id="carouselExampleCaptions"
    ref="carousel"
    class="carousel slide carousel-fade container mb-5"
    data-bs-ride="carousel"
  >
    <div class="home-carousel carousel-inner rounded-3">
      <div class="carousel-slogan">
        <h5 class="mb-0 slogan rounded-3">
          kkClock<br>鐘的專家 最專業時鐘專賣<br>
        </h5>
        <button class="btn go-buy">
            &ensp;
          <i class="bi bi-cart me-1" />
          <span>來去逛逛</span>
          <i class="bi bi-caret-right" />
          <i class="bi bi-caret-right" />
        </button>
      </div>
      <router-link to="product_list/全部商品" class="carousel-item active">
        <img src="../assets/img/banner04.jpg" class="banner d-block w-100" alt="banner1">
      </router-link>
      <router-link to="product_list/全部商品" class="carousel-item">
        <img src="../assets/img/banner07.jpg" class="banner d-block w-100" alt="banner2">
      </router-link>
      <router-link to="product_list/全部商品" class="carousel-item">
        <img src="../assets/img/banner08.jpg" class="banner d-block w-100" alt="banner3">
      </router-link>
    </div>
    <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide="prev">
      <span class="carousel-control-prev-icon" aria-hidden="true" />
      <span class="visually-hidden">Previous</span>
    </button>
    <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide="next">
      <span class="carousel-control-next-icon" aria-hidden="true" />
      <span class="visually-hidden">Next</span>
    </button>
  </div>
</template>

<script>
export default {
  data () {
    return {
    }
  },
  methods: {
  }
}
</script>

<style lang="scss" scoped>
.home-carousel {
  position: relative;
  margin-top: 72px;
  padding-top: 50px;

  .carousel-slogan {
    position: absolute;
    bottom: 10%;
    left: 0;
    right: 0;
    z-index: 99;
    background: #dddddd30;
    text-align: center;
    padding: .75rem 0;
    backdrop-filter: blur(5px);
    border-radius: 0 0 .5rem .5rem;

    .slogan {
      font-size: 15px;
      color: #111;
      letter-spacing: 0.3rem;
      line-height: 1.5;
    }

    .go-buy {
      background: #CF4900;
      color: #fff;

      &:hover {
        background: #da723a;
      }
    }
  }
  img {
    height: 600px;
    object-fit: cover;
    border-radius: .5rem;
    overflow: hidden;
  }
}
</style>
