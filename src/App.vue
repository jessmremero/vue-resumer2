<template>
  <div id="app" v-bind:class="{ previewMode:previewMode}">
     <Topbar class="topbar" v-on:preview="preview" />
	 <main>
       <Editor v-bind:resume="resume" class="editor" />
       <Preview v-bind:resume="resume" class="preview"/>
	 </main>
	 <el-button id="exitPreview" v-on:click="exitPreview">exit</el-button>
  </div>
</template>


<script>

import Topbar from './components/Topbar'
import Editor from './components/Editor'
import Preview from './components/Preview'
export default {
  data(){
     return{
	 previewMode: false,
	 resume:{
	  profile:{name:"",birth:"",city:""},
      workHistory:[{company:'',content:''},],
      studyHistory:[{school:'',duration:'',degree:''}],
      projectHistory:[{name:'',content:'',skill:''}],
      rewardHistory:[{name:''}], 
      contact:{QQ:"",wechat:"",email:"",telephone:""},   	  
	   }
	 }
  },
  methods:{
    exitPreview(){
	  this.previewMode = false
	},
    preview(){
	  this.previewMode = true
	}
  },
  components: { Topbar,Editor,Preview
  },
  created(){
  this.$on('preview',()=>{
  alert('1')
  })
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
#app main {
display:flex;
flex:1;
background:#ddd;
   > .editor{
width:30em;
margin:16px 8px 16px 16px;
background:white;
box-shadow:0 0 3px hsla(0,0,0,0.5);
border-radius:4px;
overflow:auto;
}
   > .preview{
flex:1;
margin:16px 16px 16px 8px;
background:white;
box-shadow:0 0 3px hsla(0,0,0,0.5);
   }
}
.previewMode > #topbar{
display:none;
}
.previewMode  #editor{
display:none;
}
.previewMode  #preview{
max-width:800px;
margin:32px auto;
padding:16px;
}
#exitPreview{
display:none;
}
.previewMode #exitPreview{
display:inline-block;
position:fixed;
right:32px;
bottom:16px;
}
</style>
