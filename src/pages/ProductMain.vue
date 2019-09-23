<template>
  <q-page>
    <div class="q-pa-md">
      <h5 class="text-h5 q-mt-md q-mb-md">언어설정</h5>
      <q-card class="q-pa-lg shadow-1">
        <q-select
          label="Select Language"
          v-model="lang"
          map-options
          :options="langs"
          class="row"
        />
        <div class="row q-pt-md">
          Phrase for Product Manage: {{ $t('title.productManage') }}
        </div>
        <div class="row q-pt-md">
          Phrase for Order Manage: {{ $t('title.orderManage') }}
        </div>
        <div class="row q-pt-md">Current Language: {{ $i18n.locale }}</div>
      </q-card>
    </div>
    <h2 class="text-purple-6 q-pa-md q-ma-sm bold">Vue Prototypes</h2>
    <div class="q-pa-md">
      <h5 class="text-h5 q-ma-sm">Platform</h5>
      <q-card class="q-pa-md">
        <ul class="q-mt-sm">
          <li v-for="(val, key) in $q.platform.is" v-bind:key="key">
            {{ key }} : {{ val }}
          </li>
        </ul>
      </q-card>
    </div>
    <div class="q-pa-md">
      <h5 class="text-h5 q-mb-sm">Screen</h5>
      <q-card class="q-pa-md">
        <ul class="q-mt-sm">
          <li v-for="(val, key) in $q.screen" v-bind:key="key">
            {{ key }} : {{ val }}
          </li>
        </ul>
      </q-card>
    </div>
    <div class="q-pa-md">
      <h5 class="text-h5 q-mb-sm">Lang, IconSet</h5>
      <q-card class="q-pa-md">
        <p>getLocale : {{ $q.lang.getLocale() }}</p>
        <p>
          iconSet config :
          <code>
            <pre>
              //quasar.conf.js
              extras: [ 'ionicons-v4', 'fontawesome-v5' ],
              framework: { iconSet: 'fontawesome-v5' }
            </pre>
          </code>
          iconSet dynamic change :
          <code>
            this.$q.iconSet =
            require('quasar/icon-set/fontawesome-v5.js').default
          </code>
        </p>
        <p>
          icon Sample : material(default) :
          <q-icon name="contactless" size="md" />
          material-outlined :
          <q-icon name="o_contactless" size="lg" />
          fontawesome :
          <q-icon name="fas fa-ambulance" size="xl" />
        </p>
      </q-card>
    </div>
  </q-page>
</template>

<style></style>

<script>
export default {
  name: 'PageIndex',
  data () {
    return {
      langs: [
        {
          label: '한국어',
          value: 'kr'
        },
        {
          label: 'US English',
          value: 'en-us'
        }
      ],
      lang: this.$i18n.locale
    }
  },
  mounted: function () {
    // console.log(this.$q.platform.is)
    // console.log(this.$q.lang)
    // console.log(this.$q.iconSet)
  },
  watch: {
    lang (lang) {
      this.$i18n.locale = lang.value
      // set quasar's language too!!
      import(`quasar/lang/${lang.value}`).then(language => {
        this.$q.lang.set(language.default)
      })
    }
  }
}
</script>
