<template>
  <div class="comments">
    <div class="comments__list">
      <div class="comments" v-for="(elem, index) in commentsList" :key="index">
        <Comment :name="elem.name" :message="elem.message"/>
      </div>
    </div>
    <AddComment @addComment="addComment"/>
  </div>
</template>

<script>
import AddComment from "@/components/AddComment";
import Comment from "@/components/Comment";

export default {
  name: "CommentsList",
  components: {
    Comment,
    AddComment
  },
  data() {
    return {
      commentsList: Array()
    }
  },
  methods: {
    addComment(obj) {
      this.commentsList.push(obj)
      this.$emit('commentsQuantity', this.commentsList.length)
    }
  }
}
</script>

<style lang="scss">
.comments {


  &__list {
    height: 300px;
    overflow-y: auto;
  }
}
</style>