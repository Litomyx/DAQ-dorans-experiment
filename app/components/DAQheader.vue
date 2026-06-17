<script setup lang="ts">
import type { NavigationMenuItem } from '@nuxt/ui'

const route = useRoute()

const items = computed<NavigationMenuItem[]>(() => [
  {
    label: 'Leaderboard',
    to: '/leaderboard',
    active: route.path.startsWith('/leaderboard')
  },
  {
    label: 'Quest board',
    to: '/quests',
    active: route.path.startsWith('/quests')
  },
  {
    label: 'Admin',
    to: '/admin',
    active: route.path.startsWith('/admin')
  },
  {
    label: 'Calendar',
    to: '/calendar',
    active: route.path.startsWith('/calendar')
  }
])
</script>

<template>
  <UHeader>
    <template #title>
      <Logo class="h-6 w-auto" />
    </template>
    <UNavigationMenu :items="items" />
    <template #right>
      <UColorModeButton />
    </template>
  </UHeader>
</template>

