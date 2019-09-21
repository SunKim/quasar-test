<template>
  <q-page class="flex">
    <div class="q-pa-md">
      <h5 class="text-h5 q-mt-md q-mb-md">언어설정</h5>
      <q-select label="Select Language" v-model="lang" map-options :options="langs" class="row"/>
      <div class="row q-pt-md">Phrase for Product Manage: {{ $t('title.productManage') }}</div>
      <div class="row q-pt-md">Phrase for Order Manage: {{ $t('title.orderManage') }}</div>
      <div class="row q-pt-md">Current Language: {{ $i18n.locale }}</div>
    </div>
  </q-page>
</template>

<style>
</style>

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
