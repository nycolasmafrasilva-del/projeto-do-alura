<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meu Blog Tech</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f7f6;
            color: #333;
        }
        
        /* 1. FLEXBOX NO HEADER */
        header {
            background-color: #1a1a2e;
            color: #ffffff;
            padding: 40px 20px;
            border-bottom: 4px solid #00adb5;
            
            display: flex;               /* Ativa o Flexbox */
            flex-direction: column;      /* Alinha os itens em coluna (um embaixo do outro) */
            align-items: center;         /* Centraliza horizontalmente */
            justify-content: center;     /* Centraliza verticalmente */
            text-align: center;
        }
        
        h1 {
            font-size: 3rem;
            margin: 0 0 10px 0;
            text-transform: uppercase;
            letter-spacing: 2px;
        }
        p.subtitulo {
            font-size: 0.9rem;
            color: #bfa3ff;
            margin: 0;
            font-style: italic;
        }
        .conteudo {
            max-width: 800px;
            margin: 40px auto;
            padding: 0 20px;
        }
        .artigo {
            background-color: #ffffff;
            padding: 25px;
            margin-bottom: 25px;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.05);
        }
        .artigo h2 {
            margin-top: 0;
            color: #1a1a2e;
        }
        .artigo h2 a {
            color: #1a1a2e;
            text-decoration: none;
        }
        .artigo h2 a:hover {
            color: #00adb5;
        }
        .data-post {
            font-size: 0.85rem;
            color: #777;
            margin-bottom: 15px;
        }
        
        /* 2. FLEXBOX NO RODAPÉ DO ARTIGO */
        .rodape-artigo {
            margin-top: 20px;
            padding-top: 15px;
            border-top: 1px solid #eee;
            
            display: flex;               /* Ativa o Flexbox */
            justify-content: space-between; /* Empurra um item para a esquerda e o outro para a direita */
            align-items: center;         /* Alinha o botão de texto e o botão de coração na mesma linha horizontal */
        }
        
        .botao-ler {
            color: #00adb5;
            text-decoration: none;
            font-weight: bold;
        }
        .botao-ler:hover {
            text-decoration: underline;
        }
        
        /* 3. FLEXBOX INTERNO DO BOTÃO DE GOSTEI */
        .botao-gostei {
            background: none;
            border: 1px solid #ccc;
            padding: 6px 12px;
            border-radius: 20px;
            cursor: pointer;
            color: #555;
            transition: all 0.2s ease;
            
            display: flex;               /* Ativa o Flexbox dentro do botão */
            align-items: center;         /* Alinha o coração e o número perfeitamente no meio */
            gap: 6px;                    /* Cria um espaço fixo de 6px entre o coração e o número */
            font-size: 0.9rem;
        }
        .botao-gostei:hover {
            background-color: #ffe6e6;
            border-color: #ff4d4d;
            color: #ff4d4d;
        }
        .botao-gostei.ativo {
            background-color: #ff4d4d;
            border-color: #ff4d4d;
            color: white;
        }
        .icone-coracao {
            font-size: 1.1rem;
        }
        footer {
            background-color: #1a1a2e;
            color: #ffffff;
            text-align: center;
            padding: 20px;
            font-size: 0.9rem;
            margin-top: 50px;
        }
    </style>
</head>
<body>

    <header>
        <h1>Meu Blog Tech</h1>
        <p class="subtitulo">Compartilhando conhecimento sobre tecnologia e programação</p>
    </header>

    <main class="conteudo">
        
        <article class="artigo">
            <h2><a href="#">Meu Primeiro Post: Por onde começar na programação?</a></h2>
            <div class="data-post">Postado em 18 de Junho de 2026</div>
            <p>Se você está iniciando no mundo do desenvolvimento, focar na tríade HTML, CSS e JavaScript é o melhor caminho. Neste post, explico a função de cada uma dessas tecnologias...</p>
            
            <div class="rodape-artigo">
                <a href="#" class="botao-ler">Ler mais →</a>
                <button class="botao-gostei" onclick="curtir(this)">
                    <span class="icone-coracao">♥</span> <span class="contador">0</span>
                </button>
            </div>
        </article>

        <article class="artigo">
            <h2><a href="#">Por que o CSS Semântico é importante?</a></h2>
            <div class="data-post">Postado em 15 de Junho de 2026</div>
            <p>Usar tags HTML corretas, como <code style="background: #eee; padding: 2px 4px; border-radius: 4px;">&lt;main&gt;</code> e <code style="background: #eee; padding: 2px 4px; border-radius: 4px;">&lt;article&gt;</code>, melhora drasticamente a acessibilidade do seu site e o SEO nos motores de busca...</p>
            
            <div class="rodape-artigo">
                <a href="#" class="botao-ler">Ler mais →</a>
                <button class="botao-gostei" onclick="curtir(this)">
                    <span class="icone-coracao">♥</span> <span class="contador">0</span>
                </button>
            </div>
        </article>

    </main>

    <footer>
        <p>&copy; 2026 Meu Blog Tech - Todos os direitos reservados.</p>
    </footer>

    <script>
        function curtir(botao) {
            const contadorElemento = botao.querySelector('.contador');
            let curtidas = parseInt(contadorElemento.innerText);

            if (botao.classList.contains('ativo')) {
                botao.classList.remove('ativo');
                curtidas--;
            } else {
                botao.classList.add('ativo');
                curtidas++;
            }

            contadorElemento.innerText = curtidas;
        }
    </script>

</body>
</html>
