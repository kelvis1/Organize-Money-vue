<template>
<form id="cadastro" @submit="criarConta">
    <div class="main-registro">
        <div class="left-registro">
            <h1>Faça seu Registro<br>E Organize seu Dinheiro</h1>
            <img src="" class="Money" alt="Dinheiro">
        </div>
        <div class="right-registro">
            <div class="card-registro">
                <h1>REGISTRO</h1>
                <div class="textfield">
                    <label for="usuario">Usuário:</label>
                    <input type="text" name="usuario" v-model="nome" required placeholder="Usuário">
                </div>
                <div class="textfield">
                    <label for="Email">Email:</label>
                    <input type="email" name="email" v-model="email" required placeholder="Email">
                </div>
                <div class="textfield">
                    <label for="senha">Senha:</label>
                    <input type="password" name="senha" v-model="senha" required placeholder="Senha">
                </div>
               
               <button class="btn-registro">Registro</button>
               
                <p>ou clique aqui: <router-link to="/login"> <button class="btn-login">Login</button></router-link></p>
            </div>
        </div>
       
    </div>
 </form>

</template>

<script >

export default{
    name: "cadastro",
    data(){
        return{
            nome:  null,
            email: null,
            senha: null
        }
    },
    methods:{
        criarConta(e){
            e.preventDefault();
            console.log(this);
            if(this.senha.length < 8){
                alert('A senha deve ter pelo menos 8 caracteres.');
                return;
            }
            localStorage.setItem("nomes", this.nome)
            localStorage.setItem("emails", this.email)
            localStorage.setItem("senhas", this.senha)
            this.$router.push('/home');
        }
        
    }
};

</script>

<style scoped>

.main-registro{
  width: 100vw;
  height: 100vh;
  background: #ebf2f2;
  display: flex;
  justify-content: center;
  align-items: center;
}
.left-registro{
  width: 50vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.left-registro > h1{
  font-size: 3vw;
  color: #4e3a3b;
}
.right-registro{
  width: 50vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
.card-registro{
  width: 60%;
  height: 86vh;
  display: flex;
  justify-content: center;
  align-content: center;
  flex-direction: column;
  padding: 30px 35px;
  background: #bcebdf;
  border-radius: 20px;
  box-shadow: 0px 10px 40px #ade0db;
}
.card-registro >h1{
  color: #4e3a3b;
  font-weight: 800;
  margin: 0;
}
.textfield{
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  margin: 10px 0px;
}
.textfield > input{
  width: 100%;
  border: none;
  border-radius: 10px;
  padding: 15px;
  background: #ebf2f2;
  color:#4e3a3b;
  font-size: 12pt;
}
.textfield > label{
  color:#4e3a3b;
  margin-bottom: 5px;
}
.textfield > input::placeholder{
  color: #512025;
}
.btn-registro{
  width: 100%;
  padding: 16px 0px;
  margin: center;
  border: none;
  border-radius: 8px;
  outline: none;
  text-transform: uppercase;
  font-weight: 800;
  letter-spacing: 3px;
  color: #4e3a3b;
  background:#ade0db;
  cursor: pointer;
}
.btn-login{
  background: #ade0db;
  color: #4e3a3b;
  padding: none;
  border-color: #ade0db;
}
p{
  margin-left: 23vh;
  padding: 10px;
  color:#4e3a3b;
}
@media only screen and (max-width: 950px){
  .card-login{
    width: 100%;
  }
}
@media only screen and (max-width: 600px){
  .main-login{
    flex-direction: column;
    width: 100%;
  }
  .left-login > h1{
    display: none;
    margin-bottom: 4px;
  }
  
}

</style>