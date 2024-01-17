<template>
    <header class="hidden lg:flex shadow-lg items-center justify-between gap-4 py-2 px-6">
      <div class="flex flex-grow items-center gap-4 py-2 px-6">
        <div class="logo">
          <img 
            src="https://www.udemy.com/staticx/udemy/images/v7/logo-udemy.svg" 
            width="91" 
            height="34" 
            alt=""
          >
        </div>
        <button>
          <span class="text-sm">Категории</span>
        </button>
        <form action="" class="border flex-1 rounded-full px-2 overflow-hidden gap-2 flex">
          <button class="">
            <img class="min-w-[24px] h-[24px] object-cover ojbect-center" src="../../assets/search-form/free-icon-magnifying-glass-1209875.png" alt="">
          </button>
          <input class="focus:outline-none border-none text-lg w-full py-2" type="text" placeholder="Ищите что угодно">
        </form>
        <a href="#"><span class="text-sm">Преподавайте на Udemy</span></a>
        <img src="../../assets/header/shopping-cart.png" alt="cart">
      </div>
      <div class="buttons flex items-center gap-3">
        <PrimaryButton @click="handleClick" variant="inverted">Вход</PrimaryButton>
        <PrimaryButton variant="default">Регистрация</PrimaryButton>
      </div>
    </header>
    <header class="py-4 px-4 flex lg:hidden items-center justify-between">
      <div class="mobile-menu flex justify-center flex-col h-[30px] w-[20px] gap-1">
        <span class="bar bg-color-gray-500 w-full h-[3px]"></span>
        <span class="bar bg-color-gray-500 w-full h-[3px]"></span>
        <span class="bar bg-color-gray-500 w-full h-[3px]"></span>
      </div>
      <div class="">
        <img 
          src="https://www.udemy.com/staticx/udemy/images/v7/logo-udemy.svg" 
          width="91" 
          height="34" 
          alt=""
        >
      </div>
      <div class="flex items-center gap-10">
        <img class="min-w-[24px] h-[24px] object-cover ojbect-center" src="../../assets/search-form/free-icon-magnifying-glass-1209875.png" alt="">
        <img src="../../assets/header/shopping-cart.png" alt="cart">
      </div>
    </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

import PrimaryButton from '../button/PrimaryButton.vue';

export default defineComponent({
  components: {
    PrimaryButton
  },
  methods: {
    handleClick() {
      this.$emit('isModalOpen', true)
    }
  }
})
</script>