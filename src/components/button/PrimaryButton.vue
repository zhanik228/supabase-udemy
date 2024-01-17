<template>
    <button
        :class="`inline-block py-2 px-3 text-sm border border-color-gray-500
        ${variant == 'default' ? 
        ' bg-color-gray-500  text-[#fff]' 
        :  variant === 'purple' ?
            'border-color-purple-500 bg-color-purple-500 text-[#fff]'
        :
        ' '} hover:opacity-60
        `"
        @click="click"
        type="button"
    >
        <slot></slot>
    </button>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'

interface Variants {
    variant: 'default' | 'inverted' | 'purple'
}

interface Type {
    type: 'button' | 'submit',
}

export default defineComponent({
    props: {
        variant: {
            type: String as PropType<Variants['variant']>,
            default: 'default',
        },
        type: {
            type: String as PropType<Type['type']>
        },
        click: {
            type: Function as PropType<(event: MouseEvent) => void>,
            required: false,
        }
    }
})
</script>