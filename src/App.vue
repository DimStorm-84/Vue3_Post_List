<template>
  <div class="app">
    <post-form 
    @create="createPost" 
    />
    <post-list 
    v-bind:posts="posts" 
    />
  </div>
</template>
// шаблоен и структура компанетна
// интерполяция - обращение к шаблону
// v-  слушатель событий отрибутов(дерективы)
// v-for для работы с массивом в дерективах
// v-bind позволяет связывать данные с конкретным компонентом
   
<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";
export default {
  components: {
    PostList,
    PostForm,
  },
  data() {
    return {
      posts: [
        { id: 1, title: "JavaScript", body: "Описание поста" },
        { id: 2, title: "JavaScript 2", body: "Описание поста 2" },
        { id: 3, title: "JavaScript 3", body: "Описание поста 3" },
        { id: 4, title: "JavaScript 4", body: "Описание поста 4" },
      ],
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
    },
  },
};
</script>
// создаем поля и модели, необходимые для описания функции

   
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-block;
}
.app {
  padding: 20px;
}
</style>
