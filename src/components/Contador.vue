<template>
  
<div class="container">
    <h2>Controle Financeiro</h2>

    <div class="balance">
        <p><strong>SALDO:</strong> <span id="saldo">R$ 0.00</span></p>
        <p><strong>GASTOS:</strong> <span id="gastos">R$ 0.00</span></p>
    </div>

    <div class="options">
        <select id="opcao">
            <option value="1">Cadastrar saldo</option>
            <option value="2">Cadastrar despesa</option>
        </select>
        <input type="number" id="valor" step="0.01" placeholder="Valor">
        <input type="button" value="Confirmar" onclick="processarOpcao()">
    </div>

    <div class="transactions">
        <h3>Transações</h3>
        <ul id="transacoes">
        </ul>
    </div>
</div>
</template>

<script>

 let saldo = 0.00;
    let gastos = 0.00;

    function processarOpcao() {
        let opcao = document.getElementById("opcao").value;
        let valor = parseFloat(document.getElementById("valor").value);

        switch (parseInt(opcao)) {
            case 1:
                saldo = valor;
                break;
            case 2:
                gastos += valor;
                break;
            default:
                alert("Opção inválida. Por favor, escolha novamente.");
                return;
        }

        exibirSaldoEGastos();
        exibirTransacao(opcao, valor);
    }

    function exibirSaldoEGastos() {
        document.getElementById("saldo").innerText = "R$ " + saldo.toFixed(2);
        document.getElementById("gastos").innerText = "R$ " + gastos.toFixed(2);
    }

    function exibirTransacao(opcao, valor) {
        let transacoes = document.getElementById("transacoes");
        let opcaoTexto = opcao === "1" ? "Saldo" : "Despesa";
        let li = document.createElement("li");
        li.textContent = `${opcaoTexto}: R$ ${valor.toFixed(2)}`;
        transacoes.appendChild(li);
    }

export default {
    
}
</script>

<style>

</style>