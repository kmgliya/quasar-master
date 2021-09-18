<template>
  <div class="changeNumber">
    <div class="changeNumber__img">
      <img src="../assets/smartphone.png" alt="">
    </div>
    <h1 class="changeNumber__title">
      Изменение номера телефона
    </h1>
    <p class="changeNumber__description">
     Текущий номер телефона:
    </p>

    <div class="changeNumber__currentNumber">
      0553484837
    </div>
    <div class="changeNumber__input">
      <input type="text">
    </div>

    <div class="changeNumber__btn">
      <button>Изменить</button>
    </div>
  </div>
</template>

<script>
  import {defineComponent} from 'vue'

  export default defineComponent({
    name: 'ChangeNumberComponent'
  })
</script>
