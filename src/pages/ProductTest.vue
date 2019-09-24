<template>
  <div class="q-pa-md">
    <div>
      <h4 class="q-ma-sm">Transition</h4>
      <p class="text-subtitle1 text-info">
        DefaultLayout의 &lt;router-view&gt; transition도 이렇게
        구현(mode="out-in" 포함)
      </p>
      <p class="text-subtitle1 text-info">
        전체 animation 종류는
        <a target="_blank" href="https://daneden.github.io/animate.css/">
          Animate.css
        </a>
        참고
      </p>
      <!-- Example with wrapping only one DOM element / component -->
      <transition
        appear
        enter-active-class="animated fadeInDown"
        leave-active-class="animated fadeOutDown"
      >
        <!-- Wrapping only one DOM element, defined by QBtn -->
        <q-btn
          color="secondary"
          icon="mail"
          label="Click to Animate"
          v-show="isVisible"
          @click="hide"
        />
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProductTest',
  // Options / Data
  data () {
    return {
      isVisible: true
    }
  },
  // props: [],
  // propsData: {},
  // computed: {},
  methods: {
    hide: function () {
      this.isVisible = false
      const _self = this
      setTimeout(function () {
        _self.isVisible = true
      }, 1000)
    }
  }
  // watch: {},
  // Options / DOM
  // el () {},
  // template: '',
  // render () {},

  // Options / Lifecycle Hooks
  // beforeCreate () {},
  // created () {},
  // beforeMount () {},
  // mounted () {},
  // beforeUpdate () {},
  // updated () {},
  // activated () {},
  // deactivated () {},
  // beforeDestroy () {},
  // destroyed () {},

  // Options / Assets
  // directives: {},
  // filters: {},
  // components: {},

  // Options / Misc
  // parent: null,
  // mixins: [],
  // name: '',
  // extends: {},
  // delimiters: [ '{{', '}}' ],
  // functional: false
}
</script>
