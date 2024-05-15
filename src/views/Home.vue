<template>
 <nav class="navbar bg-success shadow">
  <div class="container-fluid">
    <span class="navbar-brand mb-0 h1">Menu</span>

    <button class="navbar-toggler" type="button" data-bs-toggle="modal" data-bs-target="#exampleModal">
      <span class="navbar-toggler-icon"></span>
    </button>
  </div>
</nav>


<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog modal-fullscreen">
    <div class="modal-content">
      <div class="modal-header">
        <h1 class="modal-title fs-5" id="exampleModalLabel">Menu</h1>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
      
        <ul class="list-group list-group-flush">
  <li class="list-group-item">HOME</li>
  <li class="list-group-item">COSTUMIZAÇÃO</li>
  <li class="list-group-item">ESTATISTICAS</li>
  <li class="list-group-item">CONFIGURAÇÃO</li>
  <li class="list-group-item">SOBRE</li>
</ul>

      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-sucess" data-bs-dismiss="modal">Close</button>
      </div>
    </div>
  </div>
</div>

 <div class="row mt-4 m-0 justify-content-center">
      <Cards :titulo="'Saldo'"/>
      <Cards :titulo="'Despesa'"/>
      <Cards :titulo="'Outros'"/>
      <Boxcenter :titulo="'Boxcenter'" />
    </div>


</template>

<script>
import Cards from "../components/Cards.vue";
import Boxcenter from '@/components/Boxcenter.vue';


export default {
  name: "home",
  components: {
    Cards,
    Boxcenter,
  }
};

</script>

<style scoped>

.modal{
  width: 300px;
}

.modal-content{
  width: 300px;
}
.list-group-item{
  background: #00ff88;
}

.list-group-item:hover{
 background:  #77ffc0;
}

.modal-header{
  background: linear-gradient(180deg,  #77ffc0 0%, #00ff88 100%);
}

.modal-body{
  background: #00ff88;
}

.modal-footer{
   background: linear-gradient(180deg,  #00ff88 0%,  #77ffc0 100%);
}

@import url("https://fonts.googleapis.com/css?family=Varela+Round");

</style>
