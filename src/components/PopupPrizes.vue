<template>
  <section class="popupPrizes">
    <div class="popupPrizes__container">
      <div class="popupPrizes__wrapper">
        <div class="popupPrizes__header">
          <img src="../assets/img/logo.svg" alt="" class="popupPrizes__logo" />
          <div class="popupPrizes__title">Призы</div>
          <img
            src="../assets/img/cross.svg"
            alt=""
            class="popupPrizes__cross"
          />
        </div>
        <div class="popupPrizes__content">
          <div class="prizes">
            <div class="prizes__item" :key="prize.id" v-for="prize in prizes">
              <div class="prizrs__img">
                <img :src="prize.image.src" :alt="prize.image.alt" />
              </div>
              <div class="amount" :class="{ top: prize.num === 'top' }">
                <p class="amount__count">{{ prize.count }}</p>
                <p class="amount__text">{{ prize.text }}</p>
              </div>
              <p class="prizes__title">
                {{ prize.title }}
              </p>
            </div>
          </div>
          <button
            class="btn popupPrizes__button"
            type="sumbit"
            @click="sendForm"
            :disabled="isDisabled"
          >
            Розыгрыш призов в прямом эфире
          </button>
        </div>
      </div>
    </div>
    <div class="popup-background"></div>
  </section>
</template>
  
  <script>
export default {
  data() {
    return {
      prizes: [
        {
          id: 1,
          title: "Смартфон Apple iPhone 13 Pro Max",
          image: {
            src: require("../assets/img/iphone-1x.png"),
            alt: "айфон 13 про макс",
          },
          count: "2",
          text: "штуки",
        },
        {
          id: 2,
          title: "Антицеллюлитный прибор BORK",
          image: {
            src: require("../assets/img/device-1x.png"),
            alt: "Антицеллюлитный прибор",
          },
          count: "2",
          text: "штуки",
        },
        {
          id: 3,
          title: "Корзина продуктов La Roche-Posay",
          image: {
            src: require("../assets/img/basket.svg"),
            alt: "продукция компании",
          },
          count: "6",
          text: "штук",
          num: "top",
        },
      ],
    };
  },
};
</script>
  
  <style lang="scss" scoped>
@import "../assets/scss/index.scss";

.popupPrizes {
  padding-bottom: 6rem;
  padding-top: 6rem;
  &__wrapper {
    background-color: #e7f5ff;
    margin: 6rem 0 6rem;
    position: relative;
    z-index: 2;
    border-radius: 3rem;
    filter: drop-shadow(4px 4px 40px #a4d6f9);
  }
  &__container {
    max-width: 120rem;
    margin: auto;
  }
  &__header {
    position: relative;
  }
  &__header {
    position: relative;
  }
  &__logo {
    position: absolute;
    top: 25%;
    left: 5%;
  }
  &__title {
    font-family: "Montserrat Bold";
    font-weight: 700;
    @include adaptiv-font(54, 36);
    line-height: 6.6rem;
    text-align: center;
    color: #0070bb;
    padding-top: 6rem;
    margin-bottom: 5.5rem;
  }
  &__cross {
    position: absolute;
    right: 2%;
    top: 10%;
  }
  &__button {
    width: 58rem;
    padding: 1.8rem 0.5rem;
    font-family: "Montserrat Medium";
    font-weight: 500;
    line-height: 2.9rem;
    letter-spacing: 0.015em;
    color: #ffffff;
    @include adaptiv-font(24, 18);
  }
  &__content {
    padding-bottom: 9rem;
    text-align: center;
  }
}
.amount {
  right: 15%;
  top: 39%;
  z-index: -1;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-family: "Montserrat Bold";
  font-weight: 700;
  text-align: center;
  color: #99cef2;
  background: #fafdff;
  border-radius: 5rem;
  width: 7rem;
  height: 7rem;
  position: absolute;
  &__text {
    font-size: 16px;
    line-height: 16px;
  }
  &__count {
    font-size: 26px;
    line-height: 30px;
    letter-spacing: -0.01em;
  }
}
.top{
  top: 32%;
}


.btn {
  @include adaptiv-font(24, 18);
}

.popup-background {
  background-image: url(../assets/img/popupBackground.png);
  opacity: 0.2;
  position: absolute;
  top: 0;
  width: 100%;
  height: 100%;
}

.prizes {
  display: flex;
  justify-content: space-evenly;
  align-items: flex-end;
  margin-bottom: 9rem;
  &__title {
    text-align: center;
    margin-top: 4rem;
    font-family: "Montserrat Bold";
    font-weight: 700;
    @include adaptiv-font(24, 18);
    line-height: 3rem;
    color: #0070bb;
    max-width: 30rem;
  }
  &__item {
    position: relative;
  }
}

@media (max-width: 1400px) {
  .popupPrizes {
    &__container {
      max-width: 110rem;
    }
  }
}
@media (max-width: 1200px) {
  .popupPrizes {
    &__container {
      max-width: 95rem;
    }
  }
}

@media (max-width: 992px) {
  .popupPrizes {
    &__container {
      max-width: 70rem;
    }
    &__button {
      width: 80%;
      line-height: 2.2rem;
      padding: 0.8rem 0.5rem;
    }
    &__logo {
      position: static;
      padding-top: 2rem;
      padding-bottom: 4rem;
    }
    &__header {
      text-align: center;
    }
    &__title {
      padding-top: 0;
      margin-bottom: 3rem;
    }
  }
  .amount{
    right: 3%;
  }
  .prizes {
    flex-direction: column;
    align-items: center;
    margin-bottom: 0;
    &__item {
      align-items: center;
      text-align: center;
      margin-bottom: 6rem;
    }
    &__item:last-child {
      margin-bottom: 4rem;
    }
    &__title {
      max-width: 24rem;
    }
  }
}

@media (max-width: 767px) {
  .popupPrizes {
    &__container {
      max-width: 55rem;
    }
  }
}

@media (max-width: 615px) {
  .popupPrizes {
    &__container {
      max-width: 50rem;
    }
  }
}

@media (max-width: 576px) {
  .popupPrizes {
    &__container {
      max-width: 40rem;
    }
  }
}

@media (max-width: 480px) {
  .popupPrizes {
    &__container {
      max-width: 32rem;
    }
  }
}

@media (max-width: 350px) {
  .popupPrizes {
    &__container {
      max-width: 27rem;
    }
  }
}
</style>


<!-- 
на общем блоке попапа :status="popupReviewForm.status" 

крестик <button type="button" class="popup__close-button"
@click="togglePopupReviewForm({ status: false })" />






-->