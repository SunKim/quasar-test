<template>
  <q-page padding class="flex flex-center">
    <div>
      <h4 class="text-h4">Login</h4>
      <q-field icon="mail" error-label="A valid email address is needed">
        <!--
        <q-input v-model="credentials.email" placeholder="Your email address" @blur="$v.credentials.email.$touch" :error="$v.credentials.email.$error" class="full-width" ref="email" />
        -->
        <q-input v-model="email" placeholder="이메일" @blur="checkEmail" class="full-width" ref="email" />
      </q-field>
      <q-field icon="vpn_key">
        <q-input v-model="password" type="password" placeholder="패스워드" @blur="checkPassword" class="full-width" />
      </q-field>

      <div class="submit row q-mt-md">
        <q-btn color="primary" @click="submit()">Login</q-btn>
      </div>
    </div>
  </q-page>
</template>

<script>
export default {
  name: 'Login',
  data () {
    return {
      email: '',
      password: ''
    }
  },
  mounted () {
    // on next Vue tick, to ensure
    // our Vue reference exists
    this.$nextTick(() => {
      // calling "next()" method:
      this.$refs.email.focus()
    })
  },
  // validations: {
  //   credentials: {
  //     email: { required, email },
  //     password: { required, minLength: minLength(6) }
  //   }
  // },
  methods: {
    checkEmail () {

    },
    checkPassword () {

    },
    submit () {
      this.$v.credentials.$touch()
      if (this.$v.credentials.$error) {
        // Toast.create('Please review fields again.')
        console.log(this.$v.credentials.$error)
        // return
      }
      // auth.login(this.credentials, 'profile')
    }
  }
}
</script>

<style>
</style>
