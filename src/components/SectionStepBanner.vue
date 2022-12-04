<template>
  <section
    class="step-banner"
    :key="banner.id"
    v-for="(banner, index) in banners"
  >
    <div class="step-banner__container">
      <div class="step-banner__wrapper">
        <div
          class="step-banner__content"
          :class="{ mod: banner.pos === 'right' }"
        >
          <p class="step-banner__num">{{ index + 1 }}</p>
          <p class="step-banner__title">{{ banner.title }}</p>
          <p class="step-banner__subtitle">{{ banner.subtitle }}</p>
          <p class="step-banner__subtitle step-banner__subtitle_bottom">
            {{ banner.subtitleBottom }}
          </p>
          <button
            class="btn step-banner__button"
            type="sumbit"
            @click="sendForm"
            :disabled="isDisabled"
            :class="{ wide: banner.button === 'wide' }"
          >
            {{ banner.btn }}
          </button>
        </div>
        <div class="step-banner__img">
          <img
            :src="banner.image.src"
            :alt="banner.image.alt"
            class="step-banner__image"
          />
        </div>
      </div>
    </div>
  </section>
</template>
  
  <script>
export default {
  data() {
    return {
      banners: [
        {
          id: 1,
          title: "Пройдите видеоигру по La Roche-Posay",
          subtitleBottom: "За пройденный модуль вы получите баллы.",
          btn: "Играть",
          image: {
            src: require("@/assets/img/pharmacy.svg"),
            alt: "картинка аптеки",
          },
        },
        {
          id: 2,
          title: "Интерактивное тестирование ",
          subtitle:
            "За пройденный модуль вы получите баллы, сумма которых равна количеству верных ответов в тесте.",
          subtitleBottom:
            "Участники, набравшие более _ _ баллов, будут допущены к розыгрышу призов.",
          btn: "Начать",
          image: {
            src: require("@/assets/img/cream.svg"),
            alt: "продукция компании",
          },
          pos: "right",
        },
        {
          id: 3,
          title: "Розыгрыш призов в прямом эфире в Telegram",
          subtitle: "Эфир с вашим любимым доктором Майей Голдобиной. ",
          subtitleBottom: "Пройдет до 15 декабря 2022 года.",
          btn: "Присоединиться",
          button: "wide",
          image: {
            src: require("@/assets/img/man.svg"),
            alt: "доктор",
          },
        },
      ],
    };
  },
};
</script>
  
  <style lang="scss" scoped>
@import "../assets/scss/index.scss";
.step-banner {
  &__container {
    max-width: 132rem;
    margin: auto;
  }
  &__image {
    width: 100%;
  }
  &__wrapper {
    display: flex;
    justify-content: space-between;
    padding-bottom: 15rem;
  }
  &__content {
    max-width: 42rem;
    margin-left: 7rem;
  }

  &__num {
    font-family: "Montserrat Bold";
    font-weight: 700;
    @include adaptiv-font(22, 14);
    color: #99cef2;
    background-color: #fff;
    width: 5rem;
    height: 5rem;
    text-align: center;
    border-radius: 5rem;
    line-height: 5rem;
    margin-bottom: 2rem;
  }
  &__title {
    font-family: "Montserrat Bold";
    font-weight: 700;
    @include adaptiv-font(40, 24);
    line-height: 4.8rem;
    color: #0070bb;
    max-width: 480x;
    margin-bottom: 2.5rem;
  }
  &__subtitle {
    font-family: "Montserrat Regular";
    font-weight: 400;
    @include adaptiv-font(20, 16);
    line-height: 2.4rem;
    color: #146093;
    margin-bottom: 1.5rem;
    &_bottom {
      margin-bottom: 6rem;
    }
  }
  &__button {
    filter: drop-shadow(4px 4px 84px #b0d5f0);
    width: 28rem;
    height: 6.5rem;
    font-family: "Montserrat Medium";
    font-weight: 500;
    line-height: 2.9rem;
    text-align: center;
    letter-spacing: 0.015em;
    text-transform: capitalize;
    color: #ffffff;
  }
  &__img img {
    width: 100%;
  }
}

.btn {
  @include adaptiv-font(24, 18);
}

.mod {
  order: 2;
  margin-left: 0;
  margin-right: 7rem;
}

@media (max-width: 1400px) {
  .step-banner {
    &__container {
      max-width: 110rem;
    }
  }
}
@media (max-width: 1200px) {
  .step-banner {
    &__container {
      max-width: 95rem;
    }
  }
}

@media (max-width: 992px) {
  .step-banner {
    &__subtitle {
      &_bottom {
        margin-bottom: 3rem;
      }
    }
    &__container {
      max-width: 70rem;
    }
    &__wrapper {
      flex-wrap: wrap;
      padding-bottom: 8rem;
    }
    &__content {
      margin-right: 0;
      margin-left: 0;
      order: 1;
    }
  }
}

@media (max-width: 767px) {
  .step-banner {
    &__container {
      max-width: 55rem;
    }
    &__button {
      width: 16rem;
    }
  }
  .wide {
    width: 22rem;
  }
}

@media (max-width: 615px) {
  .step-banner {
    &__container {
      max-width: 50rem;
    }
  }
}

@media (max-width: 576px) {
  .step-banner {
    &__container {
      max-width: 40rem;
    }
    &__title {
      line-height: 3rem;
    }
    &__subtitle {
      line-height: 1.95rem;
    }
  }
}

@media (max-width: 480px) {
  .step-banner {
    &__container {
      max-width: 30rem;
    }
  }
}

@media (max-width: 350px) {
  .step-banner {
    &__container {
      max-width: 27rem;
    }
  }
}
</style>