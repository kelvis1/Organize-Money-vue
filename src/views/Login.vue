<template>
  <form id="login" @submit="logarConta">
  <div class="main-login">
        <div class="left-login">
            <h1>Faça login <br>E Organize seu Dinheiro</h1>
            <img src="" class="Money" alt="Dinheiro">
        </div>
        <div class="right-login">
            <div class="card-login">
                <h1>LOGIN</h1>
                <div class="textfield">
                    <label for="usuario">Usuário:</label>
                    <input type="text" name="usuario" required placeholder="Usuário">
                </div>
                <div class="textfield">
                    <label for="senha">Senha:</label>
                    <input type="password" name="senha" required placeholder="Senha">
                </div>
                <button class="btn-login">Login</button>
            </div>
        </div>
    </div>
    </form>
</template>

<script>

export default{
    name: "login",
    data(){
        return{
            nome: 'null',
            senha: 'null'
        }
    },
    methods:{
        logarConta(e){
             e.preventDefault();
            localStorage.setItem("nomes", this.nome)
            localStorage.setItem("senhas", this.senha)
            this.$router.push('/home');
        }
        
    }
};


</script>

<style scoped>


.main-login{
  width: 100vw;
  height: 100vh;
  background: #e46d29;
  display: flex;
  justify-content: center;
  align-items: center;
}
.left-login{
  width: 50vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.left-login > h1{
  font-size: 3vw;
  color: #4e3a3b;
}
.right-login{
  width: 50vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
.card-login{
  width: 60%;
  height: 86vh;
  display: flex;
  justify-content: center;
  align-content: center;
  flex-direction: column;
  padding: 30px 35px;
  background: #ba4c57;
  border-radius: 20px;
  box-shadow: 0px 10px 40px #512025;
}
.card-login >h1{
  color: #4e3a3b;
  font-weight: 800;
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
  background: #d0bc87;
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
.btn-login{
    width: 100%;
    padding: 16px 0px;
    border: none;
    border-radius: 8px;
    outline: none;
    text-transform:uppercase;
    font-weight: 800;
    letter-spacing: 3px;
    color:#d0bc87;
    background:#4e3a3b;
    cursor: pointer;
    box-shadow: 0px 10px 40px -12px #1f212052;
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