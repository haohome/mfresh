<template>
  <div id="app">
    <Mf-header/>
    <Mf-nav/>
    <router-view/>
    <footer class="footer">
      <Mf-footer/>
    </footer>
  </div>
</template>

<script>
/*引入公共组件:Header,Nav,Footer*/
import Header from './components/common/Header'
import Nav from './components/common/Nav'
import Footer from './components/common/Footer'
export default {
  name: 'App',
  components: {
    'Mf-header': Header,
    'Mf-footer': Footer,
    'Mf-nav': Nav
  },
}
</script>

<style>

</style>
