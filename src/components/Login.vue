<template>
  <div class="loginPage">
    <div class="login">
      <h1 class="login__title">Instagram</h1>
      <div class="login__email">
        <input type="text" placeholder="Телефон, имя пользователя или эл.адрес">
      </div>
      <div class="login__password">
        <input type="text" placeholder="Пароль">
      </div>
      <div class="login__btn">
        <button>Войти</button>
      </div>
    </div>

    <div class="accountRegister">
      У вас ещё нет аккаунта?
      <router-link to="/auth/registration" class="accountRegister__link">
        Зарегистрироваться
      </router-link>
    </div>
  </div>

</template>


<script>
  import {defineComponent} from 'vue'

  export default defineComponent({
    name: 'Login'
  })
</script>


<style>

</style>
