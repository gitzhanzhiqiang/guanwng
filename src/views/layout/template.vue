<template>
  <div>
    <header-nav></header-nav>
    <div>
      <router-view></router-view>
    </div>
    <footer-nav style="height:232px;width: 100%;"></footer-nav>
  </div>
</template>
<script>
import headerNav from './header.vue';
import mainNav from './mainNav.vue';
import footerNav from './footerNav.vue';
  export default {
  components: {
    headerNav,
    mainNav,
    footerNav
  },
  computed: {
  },
  data(){
    return{
    }
  },
  created() {
  },
  methods: {
    
  	
  }
}
</script>
<style type="text/css">
</style>