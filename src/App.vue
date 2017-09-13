<template>
  <div id="app">
     <Topbar class="topbar" />
	 <main>
       <Editor class="editor" />
       <Preview  class="preview"/>
	 </main>
  </div>
</template>

<script>

import Topbar from './components/Topbar'
import Editor from './components/Editor'
import Preview from './components/Preview'
export default {
  components: { 
	Topbar,
	Editor,
	Preview
  }
}
</script>

<style lang="scss">
*{margin:0px;padding:0px;}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  height:100%;
  display:flex;
  flex-direction:column;
  height:100vh;
}
main {
display:flex;
flex:1;
   > .editor{
width:20em;
}
   > .preview{
flex:1;
   }
}
</style>
