<template>
  <div id="app">
    <HomePage></HomePage>
    <Quote></Quote>
  </div>
</template>

<script>
  import Header from './components/Header'
  import HomePage from './components/homePage'
  import Quote from './components/quote'
export default {
  name: 'App',
  components:{
    Header,
    HomePage,
    Quote
  }
}
</script>

<style>


</style>
