<template>
  <div class="app">
    <div class="box">
		<div class="content">
			<div class="admin">
				adminstrador
				<div class="icon">
					<i class="fa-solid fa-sun" @click="activeMode" v-if="darkActive" ></i>
					<i class="fa-solid fa-moon"  @click="activeMode"  v-else></i>
				</div>
			</div>
			<div class="element">
				<input type="text" name="" placeholder="Usuario"><br>
				<input type="text" name=""  placeholder="Senha"><br>
				<a href="" class="link01">Entrar</a><br>
				<a href="" class="link02">Esquece senha</a>
			</div>
		</div>
	</div>
  </div>
</template>

<script>
export default {
  data:function(){
    return{
        darkActive:true
    }
  },
  methods:{
    activeMode(){
      this.darkActive=!this.darkActive
      console.log(this.darkActive)
      if(!this.darkActive){
        document.body.classList.toggle("activeDarkMode")
        
        console.log("active")
      }else{
        document.body.classList.toggle("activeDarkMode")
        console.log("desative")
      }   
    }
  },
created(){
    this.activeMode()
  }
}
</script>
<style>
body{
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    
}
.admin{
    position: absolute;
    top:0px;
    left: 0;
    background:#151e83;
    width: 100%;
    height: 50px;
    justify-content: center;
    align-items: center;
    display: flex;
    color: #fff;
    text-transform: uppercase;
    font-size: 20px;
    font-family: sans-serif;
    box-shadow: 0px 0px 4px #000;
    z-index: 10;
}
.icon{
    display: flex;
    width: 50px;
    height: 50px;
    position: absolute;
    top:18px;
    left: 15px;  
}
.icon i{
    color: #fff;
    cursor: pointer;
}
i:nth-child(1){
    margin-top: 5px;
    margin-left: 2px;
}
.box{
    position: relative;
    width: 90%;
    max-width: 400px;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-top: 60px;

}
.box .content{
    position: relative;
    width: 350px;
    height:400px;
    box-shadow: 2px 2px 5px #000;
    justify-content: center;
    align-items: center;
    display: flex;
    background: rgb(16, 16, 48);
   
}
.box .content:before{
    content: '';
    position: absolute;
    top: 0px;
    left: 0px;
    top: -2px;
    right: -2px;
    bottom: -2px;
    background: linear-gradient(315deg,#151e83,#151e83);
    transform: skew(2deg,2deg);
    z-index: -1;
}
.content .element{
    position: relative;
    width: 100%;
    margin-left: 25px;
    padding: 5px;
    margin-top: -30px;
}
.element input{
    width: 90%;
    margin-top: 20px;
    height: 25px;
    background: transparent;
    border: none;
    outline: none;
    border-bottom:1px solid #fff;
    color: #fff;
    font-size: 15px;
}
.element a{
    
    font-family: sans-serif;
    text-decoration: none;
    margin-top: 20px;
    padding: 10px;
}
.element .link01{
    background: #fff;
    margin-top: 20px;
    position: absolute;
    left: 35%;
    padding: 10px;
    border-radius: 5px;
    color: #000;
    font-size: 15px;
    display: inline-block;
}
.element .link01:hover{
    background: #ccc;
}
.link02{
    position: absolute;
    top: 180px;
    left: 5px;
    color: #fff;
    font-size: 14px;
}
.link02:hover{
    color: #ccc;
}
input::-webkit-input-placeholder{
    color: #fff;
}
.activeDarkMode{
    background: rgb(16, 16, 48);
    z-index: 1;
    width: 100%;
    height: 500px;
}
</style>
