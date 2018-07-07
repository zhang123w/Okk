<template>
	
<div>
	<el-container>
    <el-header style="background-color: red"><header-top></header-top></el-header>
    <el-container>
    <el-aside width="200px" style="background-color: blue"><left></left></el-aside>
    <el-main style="background-color: yellow"><main-list></main-list></el-main>
    </el-container>
    </el-container>
</div>

</template>

<script >
	import Left from './Left';
	import MainList from './Main';
	import HeaderTop from './Header';
export default{
        name:'',
	  	data(){
	  		return{
	  		}
	  	},
	  	components:{
	  		Left,
	  		MainList,
	  		HeaderTop

	  	}
	}

    
</script>

<style rel="stylesheet">

</style>