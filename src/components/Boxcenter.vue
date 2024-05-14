<template>
  <div class="card text-bg-dark">
  <img src="/img/caramelo.jpg" class="card-img" alt="caramelo">
  <div class="card-img-overlay">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
    <p class="card-text"><small>Last updated 3 mins ago</small></p>
  </div>
</div>
</template>

<script>
export default {
     props: ["titulo"]
}
</script>

<style scoped>

    .card{
        width: 150vh;
        display: block;
        margin: 50px auto 20px auto;
    }


</style>