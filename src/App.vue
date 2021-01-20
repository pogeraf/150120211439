<template>
  <div class="content">
    <Info :commentsQuantity = "commentsQuantity"/>
    <CommentsList @commentsQuantity = "commentsQuantityFunc"/>
  </div>
</template>

<script>
import Info from './components/Info'
import CommentsList from './components/CommentsList'

export default {
  name: 'App',
  components: {
    Info,
    CommentsList,
  },
  data() {
    return {
      commentsQuantity: 0
    }
  },
  methods: {
    commentsQuantityFunc(num) {
      this.commentsQuantity = num
    }
  }
}
</script>

<style>
* {
  padding: 0;
  margin: 0;
}

body {
  width: 100vw;

  display: flex;
  justify-content: center;
}
.content {
  min-width: 360px;
  max-width: 720px;

  padding: 20px 20px 0;
}
</style>
