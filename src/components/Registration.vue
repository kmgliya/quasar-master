<template>
  <div v-if="component === 'registration'" class="registration-wrapper">
    <div class="registration">
      <h1 class="registration__title-logo">Instagram</h1>
      <p class="registration__title">Зарегистрируйтесь, чтобы смотреть фото и видео ваших друзей.</p>
      <div class="registration__btn">
        <button>Войти через Facebook</button>
      </div>
      <div class="registration__lines">
        <div class="registration__right-line"></div>
        <div class="registration__line-text">ИЛИ</div>
        <div class="registration__right-line"></div>
      </div>

      <div class="registration__input" v-for="(inp, ind) in registerInputs" :key="ind">
        <input type="text" :placeholder="inp.placeholder">
      </div>
      <div class="registration__btn">
        <button v-on:click="changeComponent">Регистрация</button>
      </div>
      <p class="registration__privacy">Регистрируясь, вы принимаете наши <b>Условия, Политику использования данных и
        Политику в отношении файлов cookie.</b></p>
    </div>

    <div class="account-login">
      <span>Есть аккаунт?</span>
      <router-link to="/auth" class="account-login-link">Вход</router-link>
    </div>
    <div class="app-installation">
      <p>Установите приложение.</p>
      <div class="app-installation__icons">
        <a :href="googleLink">
          <img src="../assets/google.png" alt="">
        </a>
        <a :href="iosLink">
          <img src="../assets/ios.png" alt="">
        </a>
      </div>
    </div>

  </div>
  <div v-if="component === 'birthday'">
    <Birthday/>
  </div>
</template>


<script>
  import {defineComponent} from 'vue'
  import Birthday from "./Birthday";

  export default defineComponent({
    name: 'RegistrationComponent',
    components: {
      Birthday
    },
    data() {
      return {
        registerInputs: [
          {
            placeholder: 'Моб. телефон или эл. адрес'
          },
          {
            placeholder: 'Имя и фамилия'
          },
          {
            placeholder: 'Имя пользователя'
          },
          {
            placeholder: 'Пароль'
          }
        ],
        googleLink: 'https://play.google.com/store/apps/details?id=com.instagram.android&referrer=utm_source%3Dinstagramweb&utm_campaign=loginPage&ig_mid=D130597B-4B2B-40C0-B026-E20D31930EF1&utm_content=lo&utm_medium=badge',
        iosLink: 'https://apps.apple.com/app/instagram/id389801252?vt=lo',
        component: 'registration'
      }
    },
    methods: {
      changeComponent() {
        this.component = 'birthday'
      }
    }
  })
</script>


<style>

</style>
