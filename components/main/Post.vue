<template>
  <el-card shadow="hover" :body-style="{padding: 0}" class="post">
    <header slot="header" class="post-header">
      <h3>Title</h3>
      <small>
        <i class="el-icon-time"></i>
        {{ new Date().toLocaleString() }}
      </small>
    </header>
    <div class="post-body">
      <img
        src="https://cdn21.img.ria.ru/images/155959/50/1559595090_0:0:3160:2048_600x600_80_0_1_be476b2955b5e027bdbb47b9ff1945f2.jpg"
        alt="post img"
        class="post-img"
      />
    </div>
    <footer class="post-footer">
      <el-button round @click="openPost">Открыть пост</el-button>
      <span>
        <i class="el-icon-message"></i>
        12
      </span>
    </footer>
  </el-card>
</template>
<script>
export default {
  methods: {
    openPost() {
      const id = "test-id";
      this.$router.push(`/post/${id}`);
    }
  }
};
</script>

<style lang="scss" scoped>
.post {
  margin-bottom: 1.5rem;
}
.post-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.post-img {
  width: 100%;
  height: auto;
}

.post-footer {
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>