<template>
<div id="editor">
  <nav>
    <ol>
	  <li v-for="i in [0,1,2,3,4,5]"  
	      v-bind:class="{active:currentTab === i}" 
		  v-on:click="currentTab = i"">
	        <svg class="icon" aria-hidden="true">
            <use v-bind:xlink:href="'#icon-' + icons[i]"></use>
            </svg>
	  </li>	  
	</ol>
  </nav>
  <ol class="panes">
     <li v-bind:class="{active2:currentTab === 0}">
	    <ProfileEditor v-bind:profile = "resume.profile" />//import//
	 </li>
	 <li v-bind:class="{active2:currentTab === 1}" >
	    <ArrayEditor v-bind:items = "resume.workHistory" v-bind:labels="{company:'company',content:'content'}"  title="work-history" /> 
	 </li>
	 <li v-bind:class="{active2:currentTab === 2}" >
	    <ArrayEditor v-bind:items = "resume.studyHistory" v-bind:labels="{school:'school',duration:'duration',degree:'degree'}"  title="study-history"/>
	 
	 </li>
	 <li v-bind:class="{active2:currentTab === 3}">
		<ArrayEditor v-bind:items = "resume.projectHistory" v-bind:labels="{name:'name',content:'content',skill:'skill'}" title="project-history"/> 
	 </li>
	 <li v-bind:class="{active2:currentTab === 4}">
	    <ArrayEditor v-bind:items = "resume.rewardHistory" v-bind:labels="{name:'name',}" title="reward-history"/>
	 </li>
	 <li v-bind:class="{active2:currentTab === 5}">
	    <h2>contact</h2>
        <el-form :label-position="laberPosition"  :model="resume.contact">
            <el-form-item label="QQ">
            <el-input v-model="resume.contact.QQ"></el-input>
        </el-form-item>
        <el-form-item label="wechat">
            <el-input v-model="resume.contact.wechat"></el-input>
        </el-form-item>
        <el-form-item label="email">
            <el-input v-model="resume.contact.email"></el-input>
	    </el-form-item>
		<el-form-item label="telephone">
            <el-input v-model="resume.contact.telephone"></el-input>
	    </el-form-item>
 </el-form>
	 </li>
  </ol>
</div>
</template>

<script>
  import ProfileEditor  from './ProfileEditor'
  import ArrayEditor  from './ArrayEditor'
  export default{
     components:{ProfileEditor,ArrayEditor,},
	 props:['resume'],
     data(){
	  return{currentTab:0,
	  icons:['credentials_icon','school','xiangmu','jiangli','skill-copy','lianxi'],
	  laberPosition:'top',   
	 } 
	},
	methods:{
	
   }
  }
</script>
<style lang="scss">
#editor{
border:1px solid black;
display:flex;
   nav{
   background:black;
   width:80px;
   overflow:hidden;
   height:100%;
     ol>li{
     text-align:center;
     padding:16px;
       .icon{
        width:40px;
	    height:40px;
	    fill:white;
      }
	  &.active{
	    background:white;
		  .icon{
		   fill:black;
		  }
	   } 
	 }
   } 
   > ol {
       height:100%;
	   overflow:auto;
	   flex:1;
        >li {
          display:none;
            &.active2{
	          display:block;
	          padding:32px;	
	  	      >form{
	           min-width:330px; 
			    	   
		}
	 }
   } 
  }   
}
</style>