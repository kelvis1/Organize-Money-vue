<template>
  <div class="col col-12 col-sm-3 ">
    <div class="container text-center">
      <div class="row align-items-start">
        <div class="col">
          <div class="card">
            <div class="card-body">
              <h5 class="card-title">{{ titulo }}</h5>
              <h6 class="card-subtitle mb-2 text-body-secondary">Subtitulo</h6>
              <p class="card-text">teste texto textado</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["titulo"],
};
</script>

<style scoped>

.card-body{
    border: none;
    border-radius: 8px;
    outline: none;
    text-transform:uppercase;
    font-weight: 800;
    letter-spacing: 3px;
    cursor: pointer;
    color: #2b134b;
    background: #00ff88;
    box-shadow: 0px 10px 40px -12px #00ff8052;
}
    
.card-body:hover{
  background:#77ffc0;
}

</style>
