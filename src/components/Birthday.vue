<template>
  <div v-if="currentComponent === 'birthday'" class="birthday">
    <div class="birthday__icon">
      <img src="../assets/cake.png" alt="">
    </div>
    <h1 class="birthday__title">Укажите дату вашего рождения</h1>
    <p class="birthday__desc">
      Эта информация не будет показываться в вашем общедоступном профиле.
    </p>
    <div class="birthday__question">Почему нужно указывать дату рождения?</div>
    <div class="birthday__selects">
      <div class="q-pa-md" style="max-width: 300px">
        <div class="q-gutter-md">
          <q-select v-model="model" :options="options"/>
        </div>
      </div>

      <div class="q-pa-md" style="max-width: 300px">
        <div class="q-gutter-md">
          <q-select v-model="dateModel" :options="dateOptions"/>
        </div>
      </div>

      <div class="q-pa-md" style="max-width: 300px">
        <div class="q-gutter-md">
          <q-select v-model="yearModel" :options="yearOptions"/>
        </div>
      </div>
    </div>

    <div class="birthday__btn">
      <button v-on:click="changeComponent">Далее</button>
    </div>

    <div class="birthday__btnBack">
      <router-link to="/auth" class="back-link">Назад</router-link>
    </div>

  </div>
  <div v-else>
    <ConfirmPhoneNumber/>
  </div>
</template>


<script>
  import {defineComponent} from 'vue'
  import {ref} from 'vue'
  import ConfirmPhoneNumber from "./ConfirmPhoneNumber";

  export default defineComponent({
    name: 'Birthday',
    components: {
      ConfirmPhoneNumber
    },
    setup() {
      return {
        model: ref('сентября'),
        dateModel: ref(1),
        yearModel: ref(2020),
        options: [
          'января', 'февраля', 'марта', 'апреля', 'мая', 'июня', 'июля', 'августа', 'сентября',
          'октября', 'ноября', 'декабря'
        ],
        dateOptions: [
          1, 2, 3, 4, 5
        ],
        yearOptions: [2020, 2019, 2018]
      }
    },
    data() {
      return {
        currentComponent: 'birthday'
      }
    },
    methods: {
      changeComponent() {
        this.currentComponent = 'confirm'
      }
    }

  })
</script>
