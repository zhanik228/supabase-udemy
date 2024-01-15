
<template>
  <PrimaryModal v-model:is-active="isModalActive" />
  <PrimaryHeader @isModalOpen="handleModalOpen" />
  <RouterView />
</template>

<script lang="ts">
import { defineComponent } from 'vue';

import PrimaryHeader from './components/header/PrimaryHeader.vue';
import PrimaryModal from '@/components/modal/PrimaryModal.vue'

export default defineComponent({
  components: {
    PrimaryHeader,
    PrimaryModal
  },
  data() {
    return {
      isModalActive: false,
    }
  },
  methods: {
    handleModalOpen(value: boolean) {
      if (value) {
        this.isModalActive = true
      }
    }
  }
})
</script>