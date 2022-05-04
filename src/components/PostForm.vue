<template>
  <form @submit.prevent>
    <h4>Создание поста</h4>
    <input
      v-model="post.title"
      class="input"
      type="text"
      placeholder="Название"
    />
    <input
      v-model="post.body"
      class="input"
      type="text"
      placeholder="Описание"
    />
    <button class="btn" @click="createPost">Создать</button>
  </form>
</template>


<script>
export default {
  data() {
    return {
      post: {
        title: "",
        body: "",
      },
    };
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit("create", this.post);
      this.post = {
        title: "",
        body: "",
      };
    },
  },
};
</script>
// $emit сгенироровать событие под которое может подписаться родительский комитет.

<style scoped>
form {
  display: flax;
  flex-direction: column;
}
.input {
  width: 100%;
  border: 1px solid tomato;
  padding: 10px 15px;
  margin-top: 15px;
}

.btn {
  margin-top: 25px;
  align-self: flex-end;
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 3px solid teal;
}
</style>