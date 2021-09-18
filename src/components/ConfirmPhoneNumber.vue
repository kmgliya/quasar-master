<template>
  <div v-if="component === 'confirm'" class="confirm">
    <div class="confirm__img">
      <img src="../assets/smartphone.png" alt="">
    </div>
    <h1 class="confirm__title">
      Еще один шаг
    </h1>
    <p class="confirm__description">
      Введите шестизначный код,который мы отправили на номер 0705280505
    </p>

    <div class="confirm__input">
      <input type="text">
    </div>

    <div class="confirm__btn">
      <button>Подтвердить</button>
    </div>
    <div v-on:click="changeComponent" class="confirm__changeNumber">
      Изменить номер
    </div>
  </div>

  <ChangeNumber v-else/>
</template>

<script>
  import {defineComponent} from 'vue'
  import ChangeNumber from "./ChangeNumber";

  export default defineComponent({
    name: "ConfirmPhoneNumber",
    components: {
      ChangeNumber
    },
    data() {
      return {
        component: 'confirm'
      }
    },
    methods: {
      changeComponent() {
        this.component = 'changeNumber'
      }
    }
  })
</script>
