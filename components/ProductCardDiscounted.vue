<template>
  <section class="bg-white py-5">
    <div class="container">
      <h2 class="text-secondary mb-4">
        特價商品
        <hr>
      </h2>
      <div class="carousel-wrap p-3">
        <SlickCarousel v-bind="slickOptions">
          <div class="card" style="width: 18rem;">
            <img src="../assets/img/sample_product02.jpg" class="card-img-top">
            <div class="card-body">
              <h5 class="card-title">
                Card title
              </h5>
              <p class="card-text">
                Some quick example text to build on the card title and make up the bulk of the card's content.
              </p>
              <a href="#" class="btn btn-primary">Go somewhere</a>
            </div>
          </div>
          <div class="card" style="width: 18rem;">
            <img
              src="../assets/img/sample_product02.jpg"
              class="card-img-top"
            >
            <div class="card-body">
              <h5 class="card-title">
                Card title
              </h5>
              <p class="card-text">
                Some quick example text to build on the card title and make up the bulk of the card's content.
              </p>
              <a href="#" class="btn btn-primary">Go somewhere</a>
            </div>
          </div>
          <div class="card" style="width: 18rem;">
            <img src="../assets/img/sample_product02.jpg" class="card-img-top">
            <div class="card-body">
              <h5 class="card-title">
                Card title
              </h5>
              <p class="card-text">
                Some quick example text to build on the card title and make up the bulk of the card's content.
              </p>
              <a href="#" class="btn btn-primary">Go somewhere</a>
            </div>
          </div>
          <div class="card" style="width: 18rem;">
            <img src="../assets/img/sample_product02.jpg" class="card-img-top">
            <div class="card-body">
              <h5 class="card-title">
                Card title
              </h5>
              <p class="card-text">
                Some quick example text to build on the card title and make up the bulk of the card's content.
              </p>
              <a href="#" class="btn btn-primary">Go somewhere</a>
            </div>
          </div>
          <div class="card" style="width: 18rem;">
            <img src="../assets/img/sample_product02.jpg" class="card-img-top">
            <div class="card-body">
              <h5 class="card-title">
                Card title
              </h5>
              <p class="card-text">
                Some quick example text to build on the card title and make up the bulk of the card's content.
              </p>
              <a href="#" class="btn btn-primary">Go somewhere</a>
            </div>
          </div>
          <div class="card" style="width: 18rem;">
            <img src="../assets/img/sample_product02.jpg" class="card-img-top">
            <div class="card-body">
              <h5 class="card-title">
                Card title
              </h5>
              <p class="card-text">
                Some quick example text to build on the card title and make up the bulk of the card's content.
              </p>
              <a href="#" class="btn btn-primary">Go somewhere</a>
            </div>
          </div>
        </slickcarousel>
      </div>
    </div>
    <div class="text-center">
      <router-link to="product_list/全部商品" class="btn btn-myorange2 text-white view-more px-5">
        查看更多商品<i class="bi bi-caret-right-fill" />
      </router-link>
    </div>
  </section>
</template>

<script>
export default {
  data () {
    return {
      slickOptions: {
        dots: false,
        autoplay: true,
        autoplaySpeed: 3000,
        infinite: true,
        arows: true,
        slidesToShow: 5,
        slidesToScroll: 1,
        responsive: [
          {
            breakpoint: 1024,
            settings: {
              slidesToShow: 3,
              slidesToScroll: 3
            }
          },
          {
            breakpoint: 600,
            settings: {
              slidesToShow: 2,
              slidesToScroll: 2
            }
          },
          {
            breakpoint: 480,
            settings: {
              slidesToShow: 1,
              slidesToScroll: 1,
              dots: false
            }
          }
          // You can unslick at a given breakpoint now by adding:
          // settings: "unslick"
          // instead of a settings object
        ]
      }
    }
  }
}
</script>

<style  lang="scss">
.carousel-wrap{
  position: relative;
  width: 100%;

.slick-prev {
  z-index: 99;
}
.slick-prev::before,
.slick-next::before {
  position: absolute;
  font-size: 40px;
  color: #009e95;
}
.slick-prev::before{
  left: 0;
  transform: translate(-50%);
  @media (max-width: 575.98px) {
    transform: translate(0);
  }
}
.slick-next::before{
  right: 0;
  transform: translate(50%);
  @media (max-width: 575.98px) {
    transform: translate(0);
  }
}

}
</style>
