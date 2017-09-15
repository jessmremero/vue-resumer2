<template>
 <div>
 <h2>{{title}}</h2>
 
 <el-form>
   <div v-for="(work,index) in items" v-bind:key="index" >
        <el-form-item  v-for="key in keys"  v-bind:label="labels[key] || key"  v-bind:key="key">
        <el-input v-model="work.key"></el-input>
		</el-form-item>
	    <i class="el-icon-delete"   v-on:click = "removeWorkHistory(index)"></i>
   </div>
   <el-button  type="primary" v-on:click = "addWorkHistory">add</el-button>		  
 </el-form>
 </div>
</template>
<script>
  export default{
  props:['items','labels','title'],
  computed:{
  keys(){
  return Object.keys(this.items[0]) 
   }
  },
  methods:{
    addWorkHistory( ){
	  const empty = {}
	  this.keys.map((key)=>{
	    empty[key] = ''
	  })
	  this.items.push(empty)//这里的this指的是什么？div？ 
	},
	removeWorkHistory(index){
	  this.items.splice(index,1)  
	}//为什么只能从最后开始删除
   }
  }
</script>