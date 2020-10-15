<template>
    <div>
        <Navbar/>
        <Header/>
        <Calculator/>
    </div>
</template>




<script>

import Navbar from '../components/Navbar'
import Header from '../components/Header'
import Calculator from '../components/Calculator'
export default {
  name: 'App',
  components: {
   Navbar,
   Header,
   Calculator
  }
}
</script>