<template>
  <div class="containe-r">
    <headerC></headerC>
    <searcherC></searcherC>
    <loginC></loginC>
    <footerC></footerC>
  </div>
</template>

<script>

import loginC from '~/components/auth/loginC'
import { headerC, footerC, searcherC } from '~/components/common'
import { mapActions } from 'vuex'

export default{
  data () {
    return {}
  },
  components: {
    headerC,
    loginC,
    footerC,
    searcherC
  },
  computed: {
    ...mapActions(['bindAuth', 'unbindFirebaseReferences'])
  },
  created () {
    this.bindAuth
  },
  destroyed () {
    this.unbindFirebaseReferences
  }
}
</script>

<style media="screen">
img{width: 100%;}

@media screen and (min-width: 750px) {
  .containe-r{
    width: 100%;
    display:flex;
	  flex-flow:row wrap;
  }
}
</style>
