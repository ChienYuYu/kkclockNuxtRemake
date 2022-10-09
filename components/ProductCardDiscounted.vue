<template>
  <section class="bg-white py-5">
    <div class="container">
      <h2 class="text-secondary mb-4">
        特價商品
        <hr>
      </h2>
      <div class="carousel-wrap mb-4">
        <!-- SlickCarousel標籤裡的v-if很重要!!!!! -->
        <SlickCarousel
          v-if="products.length > 0"
          v-bind="slickOptions"
        >
          <div
            v-for="item in products"
            :key="item.title"
            class="card border-0 p-3"
            style="width: 18rem;"
          >
            <div class="card-body p-0">
              <a href="#" class="text-decoration-none text-dark">
                <img :src="item.imageUrl" class="card-img-top">
                <h5 class="card-title my-3 px-2">
                  {{ item.title }}
                </h5>
                <div class="d-flex align-items-center justify-content-between">
                  <p class="text-secondary mb-0 px-2 ogPrice">
                    原價 NT${{ item.origin_price }}
                  </p>
                  <p class="text-myred mb-0 px-2">
                    NT${{ item.price }}
                  </p>
                </div>

                <button class="add-cart-btn btn py-1">
                  加入購物車
                </button>
              </a>
            </div>
          </div>
          <!-- ------------------------------- -->
          <!-- <div
            class="card border-0"
            style="width: 18rem;"
          >
            <div class="card-body p-1">
              <a href="#" class="text-decoration-none text-dark">
                <img src="../assets/img/sample_product02.jpg" class="card-img-top">
                <h5 class="card-title my-3 px-2">
                  Card title
                </h5>
                <div class="d-flex align-items-center justify-content-between">
                  <p class="text-secondary mb-0 px-2 ogPrice">
                    原價NT$xxx
                  </p>
                  <p class="text-myred mb-0 px-2">
                    NT$xxxx
                  </p>
                </div>
              </a>

              <button class="add-cart-btn btn py-1">
                加入購物車
              </button>
            </div>
          </div> -->
          <!-- ------------------------------- -->
        </slickcarousel>
      </div>
    </div>

    <div class="text-center">
      <router-link to="product_list/全部商品" class="btn text-white more-product-btn px-5">
        查看更多商品
        <i class="bi bi-caret-right-fill" />
      </router-link>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    products: {
      type: Array,
      required: true,
      default: function () {
        return ['hello world']
      }
    }
  },
  data () {
    return {
      slickOptions: {
        dots: false,
        autoplay: true,
        autoplaySpeed: 3000,
        infinite: true,
        arows: true,
        slidesToShow: 4,
        slidesToScroll: 1,
        // variableWidth: true,
        centerMode: true,
        responsive: [
          {
            breakpoint: 1024,
            settings: {
              slidesToShow: 2,
              slidesToScroll: 1
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
        ]
      }
    }
  },
  created () {
  },
  mounted () {
  }
}
</script>

<style  lang="scss">
.carousel-wrap {
  // border: 1px solid #fa0;
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
    @media (max-width: 575.98px) {
      display: none;
    }
  }

  .slick-prev::before {
    left: 0;
    transform: translate(-50%);

    @media (max-width: 575.98px) {
      transform: translate(0);
    }
  }

  .slick-next::before {
    right: 0;
    transform: translate(50%);

    @media (max-width: 575.98px) {
      transform: translate(0);
    }
  }

  // .slick-list {
  // }

  .card {
    transition: .3s;

    &:hover {
      transform: scale(102%);
    }

    .card-body {
      border: 1px solid #ddd;
      border-radius: .5rem;
    }
  }

  .add-cart-btn {
    width: 100%;
    margin-top: 1rem;
    padding: 1rem;
    border-radius: 0 0 .35rem .35rem;
    background: #ddd;
    color: #333;

    &:hover {
      background: #aaa;
      color: #fff;
    }
  }

}

.more-product-btn {
  background: #CF4900;

  &:hover {
    background: #da723a;
  }
}
</style>
