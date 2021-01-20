<template>
  <div class="comment">
    <span class="comment__userName">{{ name }}</span>
    <span class="comment__date">{{date}}</span>
    <p class="comment__message">{{ message }}</p>
  </div>
</template>

<script>
export default {
  name: "Comment",
  props: {
    name: String,
    message: String,
  },
  computed: {
    date() {
      let Data = new Date();
      let Year = Data.getFullYear();
      let Month = Data.getMonth();
      let Day = Data.getDate();
      let fMonth;

// Преобразуем месяца
      switch (Month) {
        case 0:
          fMonth = "января";
          break;
        case 1:
          fMonth = "февраля";
          break;
        case 2:
          fMonth = "марта";
          break;
        case 3:
          fMonth = "апреля";
          break;
        case 4:
          fMonth = "мае";
          break;
        case 5:
          fMonth = "июня";
          break;
        case 6:
          fMonth = "июля";
          break;
        case 7:
          fMonth = "августа";
          break;
        case 8:
          fMonth = "сентября";
          break;
        case 9:
          fMonth = "октября";
          break;
        case 10:
          fMonth = "ноября";
          break;
        case 11:
          fMonth = "декабря";
          break;
      }
      return (Day + " " + fMonth + " " + Year)
    }
  }
}
</script>

<style lang="scss">
.comment {
  display: flex;
  flex-wrap: wrap;

  color: #333333;
  font-family: Arial;

  &__userName {
    height: 20px;
    padding-right: 10px;

    display: flex;
    align-items: center;

    font-weight: bold;
    font-size: 14px;
  }

  &__date {
    height: 22px;
    display: flex;
    align-items: center;

    font-size: 12px;
    color: #808080;
  }

  &__message {
    width: 100%;
    height: auto;

    position: relative;
    margin: 10px 0;
    padding: 20px 15px 15px 20px;

    background: #F2FBFF;
    border: 1px solid #C4CBCF;
    box-sizing: border-box;
    box-shadow: 0px 4px 10px rgba(128, 128, 128, 0.1);
  }

  &__message:after,
  &__message:before {
    content: '';
    border: solid transparent;
    position: absolute;
    left: 50px;
    bottom: 100%;
    margin-left: -12px;
    width: 0;
  }

  &__message:before {
    border-left-color: #C4CBCF;
    border-bottom-color: #C4CBCF;
    border-width: 5.5px;
  }

  &__message:after {
    border-left-color: #F2FBFF;
    border-bottom-color: #F2FBFF;
    border-width: 4px;
    margin-left: -11px;
  }


  //&__message:before {
  //  content: "";
  //  position: absolute;
  //  z-index: 0;
  //  bottom: 53px;
  //  left: 16px;
  //  height: 8px;
  //  width: 5px;
  //  background: #F2FBFF;
  //  border-radius: 0px 25px 0px 0px;
  //  border: 1px solid #C4CBCF;
  //  border-bottom: none;
  //}
}
</style>