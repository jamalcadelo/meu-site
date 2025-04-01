<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Página de Login</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="login-container">
        <h2>Entrar na Conta</h2>
        <form id="loginForm">
            <div class="input-group">
                <label for="username">Usuário:</label>
                <input type="text" id="username" name="username" placeholder="Digite seu nome de usuário" required>
            </div>
            <div class="input-group">
                <label for="password">Senha:</label>
                <input type="password" id="password" name="password" placeholder="Digite sua senha" required>
            </div>
            <button type="submit">Entrar</button>
            <div id="error-message" class="error"></div>
        </form>
    </div>

    <script src="script.js"></script>
</body>
<style>
/* Estilos gerais */
body {
    font-family: Arial, sans-serif;
    background: linear-gradient(45deg, #6a5acd, #ff69b4); /* Gradiente azul e rosa */
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}

/* Estilos para o container do login */
.login-container {
    background-color: #fff;
    padding: 30px;
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    width: 300px;
    text-align: center;
}

/* Título */
h2 {
    color: #6a5acd; /* Cor azul */
    margin-bottom: 20px;
}

/* Estilos dos campos de entrada */
.input-group {
    margin-bottom: 20px;
}

.input-group label {
    font-size: 14px;
    color: #333;
    display: block;
    margin-bottom: 5px;
}

.input-group input {
    width: 100%;
    padding: 10px;
    font-size: 16px;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
}

/* Estilos do botão de login */
button {
    width: 100%;
    padding: 12px;
    font-size: 16px;
    background-color: #ff69b4; /* Cor rosa */
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s;
}

button:hover {
    background-color: #ff1493; /* Rosa mais escuro */
}

/* Estilos da mensagem de erro */
.error {
    color: red;
    font-size: 14px;
    margin-top: 10px;
}
</style>
<script>
document.getElementById('loginForm').addEventListener('submit', function(event) {
    event.preventDefault(); // Impede o envio do formulário para testar a validação

    var username = document.getElementById('username').value;
    var password = document.getElementById('password').value;
    var errorMessage = document.getElementById('error-message');

    // Verifica se os campos estão preenchidos
    if (username === "" || password === "") {
        errorMessage.textContent = "Por favor, preencha todos os campos.";
    } else if (username === "usuario" && password === "senha123") {
        // Simula um login bem-sucedido
        errorMessage.textContent = "Login bem-sucedido!";
        errorMessage.style.color = "green";
    } else {
        // Caso o login falhe
        errorMessage.textContent = "Usuário ou senha incorretos.";
    }
});
</script>
</html>
