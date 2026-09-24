# Atividade-2-HTML
Entregável - formulário

<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Estilização do Formulário de Inscrição</title>
    <!-- Ligação ao ficheiro CSS externo -->
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <!-- Container do Formulário com largura máxima e background distinto -->
    <div class="form-container">
        
        <h2>Formulário de Inscrição</h2>
        <p>Preencha os campos abaixo para concluir a sua inscrição.</p>

        <form action="#" method="get" class="form-flex">
            
            <!-- BÓNUS: Container para colocar os campos de Nome e E-mail lado a lado -->
            <div class="campos-lado-a-lado">
                <div class="campo-grupo">
                    <label for="nome">Nome Completo:</label>
                    <input type="text" id="nome" name="nome" placeholder="Seu nome" required>
                </div>

                <div class="campo-grupo">
                    <label for="email">E-mail de Contato:</label>
                    <input type="email" id="email" name="email" placeholder="seu@email.com" required>
                </div>
            </div>

            <!-- Outros campos organizados um abaixo do outro -->
            <div class="campo-grupo">
                <label for="nivel">Nível de Interesse:</label>
                <select id="nivel" name="nivel">
                    <option value="iniciante">Iniciante</option>
                    <option value="intermediario">Intermediário</option>
                    <option value="avancado">Avançado</option>
                </select>
            </div>

            <!-- Botão de Envio com Destaque Visual -->
            <button type="submit" class="btn-enviar">Enviar Inscrição</button>

        </form>

    </div>

</body>
</html>


/*Paleta de Cores & Animações Vibrantes*/
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap');

:root {
    --bg-gradient: linear-gradient(135deg, #ff9a9e 0%, #fecfef 50%, #a1c4fd 100%);
    --card-bg: #ffffff;
    --primary-gradient: linear-gradient(45deg, #ff007f, #7928ca);
    --primary-hover: linear-gradient(45deg, #e0006c, #6610f2);
    --text-main: #2d3748;
    --text-muted: #718096;
    --border-color: #e2e8f0;
    --focus-color: #ff007f;
    --radius-lg: 20px;
    --radius-md: 10px;
}

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Poppins', sans-serif;
    background: var(--bg-gradient);
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 2rem 1rem;
}

/*1. Container Principal (Visual Colorido & Moderno) */
.form-container {
    max-width: 650px;
    width: 100%;
    background-color: var(--card-bg);
    padding: 2.5rem;
    border-radius: var(--radius-lg);
    /* Sombras coloridas em camadas para dar profundidade */
    box-shadow: 0 20px 40px rgba(255, 0, 127, 0.15),
                0 10px 20px rgba(121, 40, 202, 0.1);
    border: 3px solid #ffffff;
    transition: transform 0.3s ease;
}

.form-container:hover {
    transform: translateY(-4px);
}

.form-container h2 {
    font-size: 2rem;
    font-weight: 700;
    /* Texto com gradiente colorido */
    background: var(--primary-gradient);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    margin-bottom: 0.5rem;
}

.form-container p {
    color: var(--text-muted);
    font-size: 0.95rem;
    margin-bottom: 1.8rem;
}

/* 2. Organização Flexbox (Exigência Principal)*/
.form-flex {
    display: flex;
    flex-direction: column;
    gap: 1.4rem;
}

.campo-grupo {
    display: flex;
    flex-direction: column;
    flex: 1;
}

/*3. Estilização dos Rótulos (Labels), Inputs e Selects*/
label {
    font-weight: 600;
    font-size: 0.9rem;
    margin-bottom: 0.5rem;
    color: var(--text-main);
    display: flex;
    align-items: center;
    gap: 0.4rem;
}

input, select {
    padding: 0.9rem 1.1rem;
    border: 2px solid var(--border-color);
    border-radius: var(--radius-md);
    font-size: 0.95rem;
    font-family: inherit;
    color: var(--text-main);
    background-color: #f8fafc;
    transition: all 0.3s ease;
    outline: none;
}

/* Efeito ao Clicar/Focar nos Campos */
input:focus, select:focus {
    background-color: #ffffff;
    border-color: var(--focus-color);
    box-shadow: 0 0 0 4px rgba(255, 0, 127, 0.15);
}

/* Alteração da cor do texto de exemplo (Placeholder) */
input::placeholder {
    color: #a0aec0;
}

/* 4. Botão de Enviar com Destaque Visual + Efeito Hover */
.btn-enviar {
    background: var(--primary-gradient);
    color: #ffffff;
    padding: 1rem;
    border: none;
    border-radius: var(--radius-md);
    font-size: 1.05rem;
    font-weight: 700;
    letter-spacing: 0.5px;
    cursor: pointer;
    margin-top: 0.5rem;
    box-shadow: 0 10px 20px rgba(255, 0, 127, 0.3);
    transition: all 0.3s ease;
}

.btn-enviar:hover {
    background: var(--primary-hover);
    transform: translateY(-2px);
    box-shadow: 0 12px 25px rgba(255, 0, 127, 0.45);
}

.btn-enviar:active {
    transform: translateY(0);
}

/* 5. BÓNUS: Flexbox Lado a Lado para Nome e E-mail */
.campos-lado-a-lado {
    display: flex;
    justify-content: space-between;
    gap: 1.2rem;
}

/* Responsividade: ajusta para telas menores/telemóveis */
@media (max-width: 580px) {
    .campos-lado-a-lado {
        flex-direction: column;
    }

    .form-container {
        padding: 1.8rem 1.2rem;
    }
}
