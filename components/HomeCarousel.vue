<template>
  <div class="home-carousel container">
    <b-carousel id="carousel-fade" :interval="3000" controls indicators>
      <div class="carousel-slogan">
        <h5 class="mb-2 slogan rounded-3">
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
      <b-carousel-slide>
        <template #img>
          <img class="d-block img-fluid w-100" src="../assets/img/banner04.jpg">
        </template>
      </b-carousel-slide>
      <b-carousel-slide>
        <template #img>
          <img class="d-block img-fluid w-100" src="../assets/img/banner07.jpg">
        </template>
      </b-carousel-slide>
      <b-carousel-slide>
        <template #img>
          <img class="d-block img-fluid w-100" src="../assets/img/banner08.jpg">
        </template>
      </b-carousel-slide>
    </b-carousel>
  </div>
</template>

<script>
export default {
  data () {
    return {
      slide: 0,
      sliding: null
    }
  },
  methods: {
    onSlideStart (slide) {
      this.sliding = true
    },
    onSlideEnd (slide) {
      this.sliding = false
    }
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
    bottom: 12%;
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
