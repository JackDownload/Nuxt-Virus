<template>
  <footer>
    <div class="bottom-contact container">
      <div class="logo">
        <nuxt-link
          class="/navbar-brand logo"
          to="/"
          aria-label="Virus Logo"
        >
          <b-img-lazy
            src="~/assets/img/virus-logo.svg"
            alt="virus Footer logo"
          />
        </nuxt-link>
      </div>
      <ul>
        <li>
          <a href="mailto:deteylingvirus@gmail.com">
            deteylingvirus@gmail.com
            <font-awesome-icon
              :icon="['fa', 'envelope']"
              class="ml-2 fa-lg"
            />
          </a>
        </li>
        <li>
          <a href="tel:+380673334040">
            +38 (067) 333-40-40
            <font-awesome-icon
              :icon="['fas', 'phone']"
              class="ml-2 fa-lg"
            />
          </a>
        </li>

        <li>
          <nuxt-link
            v-scroll-to="{el: '#map-top', duration: 500, offset: -60 }"
            to="/kontakty"
          >
            Україна, м. Тернопіль, вул. Приміська 15А
            <font-awesome-icon
              :icon="['fas', 'map-marker-alt']"
              class="ml-2 fa-lg"
            />
          </nuxt-link>
        </li>
        <li>
          <a
            href="https://www.instagram.com/virusdetailing/"
            target="_blank"
            rel="noopener"
            class="instagram"
          >
            <picture>
              <source
                srcset="~/assets/imgWebP/icons8-instagram-filled-100.webp"
                type="image/webp"
              >
              <img
                src="~/assets/img/icons8-instagram-filled-100.png"
                alt="icons instagram filled"
              >
            </picture>
          </a>
          <a
            href="https://www.facebook.com/virus.te.ua/"
            target="_blank"
            rel="noopener"
            class="facebook"
          >
            <picture>
              <source
                srcset="~/assets/imgWebP/icons8-facebook-filled-100.webp"
                type="image/webp"
              >
              <img
                src="~/assets/img/icons8-facebook-filled-100.png"
                alt="icons facebook filled"
              >
            </picture>
          </a>
        </li>
      </ul>
    </div>
  </footer>
</template>

<script>
export default {}
</script>
<style lang="scss" scoped>
footer {
  width: 100vw;
  background: $darkColor;
  color: $lightColor;

  a,
  img {
    text-decoration: none;
    @include easeInOut;

    &:hover {
      @include scale;
    }
  }

  .logo {
    position: relative;
    z-index: 100;
    float: left;
    margin-right: 36px;
    padding: 0;
    margin: 0;
    line-height: 140px;

    img {
      height: 2.4rem;
    }
  }

  .bottom-contact {
    padding: 30px 0;
    position: relative;

    ul {
      text-align: right;
      list-style: none;
      overflow: hidden;
      padding: 0;
      margin: 0;
    }

    ul li {
      display: block;
      padding: 5px 0;
      margin: 0;
    }

    ul li a {
      padding: 0;
      margin: 0;
      text-decoration: none;
      color: $lightColor;
      font-family: $secondaryFont;
      font-style: normal;
      font-weight: normal;
      font-size: 14px;
      line-height: normal;
      text-align: center;
      @include easeInOut;

      &:hover {
        text-decoration: none;
        color: $redColor;
        transform: scale(1.1);
        -webkit-transform: scale(1.1);
        -moz-transform: scale(1.1);
        -ms-transform: scale(1.1);
        -o-transform: scale(1.1);
      }

      &.instagram,
      &.facebook {
        margin-left: 20px;
      }
    }
  }
}

@include mediaMd {
  footer {
    background: $darkColor;
    color: $lightColor;
    padding: 10px 0;

    a {
      text-decoration: none;
      @include easeInOut;

      &:hover {
        transform: scale(1.1);
        -webkit-transform: scale(1.1);
        -moz-transform: scale(1.1);
        -ms-transform: scale(1.1);
        -o-transform: scale(1.1);
      }
    }

    .bottom-contact {
      padding: 00px 0;
      background: $darkColor;
      height: auto;

      ul {
        position: relative;
        display: block;
        text-align: center;
        list-style: none;
        overflow: hidden;
        padding: 0;
        margin: 0;
        margin-top: 60px;
      }

      ul li {
        display: block;
        padding: 10px 0;
        margin: 0;
      }

      ul li a {
        padding: 0;
        margin: 0;
        text-decoration: none;
        color: $lightColor;
        font-family: $secondaryFont;
        font-style: normal;
        font-weight: normal;
        font-size: 14px;
        line-height: normal;
        text-align: center;
        @include easeInOut;

        &:hover {
          text-decoration: none;
          color: $redColor;
          @include scale;
        }

        &.instagram,
        &.facebook {
          margin-left: 20px;
        }
      }
    }
  }

  footer {
    .logo {
      img {
        display: none;
      }
    }
  }
}

@include mediaSm {
  footer {
    .logo {
      img {
        display: none;
      }
    }
  }
}

@include mediaXSm {
  footer {
    .logo {
      img {
        display: none;
      }
    }
  }
}
</style>
