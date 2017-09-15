<template>
<div id="preview">
<h1>{{resume.profile.name}}  </h1>
<p>{{resume.profile.birth}} | {{resume.profile.city}} </p>
<hr>

<section v-if="filter(resume.projectHistory).length > 0">
  <h2>project</h2>
  <ul>
    <li v-for="project in filter(resume.projectHistory)">
	{{projectHistory.name}}
	{{projectHistory.content}}
	{{projectHistory.skill}}
	</li>
  </ul>
</section>
<section v-if="filter(resume.workHistory).length > 0">
  <h2>work</h2>
  <ul>
    <li v-for="work in filter(resume.workHistory)">
	{{workHistory.company}}
	{{workHistory.content}}
	
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
	     return  array.filter(item=>!this.isEmpty(item))
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

<style>
#preview{
border:1px solid black;
}
</style>