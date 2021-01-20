<template>
  <section class="personal-info">
    <img src="../image/userPhoto.png" class="personal-info__photo" alt="">
    <div class="personal-info__text-info">
      <p class="personal-info__name">{{ userName }}</p>
      <p class="personal-info__position">{{ userPosition }}</p>
      <p class="personal-info__status">{{ userStatus }}</p>
    </div>
  </section>
</template>

<script>
export default {
  name: "UserInfo",
  data() {
    return {
      userName: 'Вероника Ростова',
      userPosition: 'Менеджер по продажам',
      userStatus: 'Подберу для вас самые лучшие предложения. Мои услуги абсолютно бесплатны',
    };
  },
}
</script>

<style lang="scss">
.personal-info {
  height: 124px;
  display: flex;

  &__photo {
    width: 124px;
    height: 124px;

    margin-right: 10px;
    z-index: 2;

    border-radius: 50%;
  }

  &__text-info {
    padding: 10px 0 10px 0;

    display: flex;
    flex-direction: column;
    //justify-content: space-around;

    color: #333333;
  }

  &__name {
    font-family: Arial;
    font-weight: bold;
    font-size: 16px;
    line-height: 20px;
  }

  &__position {
    color: #808080;
    font-family: Arial;
    font-size: 12px;
    line-height: 20px;
  }

  &__status {
    min-height: 50px;
    overflow: hidden;

    display: flex;
    align-items: center;

    margin: 5px 0 0 -45px;
    padding: 5px 5px 5px 45px;

    border: 1px solid #DADADA;
    background: #FFFBC8;
    box-sizing: border-box;
    border-radius: 5px;
    font-family: Arial;
    font-size: 14px;
    line-height: 20px;
  }
}

@media screen and (max-width: 485px) {
  .personal-info__status {
    min-height: 55px;
    margin: 5px 0 0 -50px;
    padding: 5px 5px 5px 50px;
  }
}
</style>