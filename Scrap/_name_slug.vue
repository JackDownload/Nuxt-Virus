
<template>
  <!-- eslint-disable vue/no-v-html -->
  <section class="container">
    <nav
      class="container mb-n4 p-0 desktop-only"
      aria-label="breadcrumb"
    >
      <ol class="breadcrumb">
        <li class="breadcrumb-item">
          <nuxt-link to="/">
            Головна
          </nuxt-link>
        </li>
        <li class="breadcrumb-item">
          <nuxt-link to="/mahazyn">
            магазин
          </nuxt-link>
        </li>
        <li
          class="breadcrumb-item active"
          aria-current="page"
        >
          {{ product.name }}
        </li>
      </ol>
    </nav>
    <div class="container pt-5">
      <div class="row mx-auto">
        <div class="col-lg-1 mb-3 desktop-only">
          <nuxt-link to="/mahazyn">
            <img
              src="~assets/img/chevron-right.png"
              alt="chevron-right"
            >
          </nuxt-link>
        </div>
        <div class="col-12 col-xl-10">
          <div class="row">
            <div class="main-image col-4 p-0">
              <div
                v-if="product.galleryToggle === false || product.galleryToggle === null"
                class="image-showcase col-12 text-center p-0"
              >
                <img
                  :src="
                    `${imageApiUrl}&src=${product.Image.path}&w=200&h=200&f[brighten]=0&o=true`
                  "
                  class="mx-auto img-fluid"
                  :alt="product.name"
                >
              </div>
              <div
                v-if="product.galleryToggle === true"
                class="image-showcase col-12 text-center p-0"
              >
                <client-only>
                  <carousel
                    :autoplay="false"
                    :nav="false"
                    :items="1"
                    :lazy-load="true"
                    :v-lazy="true"
                    :loop="true"
                    :mouse-drag="true"
                    :touch-drag="true"
                  >
                    <img
                      :src="
                        `${imageApiUrl}&src=${product.Gallery[0].path}&w=200&h=200&f[brighten]=0&o=true`
                      "
                      class="mx-auto img-fluid"
                      :alt="product.Gallery[0].meta.title"
                    >
                    <img
                      :src="
                        `${imageApiUrl}&src=${product.Gallery[1].path}&w=200&h=200&f[brighten]=0&o=true`
                      "
                      class="mx-auto img-fluid"
                      :alt="product.Gallery[1].meta.title"
                    >
                    <img
                      :src="
                        `${imageApiUrl}&src=${product.Gallery[2].path}&w=200&h=200&f[brighten]=0&o=true`
                      "
                      class="mx-auto img-fluid"
                      :alt="product.Gallery[2].meta.title"
                    >
                  </carousel>
                </client-only>
              </div>
              <style>
                .small-more-images {
                margin-top: -20px;
                }

                .main-image .owl-theme .owl-dots .owl-dot span {
                width: 73px !important;
                height: 73px !important;
                margin-bottom: -60px;
                background-color: transparent;

                margin-right: 12.5px;
                margin-left: 12.5px;
                display: abslolute;
                }

                .main-image .owl-theme .owl-dots .owl-dot:hover span {
                background-color: transparent;
                }

                .main-image .owl-theme .owl-dots .owl-dot.active span {
                background-color: transparent;
                }

                .main-image .owl-theme .owl-dots .owl-dot.active:hover span {
                background-color: transparent;
                }

                @media only screen and (min-width: 992px) and (max-width: 1199px) {
                .main-image .owl-theme .owl-dots .owl-dot span {
                width: 73px !important;
                height: 73px !important;
                margin-bottom: -55px;
                background-color: transparent;

                margin-right: 12px;
                margin-left: 12px;
                display: abslolute;
                }
                }

                @media only screen and (min-width: 768px) and (max-width: 992px) {
                .main-image .owl-theme .owl-dots .owl-dot span {
                width: 60px !important;
                height: 60px !important;
                margin-bottom: -48px;
                background-color: transparent;

                margin-right: 5.5px;
                margin-left: 5.6px;
                display: abslolute;
                }
                }

                @media only screen and (min-width: 500px) and (max-width: 767.9px) {
                .main-image .owl-theme .owl-dots .owl-dot span {
                width: 10px !important;
                height: 10px !important;
                margin-top: -25px;
                background-color: grey;

                margin-right: 5px;
                margin-left: 5px;
                }

                .main-image .owl-theme .owl-dots .owl-dot:hover span {
                background-color: #d41f26;
                }

                .main-image .owl-theme .owl-dots {
                margin-bottom: -30px;
                }

                .main-image .owl-theme .owl-dots .owl-dot.active span {
                background-color: #d41f26;
                }

                .main-image .owl-theme .owl-dots .owl-dot.active:hover span {
                background-color: red;
                }

                .small-more-images {
                margin-top: 0px;
                display: none;
                }
                }

                @media only screen and (max-width: 499.9px) {
                .main-image .owl-theme .owl-dots .owl-dot span {
                width: 5px !important;
                height: 5px !important;
                margin-top: -29px;
                background-color: grey;

                margin-right: 5px;
                margin-left: 5px;
                }

                .main-image .owl-theme .owl-dots .owl-dot:hover span {
                background-color: #d41f26;
                }

                .main-image .owl-theme .owl-dots {
                margin-bottom: -30px;
                }

                .main-image .owl-theme .owl-dots .owl-dot.active span {
                background-color: #d41f26;
                }

                .main-image .owl-theme .owl-dots .owl-dot.active:hover span {
                background-color: red;
                }

                .small-more-images {
                margin-top: 0px;
                display: none;
                }
                }
              </style>
              <div
                v-if="product.galleryToggle === true "
                class="small-more-images"
              >
                <div class="row mx-auto">
                  <img
                    :src="
                      `${imageApiUrl}&src=${product.Gallery[0].path}&w=200&h=200&f[brighten]=0&o=true`
                    "
                    :alt="product.Gallery[0].meta.title"
                    :title="product.Gallery[0].meta.title"
                    class="col-4 mx-auto mt-n4 more-images"
                  >
                  <img
                    :src="
                      `${imageApiUrl}&src=${product.Gallery[1].path}&w=200&h=200&f[brighten]=0&o=true`
                    "
                    :alt="product.Gallery[1].meta.title"
                    :title="product.Gallery[1].meta.title"
                    class="col-4 mx-auto mt-n4 more-images"
                  >
                  <img
                    :src="
                      `${imageApiUrl}&src=${product.Gallery[2].path}&w=200&h=200&f[brighten]=0&o=true`
                    "
                    :alt="product.Gallery[2].meta.title"
                    :title="product.Gallery[2].meta.title"
                    class="col-4 mx-auto mt-n4 more-images"
                  >
                </div>
              </div>
            </div>

            <div class="main-text col-8 text-center text-md-left">
              <h1 class="details-page-header">
                {{ product.name }}
              </h1>
              <style>
                li {
                margin-left: 20px;
                }
              </style>
              <section class="my-lg-5 desktop-tablet-only markdown">
                <div
                  class="mb-2"
                  v-html="(product.Description + '\n' + '<strong>Об\'єм: </strong>&nbsp;' + product.volume)"
                />
                <div class="mb-2">
                  <strong>Бренд: </strong>{{ `${product.brand}` }}
                </div>

                <ul>
                  <strong>Категорія(й):</strong>
                  <li
                    v-for="(category, index) in product.category"
                    :key="category[index]"
                    class="text-capitalize"
                  >
                    {{ category }}
                  </li>
                </ul>
                <ul>
                  <strong>Підкатегорія(й):</strong>
                  <li
                    v-for="(subcategory, index) in product.subCategories"
                    :key="subcategory[index]"
                    class="text-capitalize"
                  >
                    {{ subcategory | capitalize }}
                  </li>
                </ul>
              </section>

              <div class="row">
                <div class="col-6 text-center text-md-left my-auto pr-0">
                  <small class="mb-2 detail-discount-cost">
                    <s v-if="product.discountPrice>0">{{ product.discountPrice | currency({symbol: 'грн', thousandsSeparator: ',', fractionCount: '0', fractionSeparator: '.', symbolPosition: 'back', symbolSpacing: true}) }}</s>

                  </small>
                  <p
                    id="store-item-price"
                    class="detail-cost"
                  >
                    {{ product.Price | currency({symbol: '', thousandsSeparator: ',', fractionCount: '0', fractionSeparator: '.', symbolPosition: 'back', symbolSpacing: true}) }}

                    <span>ГРН</span>
                  </p>
                </div>
                <div class="col-6 text-center mt-lg-n3 p-0">
                  <small
                    v-show="product.Stock === true"
                    class="inStock"
                  >В наявності</small>
                  <small
                    v-show="product.Stock === false"
                    class="notInStock"
                  >Не в наявності</small>
                  <br>
                  <button
                    v-show="product.Stock === true"
                    :disableda="product.Stock === false"
                    class="btn add-to-cart snipcart-add-item card-footer-item"
                    @click.prevent="addToCart(product._id)"
                  >
                    Додати до корзини +
                  </button>
                  <button
                    v-show="product.Stock === false"
                    class="btn add-to-cart card-footer-item"
                    style="cursor: not-allowed;"
                  >
                    Додати до корзини +
                  </button>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="col-lg-1 mt-2 desktop-only">
          <div class="cart-icon text-center mx-auto">
            <div class="cart-icon">
              <b-button
                v-b-modal.modal-xl-mobile
                variant="link"
                @click="mobileModalShow = !mobileModalShow"
              >
                <img
                  id="cart"
                  src="~/assets/img/cart.png"
                  alt="Cart icon"
                >
              </b-button>
              <div
                id="show-total"
                class="text-center justify-center"
              >
                <span
                  id="item-count"
                  class="text-center m-auto p-0 snipcart-total-items"
                >{{ cartSize }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
      <section class="sm-xsm-xxsm-only">
        <div
          class="mt-3 "
          v-html="(product.Description + '\n' + '<strong>Об\'єм: </strong>&nbsp;' + product.volume)"
        />
        <div class="mb-2">
          <strong>Бренд: </strong>{{ `${product.brand}` }}
        </div>

        <ul>
          <strong>Категорія(й):</strong>
          <li
            v-for="(category, index) in product.category"
            :key="category[index]"
            class="text-capitalize"
          >
            {{ category }}
          </li>
        </ul>
        <ul>
          <strong>Підкатегорія(й):</strong>
          <li
            v-for="(subcategory, index) in product.subCategories"
            :key="subcategory[index]"
            class="text-capitalize"
          >
            {{ subcategory | capitalize }}
          </li>
        </ul>
      </section>

      <hr style="border: 1px solid #C4C4C4; margin: 40px 0; width: 100%;">

      <h2 class="text-center my-2 relatedProducts">
        Схожі товари та пропозиції
      </h2>

      <client-only>
        <carousel
          :autoplay="true"
          :nav="false"
          :items="4"
          :lazy-load="true"
          :v-lazy="true"
          :loop="true"
          :mouse-drag="true"
          :touch-drag="true"
          :autoplay-hover-pause="true"
          :responsive="{
            0: { items: 1, nav: false },
            350: { items: 2, nav: false },
            767: { items: 2, nav: false },
            992: { items: 3, nav: false },
            1200: { items: 4, nav: false }
          }"
        >
          <card
            v-for="product in relatedProducts"
            :key="product._id"
            class="mb-5 mx-auto"
            :name="`${product.name}`"
            :summary="product.Overview"
            :price="product.Price"
            :discount-price="product.discountPrice"
            :image="
              `${imageApiUrl}&src=${product.Image.path}&w=190&h=190&f[brighten]=0&o=true`
            "
            :link="{ name: 'mahazyn-name_slug', params: {name_slug: product.name_slug, _id: product._id } }"
            :stock="product.Stock"
            :sales="product.Sales"
            :brand="product.brand"
            :type="product.type"
          />
        </carousel>
      </client-only>
    </div>
  </section>
