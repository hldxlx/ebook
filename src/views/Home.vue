<template>
  <div class="home">
    aa
  </div>
</template>

<script>
// @ is an alias to /src
import Epub from 'epubjs'
global.ePub = Epub

export default {
  name: 'home',
  mounted(){
      this.book = new Epub('');
      this.book.renderTo('read',{
          width:window.innerWidth,
          height:window.innerHeight0
      }).display()
  }
}
</script>
