<template>
 <div>
 <h2>profile</h2>
 <el-form :label-position="laberPosition"  :model="profile">
    <el-form-item label="name">
    <el-input v-model="profile.name"></el-input>
    </el-form-item>
    <el-form-item label="birth">
    <el-input v-model="profile.birth"></el-input>
    </el-form-item>
    <el-form-item label="city">
    <el-input v-model="profile.city"></el-input>
	</el-form-item>
 </el-form>
 </div>
</template>
<script>
  export default{
  data(){
  return{laberPosition:'top'}
  },
  props:['profile']//父组件向子组件传值
  }
</script>