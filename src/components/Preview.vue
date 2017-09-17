<template>
<div id="preview">
<h1>{{resume.profile.name || '请填写姓名'}}  </h1>
<p>{{resume.profile.birth || '请填写出生年月'}}  |  {{resume.profile.city || '请填写所在地'}}  </p>
<hr>
<section v-if="filter(resume.workHistory).length >= 0">
  <h2>工作经历</h2>
  <ul>
    <li v-for="work in filter(resume.workHistory)">
	{{work.company || '请填写公司名'}}
	{{work.content || '请填写工作内容'}}
	</li>
  </ul>
<hr>
</section>


<section v-if="filter(resume.studyHistory).length >= 0">
  <h2>学校经历</h2>
  <ul>
    <li v-for="study in filter(resume.studyHistory)">
	{{study.school || '请填写学校名称'}}
	{{study.duration || '请填写在校时间段'}}
	{{study.degree || '请填写学位'}}
	</li>
  </ul>
 <hr>
</section>


<section v-if="filter(resume.projectHistory).length >= 0">
 <h2>项目经历</h2>
 <ul>
   <li v-for="project in filter(resume.projectHistory)">
   {{project.name}}
   {{project.content}}
   {{project.skill}}
   </li>
 </ul>  
 <hr>
</section>




<section v-if="filter(resume.rewardHistory).length >= 0">
  <h2>获奖经历</h2>
  <ul>
    <li v-for="reward in filter(resume.rewardHistory)">
	{{reward.name}}
	</li>
  </ul>
  <hr>
</section>


<section>
  <h2>联系方式</h2>
  <ul>
    <li v-for="con  in  Object.keys(resume.contact)">
	  {{con}}:{{resume.contact[con]}}
	  
	</li>
  </ul>
</section>
</div>
</template>

<script>
  export default {
    props:['resume'],
	methods:{
	   filter(array){
	     return  array.filter(item=> !this.isEmpty(item))
	   },
	   isEmpty(object){
	     let empty = true
	     for(let key in object){
		   if(object[key]){
		      empty = false
			  break
		   }
		 }
		 return empty
	   }
	}
  }
</script>

<style  lang = "scss">
#preview{
  border:1px solid black;
  border-radius:4px;
  padding-left:20px;
  padding-right:20px;
     section{
	   margin:10px 0px; 
	   >ul{
	     margin-top:10px;
		 >li{
		   margin:8px 0px;
		 }
	   }
   }
}

</style>