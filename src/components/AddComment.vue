<template>
  <form class="add-comment" @submit.prevent="addComment">
    <label class="add-comment__name">Имя
      <input
          class="add-comment__name-input"
          placeholder="name"
          type="text"
          v-model="formData.name"
          required
      >
    </label>
    <label>
      <textarea
          class="add-comment__message"
          v-model="formData.message"
          required
      >
      </textarea>
    </label>
    <button class="add-comment__submit" type="submit">Написать консультанту</button>
  </form>
</template>
<script>
export default {
  name: "AddComment",
  data() {
    return {
      formData: {
        name: '',
        message: '',
      },
    };
  },
  methods: {
    addComment() {
      console.log(this.formData)
      this.$emit('addComment', {name: this.formData.name, message: this.formData.message,})
    }
  }
}
</script>

<style lang="scss">
.add-comment {
  width: calc(100% + 40px);
  min-height: 200px;
  height: calc(100vh - 664px);

  margin-left: -20px;
  padding: 20px 0 0;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  background: #F2F2F2;
  font-family: Arial;

  &__name {
    min-width: 320px;
    width: 90vw;
    max-width: 680px;
    height: 50px;
    display: flex;
    flex-direction: column;
  }

  &__name-input {
    width: 150px;
    height: 15px;
    border: 1px solid #000000;
    border-radius: 2px;
    padding: 1vw;
  }

  &__message {
    min-width: 320px;
    width: 88vw;
    max-width: 680px;
    height: 63px;
    resize: none;

    padding: 1vw;

    display: flex;
    align-items: flex-start;
    justify-content: flex-start;

    border: 1px solid #000000;
    border-radius: 2px;
    font-family: Arial;
  }

  &__submit {
    width: 281px;
    height: 43px;

    border: none;
    background: #FDD639;
    border-radius: 23px;

    font-family: PT Sans;
    font-weight: bold;
    font-size: 16px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: auto;
  }
}
</style>