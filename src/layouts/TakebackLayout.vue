<template>
  <q-layout view="hHh Lpr fff">
    <q-header reveal elevated class="bg-deep-purple-8 text-white">
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          @click="leftDrawerOpen = !leftDrawerOpen"
          aria-label="Menu"
        >
          <q-icon name="menu" />
        </q-btn>

        <q-toolbar-title>
          Linked Market - CMS
        </q-toolbar-title>

        <q-tabs shrink stretch>
          <q-route-tab class="text-subtitle2" label="반품확인중" to="/mails" exact />
          <q-route-tab class="text-subtitle2" label="반품진행중" to="/mails" exact />
          <q-route-tab class="text-subtitle2" label="반품환불진행" to="/mails" exact />
          <q-route-tab class="text-subtitle2" label="반품신청반려" to="/mails" exact />
        </q-tabs>

        <q-space />

        <div class="q-pl-md q-gutter-sm row no-wrap items-center">
          <q-btn round dense flat color="green-1" size="14px" icon="apps">
            <q-tooltip>Google Apps</q-tooltip>
          </q-btn>

          <q-btn round dense flat color="green-1" icon="notifications">
            <q-badge color="red" text-color="white" floating>
              2
            </q-badge>
            <q-tooltip>Notifications</q-tooltip>
          </q-btn>

          <q-btn round flat>
            <q-avatar size="26px">
              <img src="https://cdn.quasar.dev/img/boy-avatar.png">
            </q-avatar>
            <q-tooltip>Account</q-tooltip>
          </q-btn>
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      side="left"
      :width="260"
      bordered
      content-class="bg-grey-1"
    >
      <q-scroll-area class="fit">
        <q-list>
          <q-item-label header>{{ $t('title.productManage') }}</q-item-label>
          <q-item clickable tag="a" target="_blank" href="https://quasar.dev">
            <q-item-section avatar>
              <q-icon name="watch" />
            </q-item-section>
            <q-item-section>
              <q-item-label>{{ $t('title.productManage') }}</q-item-label>
              <q-item-label caption>{{ $t('title.productManageDesc') }}</q-item-label>
            </q-item-section>
          </q-item>
          <q-item clickable tag="a" target="_blank" href="https://github.quasar.dev">
            <q-item-section avatar>
              <q-icon name="notifications" />
            </q-item-section>
            <q-item-section>
              <q-item-label>{{ $t('title.productNoticeImageManage') }}</q-item-label>
              <q-item-label caption>{{ $t('title.productNoticeImageManageDesc') }}</q-item-label>
            </q-item-section>
          </q-item>

          <q-separator />

          <q-item-label header>{{ $t('title.orderManage') }}</q-item-label>

          <q-item clickable tag="a" target="_blank" href="https://chat.quasar.dev">
            <q-item-section avatar>
              <q-icon name="shopping_cart" />
            </q-item-section>
            <q-item-section>
              <q-item-label>Discord Chat Channel</q-item-label>
            </q-item-section>
          </q-item>
          <q-item clickable tag="a" target="_blank" href="https://forum.quasar.dev">
            <q-item-section avatar>
              <q-icon name="record_voice_over" />
            </q-item-section>
            <q-item-section>
              <q-item-label>Forum</q-item-label>
              <q-item-label caption>forum.quasar.dev</q-item-label>
            </q-item-section>
          </q-item>
          <q-item clickable tag="a" target="_blank" href="https://twitter.quasar.dev">
            <q-item-section avatar>
              <q-icon name="rss_feed" />
            </q-item-section>
            <q-item-section>
              <q-item-label>Twitter</q-item-label>
              <q-item-label caption>@quasarframework</q-item-label>
            </q-item-section>
          </q-item>
          <q-item clickable tag="a" target="_blank" href="https://facebook.quasar.dev">
            <q-item-section avatar>
              <q-icon name="public" />
            </q-item-section>
            <q-item-section>
              <q-item-label>Facebook</q-item-label>
              <q-item-label caption>@QuasarFramework</q-item-label>
            </q-item-section>
          </q-item>
        </q-list>
      </q-scroll-area>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer bordered class="bg-blue-grey-10 text-white">
      <q-toolbar>
        <q-toolbar-title class="text-subtitle2" style="text-align:right;">
          Copyright © 2019 트라이패스㈜
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>
  </q-layout>
</template>

<script>
import { openURL } from 'quasar'

export default {
  name: 'TakebackLayout',
  data () {
    return {
      leftDrawerOpen: false
    }
  },
  methods: {
    openURL
  }
}
</script>

<style>
</style>
