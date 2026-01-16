<template>
  <q-layout view="lHh Lpr lFf">
    <q-header
      elevated
      class="bg-black text-white"
      style="border-bottom: 1px solid rgba(255, 255, 255, 0.1)"
    >
      <q-toolbar class="q-py-sm">
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
          class="q-mr-md"
        />

        <q-toolbar-title class="text-weight-bold row items-center">
          <q-icon name="diversity_3" size="32px" color="secondary" class="q-mr-sm" />
          <span class="text-h6">CRM <span class="text-secondary">Pro</span></span>
        </q-toolbar-title>

        <div class="q-gutter-sm row items-center">
          <q-btn flat round dense icon="notifications">
            <q-badge color="secondary" floating>3</q-badge>
          </q-btn>
          <q-btn flat round dense icon="settings" />
          <q-avatar size="36px" class="cursor-pointer q-ml-sm">
            <img src="https://cdn.quasar.dev/img/boy-avatar.png" />
          </q-avatar>
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      :width="260"
      class="bg-dark-page text-white"
      elevated
    >
      <div class="column full-height">
        <div class="q-pa-md q-mb-md">
          <div class="text-overline text-grey-6 q-pl-sm">MENU</div>
        </div>

        <q-list padding class="menu-list q-px-sm">
          <q-item
            v-for="link in linksList"
            :key="link.title"
            clickable
            v-ripple
            class="menu-item q-mb-sm rounded-borders"
            :active="link.active"
          >
            <q-item-section avatar>
              <q-icon
                :name="link.icon"
                size="24px"
                :color="link.active ? 'secondary' : 'white'"
                class="menu-icon"
              />
            </q-item-section>

            <q-item-section>
              <q-item-label
                class="text-weight-bold text-white"
                style="font-size: 1.1rem; letter-spacing: 0.5px"
                >{{ link.title }}</q-item-label
              >
              <q-item-label caption class="text-red-2">{{ link.caption }}</q-item-label>
            </q-item-section>

            <q-item-section side v-if="link.active">
              <q-icon name="chevron_right" color="secondary" size="xs" />
            </q-item-section>
          </q-item>
        </q-list>

        <q-space />

        <div class="q-pa-md text-center">
          <div class="glass-card q-pa-md rounded-borders">
            <q-icon name="support" size="md" color="secondary" class="q-mb-sm" />
            <div class="text-caption text-grey-4">Need Help?</div>
            <div class="text-caption text-weight-bold">Contact Support</div>
          </div>
        </div>
      </div>
    </q-drawer>

    <q-page-container class="bg-dark">
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'

const linksList = [
  {
    title: 'Dashboard',
    caption: 'Overview & Stats',
    icon: 'dashboard',
    link: '#',
    active: true,
  },
  {
    title: 'Customers',
    caption: 'Manage Client Base',
    icon: 'people',
    link: '#',
    active: false,
  },
  {
    title: 'Leads',
    caption: 'Potential Opportunities',
    icon: 'leaderboard',
    link: '#',
    active: false,
  },
  {
    title: 'Analytics',
    caption: 'Performance Reports',
    icon: 'trending_up',
    link: '#',
    active: false,
  },
  {
    title: 'Messages',
    caption: 'Direct Chats',
    icon: 'chat',
    link: '#',
    active: false,
  },
  {
    title: 'Settings',
    caption: 'System Configuration',
    icon: 'settings',
    link: '#',
    active: false,
  },
]

const leftDrawerOpen = ref(false)

function toggleLeftDrawer() {
  leftDrawerOpen.value = !leftDrawerOpen.value
}
</script>

<style lang="scss" scoped>
.menu-item {
  transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
  background: transparent;
  transform-style: preserve-3d;
  perspective: 1000px;
  position: relative;
  border-left: 3px solid transparent;
}

.menu-item:hover {
  transform: translateX(10px) scale(1.02);
  background: linear-gradient(90deg, rgba(255, 255, 255, 0.03), rgba(255, 255, 255, 0.08));
  box-shadow: -5px 5px 15px rgba(0, 0, 0, 0.5);
  border-left: 3px solid $secondary;
  z-index: 10;
}

.menu-item .menu-icon {
  transition: transform 0.4s ease;
}

.menu-item:hover .menu-icon {
  transform: scale(1.2) translateZ(20px);
  filter: drop-shadow(0 0 5px $secondary);
}

.menu-item:hover .q-item__label {
  color: #fff !important;
  text-shadow: 0 0 8px rgba(255, 255, 255, 0.6);
}

.glass-card {
  background: rgba(255, 255, 255, 0.03);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.05);
}
</style>
