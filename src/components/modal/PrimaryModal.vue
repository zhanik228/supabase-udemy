<template>
    <div v-if="isActive" @click="closeModal" class="fixed inset-0 w-full h-full bg-color-gray-500 bg-opacity-35 flex items-center justify-center">
        <div @click.stop class="content p-10 h-[450px] bg-[#fff]">
            <form class="flex items-center justify-between flex-col h-full">
                <h2 class="text-lg self-start font-bold">Вход в учетную запись Udemy</h2>
                <div class="flex flex-col gap-10 w-[200px] sm:w-[350px]">
                    <input v-model="email" class="w-full my-2 text-lg placeholder:text-color-gray-500 placeholder:font-bold py-2 px-2 border border-color-gray-500" type="email" required placeholder="Адрес электронной почты">
                    <input v-model="password" class="w-full my-2 text-lg placeholder:text-color-gray-500 placeholder:font-bold py-2 px-2 border border-color-gray-500" type="password" required placeholder="Пароль">
                </div>
                <PrimaryButton @click="createAccount" class="w-full" variant="purple">Войти</PrimaryButton>
            </form>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { supabase } from '../../clients/supabase';


import PrimaryButton from '../button/PrimaryButton.vue';

export default defineComponent({
    components: {
        PrimaryButton
    },
    data() {
        return {
            email: '',
            password: '',
        }
    },
    props: {
        isActive: {
            type: Boolean,
        },
        modalMode: {
            required: false,
            type: String
        }
    },
    methods: {
        closeModal() {
            this.$emit('update:isActive', false)
        },
        async createAccount(event: Event) {
            event.preventDefault();
            const { data, error } = await supabase.auth.signUp({
                email: this.email,
                password: this.password,
            })
            if (error) {
                console.log(error)
            } else {
                console.log(data)
            }
        }
    }
})
</script>