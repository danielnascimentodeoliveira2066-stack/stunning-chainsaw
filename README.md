.

<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Eleição Mirim</title>
<style>
body {
  font-family: Arial, sans-serif;
  background: #eaf3ff;
  text-align: center;
  padding: 20px;
}
header {
  background: #0755b5;
  color: white;
  padding: 22px;
  border-radius: 15px;
}
.card {
  background: white;
  padding: 20px;
  margin: 15px auto;
  border-radius: 15px;
  max-width: 400px;
  box-shadow: 0 3px 10px #bbb;
}
button {
  background: #087bdb;
  color: white;
  border: none;
  padding: 14px 25px;
  border-radius: 10px;
  font-size: 17px;
  cursor: pointer;
}
#resultado {
  font-size: 18px;
  font-weight: bold;
}
</style>
</head>
<body>

<header>
  <h1>🗳️ ELEIÇÃO MIRIM</h1>
  <p>Uma votação educativa e divertida!</p>
</header>

<div class="card">
  <h2>Escolha seu personagem favorito!</h2>
  <p>Esta é uma simulação educativa.</p>

  <button onclick="votar('Ana')">Votar em Ana ⭐</button>
  <br><br>
  <button onclick="votar('Lucas')">Votar em Lucas ⭐</button>
  <br><br>
  <button onclick="votar('Maria')">Votar em Maria ⭐</button>
</div>

<div class="card">
  <h2>📊 Resultado</h2>
  <p id="resultado">Nenhum voto ainda.</p>
  <button onclick="mostrar()">Ver resultado</button>
</div>

<script>
let votos = JSON.parse(
  localStorage.getItem("votos") ||
  '{"Ana":0,"Lucas":0,"Maria":0}'
);

function votar(nome) {
  votos[nome]++;
  localStorage.setItem("votos", JSON.stringify(votos));
  alert("Voto registrado nesta simulação!");
}

function mostrar() {
  document.getElementById("resultado").innerHTML =
    "Ana: " + votos.Ana + "<br>" +
    "Lucas: " + votos.Lucas + "<br>" +
    "Maria: " + votos.Maria;
}
</script>

</body>
</html>
