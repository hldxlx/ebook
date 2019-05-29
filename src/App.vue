<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
<script>
  import {mapGetters} from 'vuex'
  const getters = {
    a:() =>1,
    b:() =>2
  }
  function fn(keys) {
    const data = {}
    keys.forEach(key => {
        if(getters.hasOwnProperty(key)){
          data[key] = getters[key];
        }
    })
    return data
  }
    export default{
        computed:{
          ...mapGetters(['test']),
          ...fn(['a','b'])
        },
        mounted(){
//            console.log(this.fn())
//            console.log({
//                ...this.fn(),
//                c:3,
//                d:4
//            })
          console.log(this.a,this.b,this.c)

            this.$store.dispatch('setTest',10).then(() =>{
                console.log(this.test)
            })
        }
    }
</script>
