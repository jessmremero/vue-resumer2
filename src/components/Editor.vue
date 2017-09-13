<template>
<div id="editor">
  <nav>
    <ol>
	  <li class="active">
	   <svg class="icon" aria-hidden="true">
       <use xlink:href="#icon-credentials_icon"></use>
       </svg>
	  </li>
	  <li> 
	    <svg class="icon" aria-hidden="true">
        <use xlink:href="#icon-school"></use>
        </svg>
	  </li>
	  <li>
	    <svg class="icon" aria-hidden="true">
        <use xlink:href="#icon-xiangmu"></use>
        </svg>
	  </li>
	  <li>
	    <svg class="icon" aria-hidden="true">
        <use xlink:href="#icon-jiangli"></use>
        </svg>
	  </li>
	  <li>
	    <svg class="icon" aria-hidden="true">
        <use xlink:href="#icon-skill-copy"></use>
        </svg>
	  </li>
	  <li>
	    <svg class="icon" aria-hidden="true">
        <use xlink:href="#icon-lianxi"></use>
        </svg>
	  </li>
	</ol>
  </nav>
  <ol class="panes">
  </ol>
</div>
</template>
<style lang="scss">
#editor{
border:1px solid black;
display:flex;

   nav{
   background:black;
   width:80px;
   overflow:hidden;
     ol>li{
     text-align:center;
     padding:5px;
     border:1px solid yellow;
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
}
</style>