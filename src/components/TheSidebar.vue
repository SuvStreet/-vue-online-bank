<template>
  <div class="sidebar" v-if="sidebar">
    <span class="sidebar-close" @click="closeSidebar">&times;</span>

    <div class="sidebar-content">
      <p>
        Добро пожаловать в систему по учёту заявок в нашем банке. Здесь вы
        найдёте исчерпывающую информацию о нашем банке, а также можете создать
        заявку на получение денег.
      </p>
    </div>
  </div>
</template>

<script>
import { computed } from 'vue'
import { useStore } from 'vuex'

export default {
  setup() {
    const store = useStore()

    const sidebar = computed(() => store.state.sidebar)
    return { sidebar, closeSidebar: () => store.commit('closeSidebar') }
  },
}
</script>

<style></style>
