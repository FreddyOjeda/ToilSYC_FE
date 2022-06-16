<template>
    <div class="signUp_user">
        <div id="container_signUp_user" class="border border-warning">
            
            <div id="r1" >
                <img id="p" width="130" height="130" src="../assets/perfil.png"/>
                <textarea id="ft" class="round" type="text" placeholder="Cuentanos acerca de ti..."></textarea>
            </div>

            <div id="r2" >
                <input  id="ft" class="round" type="text" placeholder="Usuario">
                <input  id="ft" class="round" type="text" placeholder="Ciudad">
                <input  id="ft" class="round" type="text" placeholder="Carrera">
                <br>
                
            </div>

            <div id="r3" >
                <input  id="ft" class="round" type="text" placeholder="Univesidad/Instituto">
                <input  id="ft" class="round" type="tel " placeholder="Telefono" pattern="^\d+$" title="Este campo solo puede contener numeros" required>
                <input  id="ft" class="round" type="email" placeholder="Correo">
            </div>

            <div id="r4">
                <input  class="round" type="password" placeholder="Contraseña">
                <input  class="round" type="password" placeholder="Confirmar Contraseña">
            </div>

            <div id="r5">
                <button type="submit" class="boton">Registrarse</button>
            </div>
        </div>
    </div>
</template>

<script>
//import axios from 'axios';
//para hacer peticiones restfull
export default {
    name: "SignUp",

    data: function(){
        return {
            user: {
                photo:"",
                description:"",
                username: "",
                city: "",
                career: "",
                college: "",
                password: "",
                repassword: "",
            }
        }
    },

    methods: {
        
    }
}
</script>

<style>

.round {
 background-color: rgba(255, 255, 255, 0);
 width: 30%;
 height: auto;
 margin: 0 auto 15px auto;
 color: white;
 padding: 5px;
 border: 2px solid #ffae00;
 border-radius: 20px;
}

    #p{
        border-radius: 100%;
        border: 5px solid rgb(255, 255, 255);
    }

    #container_signUp_user {
        background-color: rgb(0, 0, 0);
        border-radius: 40px;
        width: 65%;
        height: 90%;
        justify-content: absolute;
        position: relative;
        /*align-items: center;*/
    }

    #r1{
        position: absolute;
        top: -55%;
        bottom: 0;
        left: 0;
        right: 0;
        width: 80%;
        height: 42%;
        margin: auto;
        display: flex;
        justify-content: center;
    }

    #r1 textarea{
        width:60%;
    }

    #r2{
        position: absolute;
        top: 5%;
        bottom: 0;
        left: 0;
        right: 0;
        width: 100%;
        height: 15%;
        margin: auto;
        display: flex;
        justify-content: center;
    }

    #r3{
        position: absolute;
        top: 35%;
        bottom: 0;
        left: 0;
        right: 0;
        width: 100%;
        height: 15%;
        margin: auto;
        display: flex;
        justify-content: center;
    }

    #r4{
        position: absolute;
        top: 65%;
        bottom: 0;
        left: 0;
        right: 0;
        width: 100%;
        height: 15%;
        margin: auto;
        display: flex;
        justify-content: center;
    }

    #r5{
        position: absolute;
        top: 85%;
        bottom: 0;
        left: 0;
        right: 0;
        width: 100%;
        height: 10%;
        margin: auto;
        display: flex;
        justify-content: center;
    }

    .signUp_user{
        background-color: rgb(0, 0, 0);
        margin: 0;
        padding: 0%;
        height: 400px;
        width: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    
</style>