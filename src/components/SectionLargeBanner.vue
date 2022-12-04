<template>
  <section class="large-banner">
    <div class="large-banner__wrapper">
      <div class="large-banner__container">
        <div class="large-banner__content">
          <div class="large-banner__text">
            <p class="large-banner__title">
              Впервые на ProExpertme <br />
              интерактивная игра <br />
              La Roche-Posay
            </p>
            <p class="large-banner__subtitle">c 21 ноября по 15 декабря</p>
            <div class="large-banner__buttons">
              <button class="btn btn__prizes" type="sumbit" @click="sendForm" :disabled="isDisabled">Призы</button>
              <button class="btn btn__rules" type="sumbit" @click="sendForm" :disabled="isDisabled">Правила</button>
            </div>
          </div>
          <div class="large-banner__img">
            <img
              src="../assets/img/woman.svg"
              alt="женщина с планшетом"
              class="large-banner__image"
            />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import '../assets/scss/index.scss';

.large-banner {
  padding-bottom: 15rem;
  padding-top: 3rem;
  &__container {
    max-width: 138rem;
    margin: auto;
    background-image: url(../assets/img/backround-large-banner.png);
    background-repeat: no-repeat;
    background-size: cover;
    filter: drop-shadow(4px 4px 40px #a4d6f9);
    border-radius: 3rem;
  }
  &__content {
    display: flex;
    justify-content: space-between;
    max-width: 118rem;
    margin: auto;
    position: relative;
  }
  &__text {
    padding: 8rem 0 8.7rem 0;
  }
  &__img {
    padding: 3rem 13rem 0 0;
  }
  &__title {
    font-family: "Montserrat Bold";
    font-weight: 700;
    @include adaptiv-font(48, 25);
    line-height: 5.8rem;
    color: #0070bb;
    margin-bottom: 2.5rem;
  }
  &__subtitle {
    font-family: "Montserrat Regular";
    font-weight: 400;
    @include adaptiv-font(24, 18);
    line-height: 2.9rem;
    color: #146093;
    margin-bottom: 6rem;
  }
}

.btn {
  @include adaptiv-font(24, 18);
  &__rules {
    padding: 1.8rem 0.5rem;
    font-family: "Montserrat Medium";
    font-weight: 500;
    line-height: 2.9rem;
    letter-spacing: 0.015em;
    color: #ffffff;
    background: #a4d6f9;
    width: 23rem;
  }
  &__prizes {
    font-family: "Montserrat Medium";
    font-weight: 500;
    line-height: 2.9rem;
    letter-spacing: 0.015em;
    text-transform: capitalize;
    color: #ffffff;
    padding: 1.8rem 0.5rem;
    margin-right: 2rem;
    width: 23rem;
  }
}

@media (max-width: 1400px) {
  .large-banner {
    &__container {
      max-width: 105rem;
    }
    &__content {
      max-width: 90rem;
    }
  }
}
@media (max-width: 1200px) {
  .large-banner {
    &__container {
      max-width: 95rem;
    }
    &__content {
      max-width: 81rem;
    }
  }
  .btn{
    &__prizes{
      margin-bottom: 2rem;
    }
  }
}

@media (max-width: 992px) {
  .large-banner {
    padding-bottom: 9rem;
    &__container {
      max-width: 67rem;
    }
    &__content {
      max-width: 57rem;
    }
  }
}

@media (max-width: 767px) {
  .large-banner {
    &__container {
      max-width: 53rem;
    }
    &__content {
      max-width: 45rem;
    }
    &__image {
      position: absolute;
      width: 50%;
      bottom: 0;
      right: -8%;
    }
    &__img {
      padding: 0;
    }
    &__title{
      margin-bottom: 1.5rem;
    }
    &__subtitle{
      margin-bottom: 3rem;
    }
  }
  .btn {
    width: 16rem;
    display: block;
  }
}

@media (max-width: 615px) {
  .large-banner {
    &__container {
      max-width: 48rem;
    }
    &__content {
      max-width: 41rem;
    }
  }
}

@media (max-width: 576px) {
  .large-banner {
    &__container {
      max-width: 38rem;
    }
    &__content {
      max-width: 32.5rem;
    }
    &__title {
      line-height: 3.05rem;
    }
  }
}

@media (max-width: 480px) {
  .large-banner {
    &__subtitle{
      max-width: 11rem;
    }
    &__container {
      max-width: 32rem;
    background-image: url(../assets/img/background-large-banner-mobile.png);
    }
    &__content {
      max-width: 28rem;
    }
  }
}

@media (max-width: 350px) {
  .large-banner {
    &__container {
      max-width: 26rem;
    }
    &__content {
      max-width: 22rem;
    }
  }
}
</style>