<template>
    <div v-if="isActive" @click="closeModal" class="fixed inset-0 w-full h-full bg-color-gray-500 bg-opacity-35 flex items-center justify-center">
        <div @click.stop class="content p-10 h-[450px] bg-[#fff]">
            <form class="flex items-center justify-between flex-col h-full">
                <h2 class="text-lg self-start font-bold">Вход в учетную запись Udemy</h2>
                <div class="flex flex-col gap-10 w-[200px] sm:w-[350px]">
                    <input class="w-full my-2 text-lg placeholder:text-color-gray-500 placeholder:font-bold py-2 px-2 border border-color-gray-500" type="email" required placeholder="Адрес электронной почты">
                    <input class="w-full my-2 text-lg placeholder:text-color-gray-500 placeholder:font-bold py-2 px-2 border border-color-gray-500" type="password" required placeholder="Пароль">
                </div>
                <PrimaryButton class="w-full" variant="purple">Войти</PrimaryButton>
            </form>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

import PrimaryButton from '../button/PrimaryButton.vue';

export default defineComponent({
    components: {
        PrimaryButton
    },
    props: {
        isActive: {
            type: Boolean,
        }
    },
    methods: {
        closeModal() {
            this.$emit('update:isActive', false)
        }
    }
})
</script>