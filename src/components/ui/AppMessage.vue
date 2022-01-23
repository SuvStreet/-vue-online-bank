<template>
  <div v-if="message" :class="['alert', message.type]">
    <p class="alert-title" v-if="title">{{ title }}</p>
    <p>{{ message.value }}</p>
    <span class="alert-close" @click="close">&times;</span>
  </div>
</template>

<script>
import { computed } from '@vue/runtime-core'
import { useStore } from 'vuex'

export default {
  setup() {
    const store = useStore()
    const TITLE_MAP = {
      primary: 'Успешно!',
      danger: 'Ошибка!',
      warning: 'Внимание!',
    }

    const message = computed(() => {
      return store.state.message
    })
    const title = computed(() => {
      return message.value ? TITLE_MAP[message.value.type] : nul
    })

    return {
      title,
      message,
      close() {
        store.commit('clearMessage')
      },
    }
  },
}
</script>

<style></style>
