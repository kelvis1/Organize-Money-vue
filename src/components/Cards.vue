<template>
  <div class="col col-12 col-sm-3">
    <div class="container text-center">
      <div class="row align-items-start">
        <div class="col">
          <div class="card">
            <div class="card-body" @click="showModal = true">
              <h5 class="card-title">{{ titulo }}</h5>
              <h6 class="card-subtitle mb-2 text-body-secondary">{{ formattedValor }}</h6>
              <p class="card-text">Clique para atualizar</p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div v-if="showModal" class="modal">
      <div class="modal-content">
        <span class="close" @click="showModal = false">&times;</span>
        <h2>{{ titulo }}</h2>

        <div class="options">
          <input type="number" v-model.number="valorInput" step="0.01" placeholder="Valor">
          <input type="button" value="Confirmar" @click="processarOpcao">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["titulo", "valor"],
  data() {
    return {
      showModal: false,
      valorInput: 0.00,
    };
  },
  computed: {
    formattedValor() {
      return `R$ ${this.valor.toFixed(2)}`;
    }
  },
  methods: {
    processarOpcao() {
      this.$emit('atualizar-valor', this.valorInput);
      this.showModal = false;
    }
  }
};
</script>

<style scoped>
.card-body {
  border: none;
  border-radius: 8px;
  outline: none;
  text-transform: uppercase;
  font-weight: 800;
  letter-spacing: 3px;
  cursor: pointer;
  color: #4e3a3b;
  background: #e4bb29;
}

.card-body:hover {
  background: #a59571;
}

.modal {
  display: flex;
  position: fixed;
  z-index: 1;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: rgba(0, 0, 0, 0.4);
  justify-content: center;
  align-items: center;
}

.modal-content {
  background-color: white;
  padding: 20px;
  border: 1px solid #888;
  width: 80%;
}

.close {
  color: #aaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: black;
  text-decoration: none;
  cursor: pointer;
}

.options {
  margin-bottom: 20px;
}

.card-body {
  border: none;
  border-radius: 8px;
  outline: none;
  text-transform: uppercase;
  font-weight: 800;
  letter-spacing: 3px;
  cursor: pointer;
  color: #4e3a3b;
  background: #e4bb29;
}

.card-body:hover {
  background: #a59571;
}

.modal {
  display: flex;
  position: fixed;
  z-index: 1;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: rgba(0, 0, 0, 0.4);
  justify-content: center;
  align-items: center;
}

.modal-content {
  background-color: white;
  padding: 20px;
  border: 1px solid #888;
  width: 80%;
}

.close {
  color: #aaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: black;
  text-decoration: none;
  cursor: pointer;
}

.balance, .options, .transactions {
  margin-bottom: 20px;
}



.card-body{
    border: none;
    border-radius: 8px;
    outline: none;
    text-transform:uppercase;
    font-weight: 800;
    letter-spacing: 3px;
    cursor: pointer;
    color:#4e3a3b;
    background: #e4bb29;

    
}
    
.card-body:hover{
  background:#a59571;
}

</style>
