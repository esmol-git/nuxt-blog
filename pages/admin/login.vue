<template>
  <el-card shadow="always" :style="{width: '500px'}">
    <div class="mb"></div>
    <el-form :model="controls" :rules="rules" ref="form" @submit.native.prevent="onSubmit">
      <h2>Войти в панель администратора</h2>
      <el-form-item label="Логин" prop="login">
        <el-input v-model.trim="controls.login" />
      </el-form-item>
      <div class="mb2">
        <el-form-item label="Пароль" prop="password">
          <el-input v-model.trim="controls.password" type="password" />
        </el-form-item>
      </div>
      <el-form-item>
        <el-button type="primary" round native-type="submit" :loading="loading">Войти</el-button>
      </el-form-item>
    </el-form>
  </el-card>
</template>


<script>
export default {
  layout: "empty",
  data() {
    return {
      loading: false,
      controls: {
        login: "",
        password: ""
      },
      rules: {
        login: [
          {
            required: true,
            message: "Введите логин",
            trigger: "blur"
          }
        ],
        password: [
          {
            required: true,
            message: "Введите пароль",
            trigger: "blur"
          },
          {
            min: 6,
            message: "Пароль должен быть не менее 6 символов",
            trigger: "blur"
          }
        ]
      }
    };
  },
  methods: {
    onSubmit() {
      this.$refs.form.validate(valid => {
        if (valid) {
          this.loading = true;

          try {
            const fornData = {
              login: this.controls.login,
              password: this.controls.password
            };
          } catch (e) {
            this.loading = false;
          }
        }
      });
    }
  }
};
</script>