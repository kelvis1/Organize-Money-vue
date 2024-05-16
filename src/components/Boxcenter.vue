<template>
  <div class="card">
  <div  class="card-img"></div>
  <div class="card-img-overlay">
    <h5 class="card-title mx-auto p-2" style="width: 300px; fw-bold">COM O QUE VOCÊ GASTOU:</h5>
    <p class="card-text ">Adicione aqui as coisas com que vc comprou/gastou, coloque o preço e a data.</p>
    

    <table class="table">
  <thead>
    <tr>
      <th scope="col">Nome</th>
      <th scope="col">Preço</th>
      <th scope="col">Data</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      
      <td>coca-cola</td>
      <td>R$ 5,00</td>
      <td>16/05/2024</td>
    </tr>
    <tr>
      
      <td>pizza-grande</td>
      <td>R$ 50,00</td>
      <td>16/05/2024</td>
    </tr>
    <tr>
      
      <td>açaí</td>
      <td>R$ 20,40</td>
      <td>16/04/2024</td>
    </tr>
  </tbody>
</table>

  </div>
</div>
</template>

<script>
export default {
     props: ["titulo"]
}
</script>

<style scoped>

    @import url("https://fonts.googleapis.com/css?family=Varela+Round");

    .card{
        width: 150vh;
        display: block;
        margin: 50px auto 20px auto;
    }

    .card-title{
      color: black;
      font-family: 'Varela' sans-serif;
    }

    .card-text{
      color: black;
      font-family: sans-serif;
      
    }
    .card-img{
       background: linear-gradient(180deg,  #781af4 0%, #2b134b 100%);
      height: 100vh;
    }
    
    th{
      background: #9a58f1;
      box-shadow: #2b134b;
      cursor: pointer;
    }
    
    td{
      background: #9a58f1;
      box-shadow: #2b134b;
      cursor: pointer;
    }
      td:hover{
      background: #781af4;
    }
</style>