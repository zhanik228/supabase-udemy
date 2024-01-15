<template>
    <header class="container mx-auto flex items-center justify-between gap-4 py-2 px-6">
      <div class="flex items-center gap-4 py-2 px-6">
        <div class="logo">
          <img 
            src="https://www.udemy.com/staticx/udemy/images/v7/logo-udemy.svg" 
            width="91" 
            height="34" 
            alt=""
          >
        </div>
        <button>
          <span class="text-xl">Категории</span>
        </button>
        <form action="" class="border w-[500px] rounded-full px-2 overflow-hidden gap-2 flex">
          <button class="">
            <img class="min-w-[24px] h-[24px] object-cover ojbect-center" src="../../assets/search-form/free-icon-magnifying-glass-1209875.png" alt="">
          </button>
          <input class="focus:outline-none border-none text-lg w-full py-2" type="text" placeholder="Ищите что угодно">
        </form>
        <a href="#"><span class="text-lg">Преподавайте на Udemy</span></a>
      </div>
      <div class="buttons flex items-center gap-3">
        <PrimaryButton @onClick="handleClick" variant="inverted">Вход</PrimaryButton>
        <PrimaryButton variant="default">Регистрация</PrimaryButton>
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