<script setup lang="ts">
// import HomeLayout from '@renderer/layout/index.vue'
// Trigger auto-import regeneration
</script>

<template>
  <div class="home">
    <HomeLayout>
      <template #body>
        <router-view v-slot="{ Component }">
          <Transition
            name="page"
            :enter-active-class="`router-fadeIn`"
            :leave-active-class="`router-fadeOut`"
            mode="out-in"
          >
            <KeepAlive exclude="list">
              <component :is="Component" />
            </KeepAlive>
          </Transition>
        </router-view>
      </template>
    </HomeLayout>
    <PlayMusic />
  </div>
</template>
