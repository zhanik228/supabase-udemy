<template>
    <button
        :class="`inline-block py-2 px-3 text-lg border border-color-gray-500
        ${variant == 'default' ? 
        ' bg-color-gray-500  text-[#fff]' 
        :  variant === 'purple' ?
            'border-color-purple-500 bg-color-purple-500 text-[#fff]'
        :
        ' '} hover:opacity-60
        `"
        @click="$emit('onClick')"
    >
        <slot></slot>
    </button>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'

interface Variants {
    variant: 'default' | 'inverted' | 'purple'
}

export default defineComponent({
    props: {
        variant: {
            type: String as PropType<Variants['variant']>,
            default: 'default',
        }
    }
})
</script>