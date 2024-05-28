<template>
  <div>
    <nav class="navbar bg-warning shadow">
      <div class="container-fluid">
        <span class="navbar-brand mb-0 h1 shadow">Organize Money</span>

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
            <button type="button" class="btn btn-success" data-bs-dismiss="modal">Close</button>
          </div>
        </div>
      </div>
    </div>

    <div class="container mt-4">
      <div class="row justify-content-center">
        <Cards :titulo="'Saldo'" :valor="saldo" @atualizar-valor="atualizarSaldo" />
        <Cards :titulo="'Despesa'" :valor="gastos" @atualizar-valor="atualizarGastos" />
          
      </div>

    
    </div>
    <Boxcenter :titulo="'Boxcenter'" />
  </div>
</template>

<script>
import Cards from '../components/Cards.vue';
import Boxcenter from '@/components/Boxcenter.vue';
export default {
  name: "home",
  components: {
    Cards,
    Boxcenter
  },
  data() {
    return {
      saldo: 0.00,
      gastos: 0.00,
      transacoes: [],
    };
  },
  methods: {
    atualizarSaldo(valor) {
      this.saldo += valor;
      this.adicionarTransacao('Saldo', valor);
    },
    atualizarGastos(valor) {
      this.gastos += valor;
      this.adicionarTransacao('Despesa', valor);
    },
    adicionarTransacao(tipo, valor) {
      this.transacoes.push(`${tipo}: R$ ${valor.toFixed(2)}`);
    },
  },
};
</script>

<style scoped>
.modal {
  width: 300px;
}

.modal-content {
  width: 300px;
}

.list-group-item {
  background: #e4bb29;
}

.list-group-item:hover {
  background: #e46d29;
}

.modal-header {
  background: #e4bb29;
}

.modal-body {
  background: #e4bb29;
}

.modal-footer {
  background: #e4bb29;
}

.balance, .transactions {
  margin-top: 20px;
}

@import url("https://fonts.googleapis.com/css?family=Varela+Round");
</style>
