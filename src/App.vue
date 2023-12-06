<template>
  <div id="app">
    <Header title='Welcome to PBBT'/>
    
    <div>
      <GetStarted />
    </div>

    <div>
      <BudgetTracking/>
    </div>

    <div class="container">
      <Pricing/>
    </div>

  </div>
</template>


<script>
import GetStarted from './components/GetStarted.vue'
import Header from './components/Header.vue'
import BudgetTracking from './components/BudgetTracking.vue'
import Pricing from './components/Pricing.vue'


export default {
  name: 'App',
  components:{
    Header,
    GetStarted,
    BudgetTracking,
    Pricing
  }  
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Poppins', sans-serif;
}



.hidden{
  visibility: hidden;
}

.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}

.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}

.btn:focus {
  outline: none;
}

.btn:active {
  transform: scale(0.98);
}

.btn-block {
  display: block;
  width: 100%;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}

.check{
        border: 1px solid black;
    }
</style>
