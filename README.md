# CODJAVASCRIPTIDADE
CÓDIGO CRIADO EM JAVASCRIPT QUE ME DA O RESULTADO DE IDADE E SIGNO ATRAVES DO MÊS E ANO DE NASCIMENTO.

<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora de Idade e Signo</title>
</head>
<body>
    <h1>Calculadora de Idade e Signo</h1>

    <label for="anoNascimento">Digite seu ano de nascimento:</label>
    <input type="number" id="anoNascimento" placeholder="Ano de nascimento">
    <br><br>

    <label for="mesNascimento">Digite seu mês de nascimento:</label>
    <input type="number" id="mesNascimento" placeholder="Mês (1-12)">
    <br><br>

    <label for="diaNascimento">Digite seu dia de nascimento:</label>
    <input type="number" id="diaNascimento" placeholder="Dia (1-31)">
    <br><br>

    <button onclick="calcularIdadeESigno()">Calcular</button>

    <h2>Resultados:</h2>
    <p id="resultadoIdade"></p>
    <p id="resultadoSigno"></p>

    <script>
        function calcularIdadeESigno() {
            // Obtendo os valores dos inputs
            const anoNascimento = parseInt(document.getElementById("anoNascimento").value);
            const mesNascimento = parseInt(document.getElementById("mesNascimento").value);
            const diaNascimento = parseInt(document.getElementById("diaNascimento").value);

            // Verificando se os inputs são válidos
            if (!anoNascimento || !mesNascimento || !diaNascimento) {
                alert("Por favor, preencha todos os campos corretamente.");
                return;
            }

            // Calculando a idade
            const dataAtual = new Date();
            const anoAtual = dataAtual.getFullYear();
            const mesAtual = dataAtual.getMonth() + 1; // Meses começam do 0, então adicionamos 1
            const diaAtual = dataAtual.getDate();

            let idade = anoAtual - anoNascimento;

            // Verificando se já fez aniversário este ano
            if (mesAtual < mesNascimento || (mesAtual === mesNascimento && diaAtual < diaNascimento)) {
                idade--;
            }

            // Calculando o signo
            let signo = "";
            if ((mesNascimento == 3 && diaNascimento >= 21) || (mesNascimento == 4 && diaNascimento <= 19)) {
                signo = "Áries";
            } else if ((mesNascimento == 4 && diaNascimento >= 20) || (mesNascimento == 5 && diaNascimento <= 20)) {
                signo = "Touro";
            } else if ((mesNascimento == 5 && diaNascimento >= 21) || (mesNascimento == 6 && diaNascimento <= 20)) {
                signo = "Gêmeos";
            } else if ((mesNascimento == 6 && diaNascimento >= 21) || (mesNascimento == 7 && diaNascimento <= 22)) {
                signo = "Câncer";
            } else if ((mesNascimento == 7 && diaNascimento >= 23) || (mesNascimento == 8 && diaNascimento <= 22)) {
                signo = "Leão";
            } else if ((mesNascimento == 8 && diaNascimento >= 23) || (mesNascimento == 9 && diaNascimento <= 22)) {
                signo = "Virgem";
            } else if ((mesNascimento == 9 && diaNascimento >= 23) || (mesNascimento == 10 && diaNascimento <= 22)) {
                signo = "Libra";
            } else if ((mesNascimento == 10 && diaNascimento >= 23) || (mesNascimento == 11 && diaNascimento <= 21)) {
                signo = "Escorpião";
            } else if ((mesNascimento == 11 && diaNascimento >= 22) || (mesNascimento == 12 && diaNascimento <= 21)) {
                signo = "Sagitário";
            } else if ((mesNascimento == 12 && diaNascimento >= 22) || (mesNascimento == 1 && diaNascimento <= 19)) {
                signo = "Capricórnio";
            } else if ((mesNascimento == 1 && diaNascimento >= 20) || (mesNascimento == 2 && diaNascimento <= 18)) {
                signo = "Aquário";
            } else if ((mesNascimento == 2 && diaNascimento >= 19) || (mesNascimento == 3 && diaNascimento <= 20)) {
                signo = "Peixes";
            }

            // Exibindo o resultado
            document.getElementById("resultadoIdade").textContent = `Sua idade é: ${idade} anos.`;
            document.getElementById("resultadoSigno").textContent = `Seu signo é: ${signo}.`;
        }
    </script>
</body>
</html>

