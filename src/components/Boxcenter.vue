<template>
  <div class="card">
    <div class="card-img"></div>
    <div class="card-img-overlay">
      <h5 class="card-title mx-auto p-2" style="fw-bold">ADMINISTRE SEU DINHEIRO AQUI: 
        <button class="btn btn-primary" @click="openModal">Adicionar Valor</button>
      </h5>
      
      <table class="table">
        <thead>
          <tr>
            <th scope="col">Nome</th>
            <th scope="col">Preço</th>
            <th scope="col">Data</th>
            <th scope="col">Tipo</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(gasto, index) in gastos" :key="index">
            <td :class="gasto.css">{{ gasto.nome }}</td>
            <td :class="gasto.css">{{ gasto.preco }}</td>
            <td :class="gasto.css">{{ gasto.data }}</td>
            <td :class="gasto.css">{{ gasto.tipo}}</td>
          </tr>
        </tbody>
      </table>

      <!-- Modal -->
      <div class="modal fade" id="gastoModal" tabindex="-1" aria-labelledby="gastoModalLabel" aria-hidden="true">
        <div class="modal-dialog modal-lg">
          <div class="modal-content">
            <div class="modal-header">
              <h5 class="modal-title" id="gastoModalLabel">Organize Money</h5>
              <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
            </div>
            <div class="modal-body">
              <div class="input-group mb-3">
                <input v-model="novoGasto.nome" type="text" class="form-control" placeholder="Nome do gasto">
                <input v-model.number="novoGasto.preco" type="number" step="0.01" class="form-control" placeholder="Preço">
                <input v-model="novoGasto.data" type="date" class="form-control" placeholder="Data">
                <InputSelectBase :opcoes="opcoesEscolaridade" v-model:selecionado="novoGasto.tipo" :obrigatorio="true" />
              </div>
            </div>
            <div class="modal-footer">
              <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Fechar</button>
              <button type="button" class="btn btn-primary" @click="adicionarGasto">Adicionar</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import InputSelectBase from './InputSelectBase.vue';

export default {
  components: {
    InputSelectBase,
  },
  data() {
    return {
      opcoesEscolaridade: [
        { id: 1, valor: 'Saldo' },
        { id: 2, valor: 'Gasto' },
      ],
      gastos: [],
      novoGasto: {
        nome: '',
        preco: 0.00,
        data: '',
        tipo: '',
        css: ''
      }
    };
  },
  methods: {
    openModal() {
      var modal = new bootstrap.Modal(document.getElementById('gastoModal'));
      modal.show();
    },
    adicionarGasto() {
      if (this.novoGasto.nome && this.novoGasto.preco && this.novoGasto.data) {
        if (this.novoGasto.tipo === 'Saldo') {
          this.novoGasto.css = 'text-success fw-bold';
          this.$emit('atualizar-saldo', this.novoGasto.preco);
        } else {
          this.novoGasto.css = 'text-danger fw-bold';
          this.$emit('atualizar-gasto', this.novoGasto.preco);
        }

        this.gastos.push({ ...this.novoGasto });

        // Resetar novoGasto após adicionar
        this.novoGasto = { nome: '', preco: 0.00, data: '', tipo: '', css: '' };
        var modal = bootstrap.Modal.getInstance(document.getElementById('gastoModal'));
        modal.hide();
      } else {
        alert('Por favor, preencha todos os campos.');
      }
    }
  }
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=Varela+Round");

.card {
  width: 150vh;
  display: block;
  margin: 50px auto 20px auto;
}
.card-title {
  color: #4e3a3b;
  font-family: 'Varela', sans-serif;
}
.card-img {
  background: #e4bb29;
  height: 100vh;
}
.modal-footer {
  background: #ba4c57;
}
.modal-body {
  background: #ba4c57;
}
.modalfade {
  background: #ba4c57;
}
.modal-header {
  background: #ba4c57;
}
.btn {
  background: #4e3a3b;
}
</style>
