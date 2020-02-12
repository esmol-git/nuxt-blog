<template>
  <article class="post">
    <header class="post-header">
      <div class="post-title">
        <h1>Post title</h1>
        <nuxt-link to="/">
          <i class="el-icon-back"></i>
        </nuxt-link>
      </div>
      <div class="post-info">
        <small>
          <i class="el-icon-time"></i>
          {{ new Date().toLocaleString() }}
        </small>
        <small>
          <i class="el-icon-view"></i>
          42
        </small>
      </div>
      <div class="post-image">
        <img
          src="https://cdn21.img.ria.ru/images/155959/50/1559595090_0:0:3160:2048_600x600_80_0_1_be476b2955b5e027bdbb47b9ff1945f2.jpg"
          alt="post image"
        />
      </div>
    </header>
    <main class="post-text">
      <p>
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Culpa cumque non
        atque numquam odio expedita doloremque dignissimos, libero voluptatum
        sapiente.
      </p>
      <p>
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Culpa cumque non
        atque numquam odio expedita doloremque dignissimos, libero voluptatum
        sapiente.
      </p>
      <p>
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Culpa cumque non
        atque numquam odio expedita doloremque dignissimos, libero voluptatum
        sapiente.
      </p>
      <p>
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Culpa cumque non
        atque numquam odio expedita doloremque dignissimos, libero voluptatum
        sapiente.
      </p>
    </main>
    <footer>
      <app-comment-form v-if="canAddComment" @created="createCommetHandler" />

      <div class="comments" v-if="true">
        <app-comment v-for="comment in 4" :key="comment" :comment="comment" />
      </div>
      <div class="text-center" v-else>Комментариев нет</div>
    </footer>
  </article>
</template>

<script>
import AppComment from "@/components/main/Comment";
import AppCommentForm from "@/components/main/CommentForm";
export default {
  validate({ params }) {
    return Boolean(params.id);
  },
  data() {
    return {
      canAddComment: true
    };
  },
  methods: {
    createCommetHandler() {
      this.canAddComment = false;
    }
  },
  components: { AppComment, AppCommentForm }
};
</script>
<style lang="scss" scoped>
.post {
  width: 600px;
  margin: 0 auto;
}
.post-title {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1rem;
}
.post-info {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 0.5rem;
}
.post-image {
  width: 100%;
  height: auto;
}
.post-header {
  margin-bottom: 1.5rem;
}
.post-content {
  margin-bottom: 2rem;
}
.post-text {
  margin-bottom: 1.5rem;
}
</style>
