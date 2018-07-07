<template>
<div style="margin: auto; width=50%">
    	<p style="font-size: 30px">登录页面</p>
    	手机号： <el-input v-model="phone" placeholder="请输入手机号" style="width: 20%"></el-input><br><br>
    	用户名： <el-input v-model="username"  placeholder="请输入用户名" style="width: 20%"></el-input><br><br>
    	 密 码： <el-input v-model="password" placeholder="请输入密码" style="width: 20%"></el-input><br><br>
    	 姓 名： <el-input v-model="name"  placeholder="请输入姓名" style="width: 20%"></el-input><br><br>
    	 <el-button type="primary" round @click="regist()">注册</el-button>
    	 <el-button type="primary" round @click="login()">登录</el-button>
    </div>
</template>

<script>
export default{
	  	data(){
	  		return{
	  			phone:'',
	  			username:'',
	  			password:'',
	  			name:''
	  		}
	  	},
	  	methods:{
                login(){
                	this.$axios.get('http://localhost:8080/regist?phone='+this.phone+'&username='+this.username+'&password='+this.password+'&name='+this.name).then(response =>{
                		if(response.data.code='0000'){
                           this.$message({
                    	message:response.data.msg,
                    	type:'success'
                    });
                    this.$router.push({path:'/index'})
               	}else{
               		this.$message.error(response.data.msg);
               	}
                	})
                },
                regist(){
                    this.$router.push({path:'/regist'})
        }
	  	}
	  	
	  }

</script>

<style rel="stylesheet">

</style>