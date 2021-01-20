<template>
  <section class="services-info">
    <p class="services-info__title">Услуг</p>
    <div class="services-info__services-list">

      <div
          v-for="(service, index) in servicesList"
          :key="index"
          class="services-list__service"
      >
        <p
            :style="{'--width': `${service.value / ( getMaxServiceListValue / 100)}%`, '--backgroundColor': service.value === getMaxServiceListValue ? '#B1E19B' : '#ACE2F8'}"
            class="services-list__name"
        >
          <span>{{ service.name }}</span>
        </p>
        <p class="services-list__quantity">{{ service.value }}</p>
      </div>

    </div>
    <div class="services-info__quantity-services">
      <div class="quantity-services__title">Всего</div>
      <div class="quantity-services__value">{{ quantityServices }}</div>
    </div>
  </section>
</template>

<script>
export default {
  name: "ServicesInfo",
  data() {
    return {
      servicesList: [
        {
          name: 'Ручное бронирование',
          value: 11,
        },
        {
          name: 'Пакетные туры',
          value: 3,
        },
        {
          name: 'Отели',
          value: 1,
        },
      ],
      quantityServices: '15',
    };
  },
  computed: {
    getMaxServiceListValue() {
      return Math.max.apply(null, this.servicesList.map(s => s.value));
    },
  },
}
</script>

<style lang="scss">

$borderQuantity: 1px solid #DADADA;

.services-info {
  margin-left: 135px;

  color: #333333;

  font-family: Arial;

  &__title {
    padding: 0 20px 0 0;

    text-align: right;


    font-size: 13px;
    line-height: 15px;
  }

  &__services-list {
    height: 107px;

    margin: 8px 0 15px 0;

    display: flex;
    flex-direction: column;

    justify-content: center;

    border-top: $borderQuantity;
    border-bottom: $borderQuantity;

    font-size: 13px;
  }

  &__quantity-services {
    display: flex;

    font-weight: bold;
    font-size: 16px;
  }
}


.services-list {
  &__service {
    display: flex;
    margin: 1px 0;
  }

  &__name {
    width: 80%;

    position: relative;

    line-height: 26px;

    &:before {
      content: '';
      position: absolute;
      width: var(--width);
      height: 26px;
      background: var(--backgroundColor);
      border-radius: 0 5px 5px 0;
      z-index: -1;
    }

    span {
      padding: 0 10px;
    }
  }

  &__quantity {
    width: 20%;

    padding: 0 30px 0 0;
    display: flex;
    align-items: center;
    justify-content: flex-end;

    font-weight: bold;
  }
}


.quantity-services {
  &__title {
    width: 80%;
  }


  &__value {
    width: 20%;
    padding-right: 30px;

    text-align: right;
  }
}
</style>