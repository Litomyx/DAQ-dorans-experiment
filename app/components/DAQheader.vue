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
    active: route.path.startsWith('/leaderboard')
  },
  {
    label: 'Admin',
    to: '/admin',
    active: route.path.startsWith('/admin')
  },
  {
    label: 'Calendar',
    to: '/calendar',
    active: route.path.startsWith('/admin')
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

      <UTooltip text="Open on GitHub" :kbds="['meta', 'G']">
        <UButton
          color="neutral"
          variant="ghost"
          to="https://github.com/nuxt/ui"
          target="_blank"
          icon="i-simple-icons-github"
          aria-label="GitHub"
        />
      </UTooltip>
    </template>
  </UHeader>
</template>

