<!DOCTYPE html>
<html lang="pt">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bango V2</title>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #031c12;
  color: white;
}

header {
  background: #064b31;
  text-align: center;
  padding: 28px 15px;
  border-bottom: 2px solid #21d47b;
}

header h1 {
  margin: 0;
  color: #2ee783;
  font-size: 42px;
}

header p {
  margin: 10px 0 0;
  font-size: 22px;
  color: #b8d8c9;
}

.container {
  max-width: 700px;
  margin: auto;
  padding: 25px;
}

.card {
  background: #073323;
  border-radius: 28px;
  padding: 28px;
  margin-bottom: 25px;
}

h2 {
  color: #36e889;
  font-size: 30px;
}

p {
  font-size: 18px;
  line-height: 1.5;
}

button {
  width: 100%;
  padding: 18px;
  margin: 8px 0;
  border: none;
  border-radius: 18px;
  background: #20d477;
  color: #001b10;
  font-size: 20px;
  font-weight: bold;
  cursor: pointer;
}

button.secundario {
  background: transparent;
  border: 2px solid #2ee783;
  color: #2ee783;
}

input {
  width: 100%;
  padding: 16px;
  margin: 8px 0;
  border-radius: 12px;
  border: none;
  font-size: 17px;
}

.saldo {
  background: #0b402c;
  text-align: center;
  padding: 25px;
  border-radius: 22px;
  margin: 20px 0;
}

.saldo pequeno {
  color: #b8d8c9;
}

.valor {
  color: #2ee783;
  font-size: 42px;
  font-weight: bold;
}

.opcoes {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 15px;
}

.opcao {
  background: #0b402c;
  border: none;
  color: white;
  padding: 25px 10px;
  border-radius: 18px;
  font-size: 18px;
}

.oculto {
  display: none;
}

footer {
  text-align: center;
  color: #8fb9a7;
  padding: 25px;
}
</style>
</head>

<body>

<header>
  <h1>BANGO V2</h1>
  <p>Oportunidades para todos</p>
</header>

<div class="container">

  <!-- INÍCIO -->
  <section id="inicio" class="card">
    <h2>Bem-vindo ao Bango V2</h2>
    <p>
      Uma plataforma criada para aproximar pessoas de oportunidades,
      serviços e atividades na nossa sociedade.
    </p>

    <button onclick="mostrar('login')">Entrar</button>
    <button class="secundario" onclick="mostrar('cadastro')">
      Criar conta
    </button>
  </section>

  <!-- CADASTRO -->
  <section id="cadastro" class="card oculto">
    <h2>Criar conta</h2>

    <input id="nome" type="text" placeholder="Nome completo">
    <input id="email" type="email" placeholder="E-mail">
    <input id="senha" type="password" placeholder="Criar senha">

    <button onclick="criarConta()">Criar conta</button>
    <button class="secundario" onclick="mostrar('inicio')">
      Voltar
    </button>
  </section>

  <!-- LOGIN -->
  <section id="login" class="card oculto">
    <h2>Entrar</h2>

    <input id="loginEmail" type="email" placeholder="E-mail">
    <input id="loginSenha" type="password" placeholder="Senha">

    <button onclick="entrar()">Entrar</button>
    <button class="secundario" onclick="mostrar('inicio')">
      Voltar
    </button>
  </section>

  <!-- PAINEL -->
  <section id="painel" class="oculto">

    <div class="card">
      <h2 id="saudacao">Olá 👋</h2>
      <p>Bem-vindo ao teu painel Bango V2.</p>

      <div class="saldo">
        <p>Saldo demonstrativo</p>
        <div class="valor">0,00 Kz</div>
      </div>

      <button onclick="alert('Função demonstrativa: adicionar dinheiro.')">
        Adicionar dinheiro
      </button>

      <button onclick="alert('Função demonstrativa: enviar dinheiro.')">
        Enviar dinheiro
      </button>

      <button class="secundario" onclick="sair()">
        Sair
      </button>
    </div>

    <div class="card">
      <h2>Oportunidades</h2>

      <div class="opcoes">

        <button class="opcao" onclick="abrirArea('Trabalho')">
          💼 Trabalho
        </button>

        <button class="opcao" onclick="abrirArea('Serviços')">
          🛠️ Serviços
        </button>

        <button class="opcao" onclick="abrirArea('Reciclagem')">
          ♻️ Reciclagem
        </button>

        <button class="opcao" onclick="abrirArea('Comunidade')">
          🤝 Comunidade
        </button>

      </div>
    </div>

  </section>

  <!-- ÁREA DE OPORTUNIDADE -->
  <section id="area" class="card oculto">

    <h2 id="tituloArea">Área</h2>

    <p id="textoArea">
      Bem-vindo a esta área do Bango V2.
    </p>

    <button onclick="alert('A função de publicar oportunidades será adicionada nesta próxima etapa.')">
      Publicar oportunidade
    </button>

    <button onclick="alert('A função de procurar oportunidades será adicionada nesta próxima etapa.')">
      Procurar oportunidades
    </button>

    <button class="secundario" onclick="voltarPainel()">
      Voltar ao painel
    </button>

  </section>

</div>

<footer>
  Bango V2 © 2026<br>
  Protótipo em desenvolvimento
</footer>

<script>

function esconderTudo() {
  document.getElementById("inicio").classList.add("oculto");
  document.getElementById("cadastro").classList.add("oculto");
  document.getElementById("login").classList.add("oculto");
  document.getElementById("painel").classList.add("oculto");
  document.getElementById("area").classList.add("oculto");
}

function mostrar(id) {
  esconderTudo();
  document.getElementById(id).classList.remove("oculto");
}

function criarConta() {

  let nome = document.getElementById("nome").value;
  let email = document.getElementById("email").value;
  let senha = document.getElementById("senha").value;

  if (!nome || !email || !senha) {
    alert("Preenche todos os campos.");
    return;
  }

  localStorage.setItem("bangoNome", nome);
  localStorage.setItem("bangoEmail", email);
  localStorage.setItem("bangoSenha", senha);

  alert("Conta criada com sucesso!");

  abrirPainel(nome);
}

function entrar() {

  let email = document.getElementById("loginEmail").value;
  let senha = document.getElementById("loginSenha").value;

  let emailGuardado = localStorage.getItem("bangoEmail");
  let senhaGuardada = localStorage.getItem("bangoSenha");
  let nome = localStorage.getItem("bangoNome");

  if (email === emailGuardado && senha === senhaGuardada) {
    abrirPainel(nome);
  } else {
    alert("E-mail ou senha incorretos.");
  }
}

function abrirPainel(nome) {

  esconderTudo();

  document.getElementById("painel").classList.remove("oculto");

  document.getElementById("saudacao").innerText =
    "Olá, " + nome + " 👋";
}

function abrirArea(nomeArea) {

  esconderTudo();

  document.getElementById("area").classList.remove("oculto");

  document.getElementById("tituloArea").innerText =
    nomeArea;

  document.getElementById("textoArea").innerText =
    "Encontra aqui oportunidades de " +
    nomeArea.toLowerCase() +
    " no Bango V2.";
}

function voltarPainel() {

  let nome = localStorage.getItem("bangoNome");

  abrirPainel(nome);
}

function sair() {

  esconderTudo();

  document.getElementById("inicio").classList.remove("oculto");
}

</script>

</body>
</html>
