<template>

  <div id = "app" class="app">

  <div id="cabecera" class="header">
    <img class="text-left" width="200" height="130" src="./assets/ogo.jpeg"/>
    <FONT SIZE=29 id="ma" face="Impact" class=" text-right text-primary p-7" v-if="!is_auth">Bienvenido</FONT>
  </div>

  <div id="toolbar" class="border border-warning">
    <nav>
      <button id="bt" class="btn btn-link" v-if="is_auth">Inicio</button> 
      <button id="bt" class="btn btn-link" v-if="is_auth">Programadores</button> 
      <button id="bt" class="btn btn-link" v-if="is_auth">Contacto</button>
      <button id="bt" class="btn btn-link" v-if="!is_auth && !suNow" v-on:click="loadSignUp">¿Aun no tienes cuenta?</button>
      <FONT SIZE=9 id="ma" face="Brush Script MT" class=" text-right text-primary p-7" v-if="!is_auth && suNow" >Se Parte De Nosotros</FONT> 
    </nav>

    <div id="fma">
      <form >
      <div class="fm">
        <input v-if="!suNow" id="ft" class="round" type="text" placeholder="Usuario">
        <input v-if="!suNow" id="ft" class="round" type="password" placeholder="Contraseña">
        <button v-if="!suNow" type="submit" class="boton">Acceder</button>
      </div>
    </form>
    </div>
    
  </div>

  <div class="main-component">
    <router-view
      v-on:completedLogIn="completedLogIn"
      v-on:completedSignUp="completedSignUp"
      v-on:logOut="logOut"
    >
    </router-view>
  </div>
  <footer class="text-center text-white" style="background-color: #0A0D0E;" >
    <div class="border border-warning">
      <nav >
        <a href="https://www.facebook.com/esteban.ojeda.718689" target="_blank"><img id="if" width="30" height="30" src="./assets/logo-de-facebook.png"></a>
        <a href="https://www.instagram.com/estebanojeda2361/" target="_blank"><img id="if" width="30" height="30" src="./assets/instagram.png"></a>
        <a href="https://twitter.com/fred0814" target="_blank"><img id="if" width="30" height="30" src="./assets/twitter.png"></a>
    </nav>
    <span style="color: #206DC1">© 2022 Copyright: Freddy Ojeda - Ronaldo Perez</span>
    </div>
    
  </footer>
  
</div>
</template>

<script>

export default {
  name: 'App',

  data: function(){
    return{
      is_auth: false,
      suNow:false
    }
  },

  components: {
    
  },

  methods:{
    verifyAuth: function() {
     this.is_auth = localStorage.getItem("isAuth") || false;

      if (this.is_auth == false)
        this.$router.push({ name: "logIn" });
      else
        this.$router.push({ name: "home" });
    },

    loadSignUp: function(){
      this.suNow=true;
      this.$router.push({name: "signUp"})
    },
  },

  created: function(){
    this.verifyAuth();
  }
}
</script>

<style>
#fma{
  
  /*top: 120; [wherever you want it]*/
  /*left:0; [wherever you want it]*/
 /* right: inherit;*/
 /*position: relative;*/
 width: 600px;
 left: 500px;
}
.fm{
  display:inline-block;
  text-align:center;
  width:100%;
}

.app{
  size: auto;
  width:auto;
  height:auto;
}
.header{
  display: flex;
  width:auto;
  background: 000000;
}

#cabecera{
  width: auto;
  background-color: rgba(0, 0, 0, 0.932);
}

#ma{
  position: auto;
  top: 40px;
  left: 1000px;
  width: 80%;
  height: 80%;
}

#toolbar{
  width: auto;
  min-width: auto;
  max-width: auto;
  display:flex;
  background-color: black;
  border-color: yellow;
}

#bt:hover{
  background-color: #0d3297; 
  color: white;
}

#btf{
  background-color: #0d3297;
  color:white;
  text-align: center;
  
}

#btf:hover{
  background-color: #ffffff00;
  color:rgb(255, 255, 255);
  border-color: #0d3297;
  border-width:medium
}

.cplg{
  position:auto;
  left:890px
}

#ft{
  padding-top: 5px;
}

.round {
 background-color: rgba(255, 255, 255, 0);
 width: auto;
 height: auto;
 margin: 0 auto 15px auto;
 color: white;
 padding: 5px;
 border: 2px solid rgb(255, 174, 0);
 border-radius: 20px;
}

.boton{
   text-decoration: none;
    padding: 5px;
    width: 30%;
    font-weight: 600;
    font-size: 15px;
    color: #ffffff;
    background-color: #1883ba;
    border-radius: 20px;
    border: 2px solid #0016b0;
}
.boton:hover{
  color: #1883ba;
    background-color: #ffffff00;
}
/*
*a partir de aqui comienza todo los estilos del footer
 */
#lista {
    font-family:Arial;
    font-weight:bold;
    font-size:13px;
    align-content: center;
}

#lista li {
     display:inline;
     padding-left:3px;
     padding-right:3px;
    /*background-color:black;*/
}

.footer{
  
  background-color: black;
  width: auto;
  height: auto;
  align-content: center;
}

.ft{

}

#if{
  align-self: center;
  filter: opacity(0.6) drop-shadow(0 0 0 #00d9ff); 
}

</style>