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
.icon {
    
    vertical-align: -0.15em;
    fill: currentColor;
    overflow: hidden;
    }
.topbar{
box-shadow:0 0 3px hsla(0,0,0,0.5);
z-index:1;
}
main {
display:flex;
flex:1;
background:#ddd;
   > .editor{
width:30em;
margin:16px 8px 16px 16px;
background:white;
box-shadow:0 0 3px hsla(0,0,0,0.5);
border-radius:4px;
overflow:hidden;
}
   > .preview{
flex:1;
margin:16px 16px 16px 8px;
background:white;
box-shadow:0 0 3px hsla(0,0,0,0.5);
   }
}
</style>