</template>

<script>
import axios from 'axios'
import { mapState, mapGetters } from 'vuex'

export default {
  name: 'SingleProduct',
  filters: {
    capitalize: (item) => {
      return item.toLowerCase()
    }
  },
  async asyncData ({ app, params, error, payload }) {
    if (payload) {
      return { product: payload }
    }
    const product = await axios.post(
      'https://admin.virus.te.ua/api/collections/get/Product?token=9fc49d5af4dda3c961d71b489540a4&rspc=1',
      JSON.stringify({
        filter: { Published: true, name_slug: params.name_slug },
        sort: { _created: -1 },
        populate: 1
      }),
      {
        headers: { 'Content-Type': 'application/json' }
      }
    )
    const products = await axios.get(
      'https://admin.virus.te.ua/api/collections/get/Product?token=9fc49d5af4dda3c961d71b489540a4&rspc=1&limit=12',
      JSON.stringify({
        filter: { Published: true },
        limit: 4,
        sort: { _created: -1 },
        populate: 1
      }),
      {
        headers: { 'Content-Type': 'application/json' }
      }
    )

    // if (!product.data.entries || !products.data.entries) {
    //   return error({ message: '404 Page not found', statusCode: 404 })
    // }

    return {
      product: product.data.entries[0],
      relatedProducts: products.data.entries.filter(el => el.category.includes(product.data.entries[0].category[0]))
    }
  },

  data () {
    return {
      mobileModalShow: false,
      imageApiUrl: process.env.IMAGE_LINK_DYNAMIC
    }
  },
  computed: {
    ...mapState(['cart']),
    ...mapGetters(['cartSize', 'cartTotalAmount'])
  },

  methods: {
    addToCart (id) {
      this.$store.dispatch('addToCart', id)
    }

  },

  head () {
    return {
      title: this.product.name,
      titleTemplate: '%s! - Virus',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: this.product.Description
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.sm-xsm-xxsm-only {
  display: none;
}

h1.details-page-header {
  font-family: "Roboto", sans-serif;
  font-style: normal;
  font-weight: bold;
  font-size: 40px;
  line-height: normal;
  margin-top: 10px;

  color: #000000;
}

.cart-icon {
  #show-total {
    width: 35px;
    height: 35px;

    background-color: $redColor;
    border-radius: 50%;
    -webkit-border-radius: 50%;
    -moz-border-radius: 50%;
    -ms-border-radius: 50%;
    -o-border-radius: 50%;

    margin: 17px auto 0;

    justify-content: center;
    margin: auto;

    span {
      font-family: $mainFont;
      font-style: normal;
      font-weight: bold;
      font-size: 18px;
      line-height: 35px;

      color: $lightColor;
      text-align: center;
      margin: auto;
    }
  }
}

.image-showcase {
  margin-top: 10px;
  margin-bottom: 22px;
}

.image-showcase img {
  box-shadow: 0px 5px 10px rgba(0, 0, 0, 0.35);
  border-radius: 20px;
  width: 100%;
  max-width: 200px;
  height: 100%;
  max-height: 200px;
  margin: 10px;
}

.more-images {
  max-height: 73px;
  min-height: 73px;
  height: 100%;
  max-width: 73px;
  min-width: 73px;
  margin-top: 4px;
  width: 100%;
  object-fit: scale-down;
  object-position: center;
  background: url("~assets/img/86.jpg");
  box-shadow: 0px 5px 10px rgba(0, 0, 0, 0.35);
  border-radius: 10px;
}

.detail-cost {
  font-family: "Roboto", sans-serif;
  font-style: normal;
  font-weight: bold;
  font-size: 40px;
  line-height: 38px;
  letter-spacing: -0.05em;

  color: #8b8b8b;
}

.detail-discount-cost {
  font-family: "Roboto", sans-serif;
  font-style: normal;
  font-weight: bold;
  font-size: 18px;
  line-height: normal;
  text-align: center;
  text-decoration-line: line-through;

  color: #d7000b;
}

.inStock {
  font-family: "Roboto Condensed";
  font-style: normal;
  font-weight: normal;
  font-size: 18px;
  line-height: normal;
  text-align: center;

  color: #239a0f;
}

.notInStock {
  font-family: "Roboto Condensed";
  font-style: normal;
  font-weight: normal;
  font-size: 18px;
  line-height: normal;
  text-align: center;

  color: $redColor;
}

.btn.add-to-cart {
  padding: 12px 36px;
  background: #d41f26;
  border-radius: 50px;
  font-family: "Roboto Condensed", sans-serif;
  font-style: normal;
  font-weight: bold;
  font-size: 17px;
  line-height: normal;
  text-align: center;
  color: #ffffff;
  text-decoration: none;
  @include easeInOut;
  box-shadow: 0px 3px 10px rgba(0, 0, 0, 0.35);

  margin-top: 5px;
}

.btn:hover {
  color: #d41f26;
  background: #ffffff;
  transform: scale(1.1);
  -webkit-transform: scale(1.1);
  -moz-transform: scale(1.1);
  -ms-transform: scale(1.1);
  -o-transform: scale(1.1);
}

.relatedProducts {
  font-family: $mainFont;
  font-style: normal;
  font-weight: normal;
  font-size: 20px;
  line-height: 23px;

  align-items: center;

  color: #8b8b8b;
}

@include mediaMenu {
  .desktop-only,
  .sm-xsm-xxsm-only {
    display: none;
  }

  .mobile-only {
    display: block;
  }

  .more-images {
    max-height: 63px;
    min-height: 63px;
    height: 100%;
    max-width: 63px;
    min-width: 63px;
    margin-top: 4px;
    width: 100%;
    object-fit: scale-down;
    object-position: center;
    background: url("~assets/img/86.jpg");
    box-shadow: 0px 5px 10px rgba(0, 0, 0, 0.35);
    border-radius: 10px;
  }
}

@include mediaMd {
  .desktop-only,
  .desktop-tablet-only {
    display: none;
  }

  .sm-xsm-xxsm-only {
    display: block;
  }

  .mobile-only {
    display: block;
  }

  .image-showcase img {
    box-shadow: 0px 5px 10px rgba(0, 0, 0, 0.35);
    border-radius: 20px;
    width: 100%;
    max-width: 130px;
    height: 100%;
    max-height: 130px;
    margin: 15px;
  }

  .more-images {
    max-height: 40px;
    min-height: 40px;
    height: 100%;
    max-width: 40px;
    min-width: 40px;
    margin-top: 4px;
    width: 100%;
    object-fit: scale-down;
    object-position: center;

    box-shadow: 0px 5px 10px rgba(0, 0, 0, 0.35);
    border-radius: 10px;
  }

  .detail-cost {
    font-family: "Roboto", sans-serif;
    font-style: normal;
    font-weight: bold;
    font-size: 24px;
    line-height: 93.75%;
    letter-spacing: -0.05em;

    color: #8b8b8b;
    margin-bottom: -10px;
  }

  .detail-discount-cost {
    font-family: "Roboto", sans-serif;
    font-style: normal;
    font-weight: bold;
    font-size: 14px;
    line-height: 16px;
    text-align: center;
    text-decoration-line: line-through;

    color: #d7000b;
    padding-top: 25px;
  }

  .inStock {
    font-family: "Roboto Condensed";
    font-style: normal;
    font-weight: normal;
    font-size: 14px;
    line-height: 16px;
    text-align: center;

    color: #239a0f;
  }

  .notInStock {
    font-family: "Roboto Condensed";
    font-style: normal;
    font-weight: normal;
    font-size: 12px;
    line-height: 14px;
    text-align: center;

    color: $redColor;
  }

  .btn.add-to-cart {
    padding: 14px 8px;
    background: #d41f26;
    border-radius: 50px;
    font-family: "Roboto Condensed", sans-serif;
    font-style: normal;
    font-weight: bold;
    font-size: 14px;
    line-height: 16px;
    text-align: center;
    color: #ffffff;
    text-decoration: none;
    @include easeInOut;
    box-shadow: 0px 3px 10px rgba(0, 0, 0, 0.35);

    margin-top: 0px;
  }
}

@include mediaSm {
  .desktop-only {
    display: none;
  }

  .mobile-only,
  .sm-xsm-xxsm-only {
    display: block;
  }

  h1.details-page-header {
    font-family: "Roboto", sans-serif;
    font-style: normal;
    font-weight: bold;
    font-size: 18px;
    line-height: 21px;
    margin-top: 0px;

    color: #000000;
  }

  .image-showcase {
    margin-top: 0px;
    margin-bottom: 0px;
  }

  .image-showcase img {
    min-height: 100px;
    max-height: 100px;
    height: 100%;
    min-width: 100px;
    max-width: 100px;
    width: 100%;
    box-shadow: 0px 3px 10px rgba(0, 0, 0, 0.25);
    border-radius: 5px;
  }

  .markdown {
    font-family: $mainFont;
    font-style: normal;
    font-weight: normal;
    font-size: 12px;
    line-height: 14px;

    color: #8b8b8b;
  }

  .more-images {
    display: none;
  }

  .detail-cost {
    font-family: "Roboto", sans-serif;
    font-style: normal;
    font-weight: bold;
    font-size: 18px;
    line-height: 93.75%;
    letter-spacing: -0.05em;

    color: #8b8b8b;
    margin-bottom: -10px;
  }

  .detail-discount-cost {
    font-family: "Roboto", sans-serif;
    font-style: normal;
    font-weight: bold;
    font-size: 12px;
    line-height: 14px;
    text-align: center;
    text-decoration-line: line-through;

    color: #d7000b;
    padding-top: 25px;
  }

  .inStock {
    font-family: "Roboto Condensed";
    font-style: normal;
    font-weight: normal;
    font-size: 12px;
    line-height: 14px;
    text-align: center;

    color: #239a0f;
  }

  .notInStock {
    font-family: "Roboto Condensed";
    font-style: normal;
    font-weight: normal;
    font-size: 12px;
    line-height: 14px;
    text-align: center;

    color: $redColor;
  }

  .btn.add-to-cart {
    padding: 7px 4px;
    background: #d41f26;
    border-radius: 50px;
    font-family: "Roboto Condensed", sans-serif;
    font-style: normal;
    font-weight: bold;
    font-size: 12px;
    line-height: 14px;
    text-align: center;
    color: #ffffff;
    text-decoration: none;
    @include easeInOut;
    box-shadow: 0px 3px 10px rgba(0, 0, 0, 0.35);

    margin-top: 0px;
  }

  .more-images {
    display: none;
  }

  .relatedProducts {
    font-family: $mainFont;
    font-style: normal;
    font-weight: normal;
    font-size: 12px;
    line-height: 14px;

    align-items: center;

    color: #8b8b8b;
  }
}
@include mediaXSm {
  .image-showcase img {
    min-height: 70px;
    max-height: 70px;
    height: 100%;
    min-width: 70px;
    max-width: 70px;
    width: 100%;
    box-shadow: 0px 3px 5px rgba(0, 0, 0, 0.25);
    border-radius: 5px;
  }
}
@include mediaXXXSm {
  .desktop-only {
    display: none;
  }

  .mobile-only,
  .sm-xsm-xxsm-only {
    display: block;
  }

  h1.details-page-header {
    font-size: 14px;
    line-height: 16px;
    margin-top: 0px;

    color: #000000;
  }

  .image-showcase {
    margin-top: 0px;
    margin-bottom: 0px;
  }

  .image-showcase img {
    min-height: 70px;
    max-height: 70px;
    height: 100%;
    min-width: 70px;
    max-width: 70px;
    width: 100%;
    box-shadow: 0px 3px 5px rgba(0, 0, 0, 0.25);
    border-radius: 5px;
  }

  .more-images {
    display: none;
  }

  .detail-cost {
    font-family: "Roboto", sans-serif;
    font-style: normal;
    font-weight: bold;
    font-size: 14px;
    line-height: 93.75%;
    letter-spacing: -0.05em;

    color: #8b8b8b;
    margin-bottom: -10px;
  }

  .markdown {
    font-family: $mainFont;
    font-style: normal;
    font-weight: normal;
    font-size: 12px;
    line-height: 14px;

    color: #8b8b8b;
  }

  .detail-discount-cost {
    font-family: "Roboto", sans-serif;
    font-style: normal;
    font-weight: bold;
    font-size: 10px;
    line-height: 12px;
    text-align: center;
    text-decoration-line: line-through;

    color: #d7000b;
    padding-top: 25px;
  }

  .inStock {
    font-family: "Roboto Condensed";
    font-style: normal;
    font-weight: normal;
    font-size: 10px;
    line-height: 12px;
    text-align: center;

    color: #239a0f;
  }

  .notInStock {
    font-family: "Roboto Condensed";
    font-style: normal;
    font-weight: normal;
    font-size: 10px;
    line-height: 12px;
    text-align: center;

    color: $redColor;
  }

  .btn.add-to-cart {
    padding: 2px 1px;
    background: #d41f26;
    border-radius: 50px;
    font-family: "Roboto Condensed", sans-serif;
    font-style: normal;
    font-weight: bold;
    font-size: 11px;
    line-height: 12px;
    text-align: center;
    color: #ffffff;
    text-decoration: none;
    @include easeInOut;
    box-shadow: 0px 3px 10px rgba(0, 0, 0, 0.35);

    margin-top: 0px;
  }

  .more-images {
    display: none;
  }
}
</style>
