<template>
  <q-layout view="lHh Lpr lFf">

    <q-page-sticky class="sticky" position="top-left" :offset="[18, 18]" :content-style="{color:'red'}">
      <q-btn round color="primary" @click="alertHandler" icon="alarm" />
    </q-page-sticky>

    <!-- Header內容 -->
    <q-header elevated>
      <q-toolbar class="bg-primary text-white">
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />

      <q-avatar>
        <img src="https://cdn.quasar.dev/logo/svg/quasar-logo.svg">
      </q-avatar>

        <q-toolbar-title>
          S2 FORWARDER
          <!-- TODO: -->
          <div slot="subtitle">asdasd</div>
        </q-toolbar-title>

                <div class="gt-xs">
          <q-btn flat class="q-mr-md">HOME</q-btn>
          <q-btn flat class="q-mr-md">SERVICES</q-btn>
          <q-btn flat class="q-mr-md">INDUSTRIES</q-btn>
          <q-btn flat class="q-mr-md">LOGIN</q-btn>
          <q-btn flat class="q-mr-md">SIGN UP</q-btn>
        </div>

        <!-- <div>Quasar v{{ $q.version }}</div> -->
      </q-toolbar>
    </q-header>

    <!-- 可選, 左側欄的內容 -->
    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label
          header
          class="text-grey-8"
        >
          Essential Links
        </q-item-label>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <!-- 必要 -->
    <q-page-container>
      <!-- 頁面容器，頁面都放在這下面，
      容器內的第一個頁面的外層一定要用 <q-page> 包起來，之後就能透過 vue router 渲染頁面了
      -->
      <router-view />
    </q-page-container>

    <!-- 加上 footer 來看看 -->
          <q-footer>
        <q-toolbar>
          <q-toolbar-title>Footer</q-toolbar-title>
        </q-toolbar>
      </q-footer>

            <q-drawer
        v-model="drawerLeft"
        :width="200"
        :breakpoint="700"
        bordered
        content-class="bg-grey-3"
      >
        <q-scroll-area class="fit">
          <div class="q-pa-sm">
            <div v-for="n in 20" :key="n">Drawer {{ n }} / 20</div>
          </div>
        </q-scroll-area>
      </q-drawer>

      <q-drawer
        side="right"
        v-model="drawerRight"
        bordered
        :width="200"
        :breakpoint="500"
        content-class="bg-grey-3"
      >
        <q-scroll-area class="fit">
          <div class="q-pa-sm">
            <div v-for="n in 20" :key="n">Drawer {{ n }} / 20</div>
          </div>
        </q-scroll-area>
      </q-drawer>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksData = [
  {
    title: 'Docs',
    caption: 'quasar.dev',
    icon: 'school',
    link: 'https://quasar.dev'
  },
  {
    title: 'Github',
    caption: 'github.com/quasarframework',
    icon: 'code',
    link: 'https://github.com/quasarframework'
  },
  {
    title: 'Discord Chat Channel',
    caption: 'chat.quasar.dev',
    icon: 'chat',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'Forum',
    caption: 'forum.quasar.dev',
    icon: 'record_voice_over',
    link: 'https://forum.quasar.dev'
  },
  {
    title: 'Twitter',
    caption: '@quasarframework',
    icon: 'rss_feed',
    link: 'https://twitter.quasar.dev'
  },
  {
    title: 'Facebook',
    caption: '@QuasarFramework',
    icon: 'public',
    link: 'https://facebook.quasar.dev'
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'favorite',
    link: 'https://awesome.quasar.dev'
  }
]

export default {
  name: 'MainLayout',
  components: { EssentialLink },
  data () {
    return {
      leftDrawerOpen: false,
      essentialLinks: linksData,
      drawerLeft: false,
      drawerRight: true,
      subtitle: 'Take a break ...' // TODO:

    }
  },
  methods: {
    alertHandler () {
      alert('TEST')
    }
  }
}
</script>

<style lang="scss">
  // :content-style="{color:'red'}"

  // .sticky{
  //   cursor: pointer;
  // }

</style>
