<template>
  <section class="rating-info">
    <p class="rating-info__last-comment">Последние отзывы</p>
    <p class="rating-info__all-comment">Все отзывы</p>
    <div class="rating-info__quantity" @click="valueLikes++">
      <img src="../image/like.png" class="rating-info__icon">
      <p class="rating-info__value">{{ valueLikes }}</p>
    </div>
    <div class="rating-info__quantity">
      <img src="../image/comment.png" class="rating-info__icon">
      <p class="rating-info__value">{{ commentsQuantity }}</p>
    </div>
  </section>
</template>

<script>
export default {
  name: "RatingInfo",
  props: {
    commentsQuantity: Number
  },
  data() {
    return {
      valueLikes: 0,
    };
  },
}
</script>

<style lang="scss">
.rating-info {
  display: flex;
  align-items: center;
  font-family: Arial;
  color: #333333;

  &__last-comment {
    padding-right: 10px;

    font-weight: bold;
    font-size: 16px;
    line-height: 16px;
  }

  &__all-comment {
    min-width: 76px;
    width: calc(100vw - 315px);
    max-width: 404px;
    font-size: 14px;
    text-decoration-line: underline;
    color: #005DA1;
  }

  &__quantity {
    display: flex;
    padding: 10px;
  }

  &__icon {
    width: 13px;
    height: 13px;
    margin: 1px 2px;
  }

  &__value {
    font-size: 12px;
    line-height: 14px;
  }
}
</style>