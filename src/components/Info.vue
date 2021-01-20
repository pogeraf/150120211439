<template>
  <div>
    <UserInfo/>
    <ServicesInfo/>
    <RatingInfo :commentsQuantity = "commentsQuantity"/>
  </div>
</template>

<script>
import UserInfo from '@/components/UserInfo'
import ServicesInfo from '@/components/ServicesInfo'
import RatingInfo from '@/components/RatingInfo'
export default {
  name: "Info",
  components: {
    UserInfo,
    ServicesInfo,
    RatingInfo,
  },
  props: {
    commentsQuantity: Number
  },
  data() {
    return {

    };
  },
}
</script>

<style lang="scss">
</style>