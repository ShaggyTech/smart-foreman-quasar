<template>
  <q-layout view="lHh lpR fFr">
    <q-header elevated>
      <q-toolbar class="text-white fit row items-center justify-between">
        <div class="self-start q-my-auto">
          <q-btn
            stretch
            flat
            round
            icon="menu"
            aria-label="Menu"
            @click="leftDrawerOpen = !leftDrawerOpen"
          />
          <q-separator inset size="4px" vertical />
        </div>
        <q-toolbar-title class="column items-center justify-center q-mx-md">
          <q-icon name="img:icons/smart-foreman-logo.svg" :size="iconSize"></q-icon>Smart Foreman
        </q-toolbar-title>
        <div class="self-end q-my-auto">
          <q-btn
            stretch
            flat
            round
            icon="menu"
            aria-label="Menu"
            @click="leftDrawerOpen = !leftDrawerOpen"
          />
          <q-separator inset size="4px" vertical />
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered content-class="bg-grey-1">
      <q-list>
        <q-item-label header class="text-grey-8">Essential Links</q-item-label>
        <EssentialLink v-for="link in essentialLinks" :key="link.title" v-bind="link" />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script lang="ts">
import EssentialLink from 'components/EssentialLink.vue';

const linksData = [
  {
    title: 'Docs',
    caption: 'quasar.dev',
    icon: 'school',
    link: 'https://quasar.dev',
  },
  {
    title: 'Github',
    caption: 'github.com/quasarframework',
    icon: 'code',
    link: 'https://github.com/quasarframework',
  },
  {
    title: 'Discord Chat Channel',
    caption: 'chat.quasar.dev',
    icon: 'chat',
    link: 'https://chat.quasar.dev',
  },
  {
    title: 'Forum',
    caption: 'forum.quasar.dev',
    icon: 'record_voice_over',
    link: 'https://forum.quasar.dev',
  },
  {
    title: 'Twitter',
    caption: '@quasarframework',
    icon: 'rss_feed',
    link: 'https://twitter.quasar.dev',
  },
  {
    title: 'Facebook',
    caption: '@QuasarFramework',
    icon: 'public',
    link: 'https://facebook.quasar.dev',
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'favorite',
    link: 'https://awesome.quasar.dev',
  },
];

import { computed, defineComponent, ref, Ref } from '@vue/composition-api';

// interface ViewPort {
//   /* width of viewport (in px) */
//   width: number;
//   /* height of viewport (in px) */
//   height: number;
// }

// type IconSize = '64px' | '96px' | '120px';

export default defineComponent({
  name: 'MainLayout',
  components: { EssentialLink },
  setup(_, { root: { $q } }) {
    const leftDrawerOpen: Ref<boolean> = ref(false);
    const essentialLinks = ref(linksData);
    // const viewport: ComputedRef<ViewPort> = computed(() => ({
    //   height: $q.screen.height || 0,
    //   width: $q.screen.width || 0,
    // }));
    const iconSize = computed(() => {
      let size = 48;
      if ($q.screen.height < 400) return `${36}px`;
      switch ($q.screen.name) {
        case 'sm':
          size = 64;
        case 'md':
          size = 96;
          break;
        case 'lg':
          size = 120;
          break;
        case 'xl':
          size = 164;
          break;
      }
      return `${size}px`;
    });

    return { iconSize, leftDrawerOpen, essentialLinks };
  },
});
</script>
