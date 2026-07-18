<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>💖 Isa Calculadora Divina 💖</title>
    <style>
        /* ===== RESET E FONTE ===== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', 'Quicksand', system-ui, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background: #1a0b1f;
            overflow: hidden;
            position: relative;
        }

        /* ===== FUNDO ANIMADO COM CORAÇÕES ===== */
        .heart-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
            overflow: hidden;
        }

        .heart {
            position: absolute;
            bottom: -100px;
            font-size: 2rem;
            animation: floatUp linear infinite;
            user-select: none;
            filter: drop-shadow(0 0 10px rgba(255, 80, 160, 0.5));
        }

        @keyframes floatUp {
            0% {
                transform: translateY(0) rotate(0deg) scale(0.6);
                opacity: 0.3;
            }
            50% {
                opacity: 0.9;
            }
            100% {
                transform: translateY(-120vh) rotate(720deg) scale(1.4);
                opacity: 0;
            }
        }

        /* ===== NOME "ISA" COM ESTILO LUXUOSO ===== */
        .nome-isa {
            position: fixed;
            top: 22px;
            left: 50%;
            transform: translateX(-50%);
            z-index: 5;
            font-size: 3rem;
            font-weight: 800;
            letter-spacing: 8px;
            background: linear-gradient(135deg, #ffb6d9, #ff7eb3, #ff4d94, #ff6eb4);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            animation: brilhoNome 4s ease-in-out infinite;
            text-shadow: 0 0 40px rgba(255, 80, 160, 0.3);
            font-family: 'Quicksand', 'Segoe UI', sans-serif;
            padding: 0 30px;
            backdrop-filter: blur(4px);
            border-radius: 80px;
            white-space: nowrap;
        }

        @keyframes brilhoNome {
            0%,
            100% {
                background-position: 0% 50%;
                text-shadow: 0 0 40px rgba(255, 80, 160, 0.3);
            }
            50% {
                background-position: 100% 50%;
                text-shadow: 0 0 80px rgba(255, 80, 160, 0.6), 0 0 120px rgba(255, 50, 150, 0.3);
            }
        }

        /* ===== RELÓGIO DIGITAL ===== */
        .relogio-container {
            position: fixed;
            top: 95px;
            left: 50%;
            transform: translateX(-50%);
            z-index: 5;
            background: rgba(255, 200, 220, 0.08);
            backdrop-filter: blur(12px);
            padding: 12px 32px;
            border-radius: 80px;
            border: 1px solid rgba(255, 150, 200, 0.2);
            box-shadow: 0 8px 40px rgba(255, 80, 160, 0.15), inset 0 1px 0 rgba(255, 255, 255, 0.05);
            text-align: center;
            font-size: 1.9rem;
            font-weight: 500;
            letter-spacing: 4px;
            color: #ffe2f0;
            text-shadow: 0 0 20px #ff8eb5;
            font-variant-numeric: tabular-nums;
            min-width: 180px;
        }

        .relogio-digital {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .relogio-digital span {
            background: rgba(255, 200, 220, 0.05);
            padding: 0 8px;
            border-radius: 16px;
            min-width: 40px;
            text-align: center;
        }

        .relogio-digital .dois-pontos {
            animation: piscar 1s infinite;
            font-weight: 300;
            color: #ffb0cf;
            min-width: 12px;
            padding: 0;
            background: transparent;
        }

        @keyframes piscar {
            0%,
            100% {
                opacity: 1;
            }
            50% {
                opacity: 0.15;
            }
        }

        /* ===== CALCULADORA COMPLETA E LINDÍSSIMA ===== */
        .calculadora {
            position: relative;
            z-index: 10;
            background: rgba(25, 10, 24, 0.65);
            backdrop-filter: blur(24px);
            padding: 32px 26px 34px;
            border-radius: 56px;
            box-shadow:
                0 30px 80px rgba(255, 80, 160, 0.2),
                0 0 0 1px rgba(255, 160, 200, 0.12),
                inset 0 1px 0 rgba(255, 255, 255, 0.06);
            width: 400px;
            margin-top: 50px;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 180, 210, 0.08);
        }

        .calculadora:hover {
            box-shadow: 0 35px 90px rgba(255, 80, 160, 0.3), 0 0 0 1px rgba(255, 160, 200, 0.2);
        }

        /* ===== VISOR MELHORADO - MOSTRA A EXPRESSÃO COMPLETA ===== */
        .visor-container {
            width: 100%;
            background: rgba(12, 5, 12, 0.7);
            border: 1px solid rgba(255, 150, 200, 0.15);
            border-radius: 32px;
            margin-bottom: 24px;
            padding: 16px 20px;
            box-shadow: inset 0 6px 20px rgba(0, 0, 0, 0.5);
            backdrop-filter: blur(4px);
            background: rgba(18, 8, 18, 0.5);
            min-height: 110px;
            display: flex;
            flex-direction: column;
            justify-content: flex-end;
            align-items: flex-end;
            transition: all 0.2s;
        }

        .visor-container:focus-within {
            border-color: rgba(255, 130, 180, 0.4);
            box-shadow: inset 0 6px 20px rgba(0, 0, 0, 0.5), 0 0 30px rgba(255, 80, 160, 0.05);
        }

        /* Expressão que está sendo digitada */
        .visor-expressao {
            width: 100%;
            color: #ffb0cf;
            font-size: 1.3rem;
            font-weight: 300;
            text-align: right;
            word-wrap: break-word;
            overflow-wrap: break-word;
            min-height: 30px;
            line-height: 1.4;
            font-family: 'Segoe UI', 'Quicksand', sans-serif;
            letter-spacing: 1px;
            padding-bottom: 4px;
            border: none;
            outline: none;
            background: transparent;
            resize: none;
            color: #ffc8dd;
        }

        .visor-expressao:empty::before {
            content: 'Digite sua conta...';
            color: rgba(255, 180, 210, 0.2);
            font-weight: 200;
        }

        /* Resultado em destaque */
        .visor-resultado {
            width: 100%;
            color: #fff2f7;
            font-size: 2.6rem;
            font-weight: 600;
            text-align: right;
            word-wrap: break-word;
            overflow-wrap: break-word;
            min-height: 45px;
            line-height: 1.2;
            font-family: 'Segoe UI', 'Quicksand', sans-serif;
            letter-spacing: 2px;
            border: none;
            outline: none;
            background: transparent;
            transition: all 0.2s;
        }

        .visor-resultado:empty::before {
            content: '0';
            color: rgba(255, 255, 255, 0.1);
            font-weight: 200;
        }

        /* ===== GRADE DE BOTÕES ===== */
        .botoes {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 14px;
        }

        /* ===== BOTÕES BASE ===== */
        button {
            padding: 20px 6px;
            font-size: 1.4rem;
            font-weight: 600;
            border: none;
            border-radius: 44px;
            cursor: pointer;
            transition: all 0.15s ease;
            background: rgba(55, 28, 50, 0.5);
            color: #f5dce8;
            backdrop-filter: blur(4px);
            border: 1px solid rgba(255, 150, 200, 0.06);
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.15);
            font-family: 'Quicksand', 'Segoe UI', sans-serif;
            position: relative;
            overflow: hidden;
        }

        button::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255, 255, 255, 0.03) 0%, transparent 70%);
            opacity: 0;
            transition: opacity 0.3s;
            pointer-events: none;
        }

        button:hover::after {
            opacity: 1;
        }

        button:active {
            transform: scale(0.92);
            background: rgba(255, 120, 180, 0.15);
        }

        /* ===== NÚMEROS ===== */
        button.numero {
            background: rgba(65, 32, 60, 0.5);
            border-color: rgba(255, 150, 200, 0.05);
        }

        button.numero:hover {
            background: rgba(160, 70, 130, 0.25);
            border-color: rgba(255, 150, 200, 0.2);
            box-shadow: 0 0 25px rgba(255, 80, 160, 0.05);
        }

        /* ===== OPERADORES ===== */
        button.operador {
            background: rgba(255, 100, 150, 0.15);
            color: #ffb6d9;
            border-color: rgba(255, 100, 150, 0.1);
            font-weight: 700;
        }

        button.operador:hover {
            background: rgba(255, 80, 140, 0.3);
            border-color: #ff8eb5;
            box-shadow: 0 0 30px rgba(255, 80, 160, 0.15);
            transform: translateY(-2px);
        }

        /* ===== BOTÃO LIMPAR (C) ===== */
        button.limpar {
            background: rgba(255, 50, 90, 0.2);
            color: #ff9bb5;
            border-color: rgba(255, 50, 90, 0.1);
        }

        button.limpar:hover {
            background: rgba(255, 40, 80, 0.35);
            border-color: #ff6b8a;
            box-shadow: 0 0 30px rgba(255, 40, 80, 0.15);
        }

        /* ===== IGUAL (DESTAQUE) ===== */
        button.igual {
            background: linear-gradient(145deg, #ff7eb3, #e85a8a);
            color: #fff2f7;
            border: none;
            box-shadow: 0 6px 30px rgba(255, 60, 140, 0.35);
            grid-column: span 2;
            font-weight: 700;
            letter-spacing: 3px;
            font-size: 1.6rem;
        }

        button.igual:hover {
            background: linear-gradient(145deg, #ff90c0, #f06a9a);
            box-shadow: 0 8px 40px rgba(255, 60, 140, 0.5);
            transform: scale(1.03) translateY(-2px);
        }

        /* ===== BACKSPACE ===== */
        button.apagar {
            background: rgba(180, 80, 140, 0.15);
            color: #f0c0d8;
        }

        button.apagar:hover {
            background: rgba(200, 100, 160, 0.25);
            border-color: rgba(255, 150, 200, 0.15);
        }

        /* ===== BOTÃO PORCENTAGEM ===== */
        button.porcentagem {
            background: rgba(180, 80, 140, 0.12);
            color: #f0c0d8;
        }

        button.porcentagem:hover {
            background: rgba(200, 100, 160, 0.22);
        }

        /* ===== BOTÃO PARÊNTESES ===== */
        button.parenteses {
            background: rgba(180, 80, 140, 0.1);
            color: #e8c0d8;
            font-size: 1.2rem;
        }

        button.parenteses:hover {
            background: rgba(200, 100, 160, 0.2);
        }

        /* ===== BOTÃO VÍRGULA ===== */
        button.ponto {
            background: rgba(65, 32, 60, 0.5);
            border-color: rgba(255, 150, 200, 0.05);
        }

        button.ponto:hover {
            background: rgba(160, 70, 130, 0.25);
            border-color: rgba(255, 150, 200, 0.2);
        }

        /* ===== RESPONSIVIDADE ===== */
        @media (max-width: 480px) {
            .calculadora {
                width: 320px;
                padding: 22px 16px 26px;
                border-radius: 40px;
            }

            .visor-container {
                min-height: 90px;
                padding: 12px 16px;
                border-radius: 26px;
            }

            .visor-expressao {
                font-size: 1.0rem;
                min-height: 24px;
            }

            .visor-resultado {
                font-size: 2.0rem;
                min-height: 36px;
            }

            button {
                padding: 16px 4px;
                font-size: 1.1rem;
                border-radius: 36px;
            }

            .nome-isa {
                font-size: 2.2rem;
                top: 16px;
                letter-spacing: 5px;
                padding: 0 16px;
            }

            .relogio-container {
                top: 78px;
                font-size: 1.4rem;
                padding: 8px 18px;
                min-width: 140px;
                border-radius: 60px;
            }

            .relogio-digital span {
                min-width: 30px;
                padding: 0 4px;
            }

            button.igual {
                font-size: 1.3rem;
            }
        }

        @media (max-width: 380px) {
            .calculadora {
                width: 280px;
                padding: 18px 12px 22px;
                gap: 10px;
            }

            .botoes {
                gap: 10px;
            }

            button {
                padding: 14px 2px;
                font-size: 1.0rem;
                border-radius: 30px;
            }

            .visor-container {
                min-height: 75px;
                padding: 10px 12px;
            }

            .visor-expressao {
                font-size: 0.85rem;
                min-height: 20px;
            }

            .visor-resultado {
                font-size: 1.6rem;
                min-height: 30px;
            }

            .nome-isa {
                font-size: 1.8rem;
                top: 12px;
                letter-spacing: 3px;
            }

            .relogio-container {
                top: 62px;
                font-size: 1.1rem;
                padding: 6px 14px;
                min-width: 110px;
            }
        }
    </style>
</head>
<body>

    <!-- ===== FUNDO DE CORAÇÕES ===== -->
    <div class="heart-bg" id="heartBg"></div>

    <!-- ===== NOME "ISA" ===== -->
    <div class="nome-isa">✦ Isa ✦</div>

    <!-- ===== RELÓGIO DIGITAL ===== -->
    <div class="relogio-container">
        <div class="relogio-digital" id="relogioDigital">
            <span id="horas">00</span>
            <span class="dois-pontos">:</span>
            <span id="minutos">00</span>
            <span class="dois-pontos">:</span>
            <span id="segundos">00</span>
        </div>
    </div>

    <!-- ===== CALCULADORA COMPLETA ===== -->
    <div class="calculadora">
        <div class="visor-container">
            <div class="visor-expressao" id="visorExpressao" contenteditable="false"></div>
            <div class="visor-resultado" id="visorResultado" contenteditable="false"></div>
        </div>

        <div class="botoes">
            <!-- Linha 1: C, ⌫, %, ÷ -->
            <button class="limpar" onclick="limparVisor()">C</button>
            <button class="apagar" onclick="apagarUltimo()">⌫</button>
            <button class="porcentagem" onclick="inserirPorcentagem()">%</button>
            <button class="operador" onclick="inserir('÷')">÷</button>

            <!-- Linha 2: 7, 8, 9, × -->
            <button class="numero" onclick="inserir('7')">7</button>
            <button class="numero" onclick="inserir('8')">8</button>
            <button class="numero" onclick="inserir('9')">9</button>
            <button class="operador" onclick="inserir('×')">×</button>

            <!-- Linha 3: 4, 5, 6, − -->
            <button class="numero" onclick="inserir('4')">4</button>
            <button class="numero" onclick="inserir('5')">5</button>
            <button class="numero" onclick="inserir('6')">6</button>
            <button class="operador" onclick="inserir('−')">−</button>

            <!-- Linha 4: 1, 2, 3, + -->
            <button class="numero" onclick="inserir('1')">1</button>
            <button class="numero" onclick="inserir('2')">2</button>
            <button class="numero" onclick="inserir('3')">3</button>
            <button class="operador" onclick="inserir('+')">+</button>

            <!-- Linha 5: 0, ., ( , ) -->
            <button class="numero" onclick="inserir('0')">0</button>
            <button class="ponto" onclick="inserir('.')">.</button>
            <button class="parenteses" onclick="inserir('(')">(</button>
            <button class="parenteses" onclick="inserir(')')">)</button>

            <!-- Linha 6: = (ocupa 2 colunas) -->
            <button class="igual" onclick="calcular()">=</button>
        </div>
    </div>

    <script>
        // ============================================================
        // 1. CORAÇÕES ANIMADOS (GERADOR CONTÍNUO)
        // ============================================================
        (function criarCoracoes() {
            const bg = document.getElementById('heartBg');
            const emojis = ['♥', '❤️', '💖', '💗', '💕', '🌸', '✨', '💓', '🩷', '💞', '💝', '🌟'];
            const numCoracoes = 40;

            for (let i = 0; i < numCoracoes; i++) {
                const heart = document.createElement('div');
                heart.className = 'heart';
                heart.textContent = emojis[Math.floor(Math.random() * emojis.length)];
                heart.style.left = Math.random() * 100 + '%';
                heart.style.fontSize = (1.2 + Math.random() * 3.0) + 'rem';
                heart.style.animationDuration = (14 + Math.random() * 22) + 's';
                heart.style.animationDelay = (Math.random() * 25) + 's';
                heart.style.opacity = 0.25 + Math.random() * 0.6;
                const rotacao = Math.random() * 40 - 20;
                heart.style.transform = `rotate(${rotacao}deg)`;
                bg.appendChild(heart);
            }

            const especiais = ['💖', '💗', '💞', '🩷'];
            for (let i = 0; i < 6; i++) {
                const heart = document.createElement('div');
                heart.className = 'heart';
                heart.textContent = especiais[i % especiais.length];
                heart.style.left = (10 + Math.random() * 80) + '%';
                heart.style.fontSize = (3.0 + Math.random() * 2.0) + 'rem';
                heart.style.animationDuration = (20 + Math.random() * 18) + 's';
                heart.style.animationDelay = (Math.random() * 30) + 's';
                heart.style.opacity = 0.3 + Math.random() * 0.4;
                bg.appendChild(heart);
            }
        })();

        // ============================================================
        // 2. RELÓGIO DIGITAL
        // ============================================================
        function atualizarRelogio() {
            const agora = new Date();
            const h = String(agora.getHours()).padStart(2, '0');
            const m = String(agora.getMinutes()).padStart(2, '0');
            const s = String(agora.getSeconds()).padStart(2, '0');

            document.getElementById('horas').textContent = h;
            document.getElementById('minutos').textContent = m;
            document.getElementById('segundos').textContent = s;
        }

        atualizarRelogio();
        setInterval(atualizarRelogio, 1000);

        // ============================================================
        // 3. CALCULADORA COMPLETA COM VISOR DE EXPRESSÃO
        // ============================================================
        const visorExpressao = document.getElementById('visorExpressao');
        const visorResultado = document.getElementById('visorResultado');

        // Expressão interna (visível) e expressão para cálculo
        let expressaoVisivel = '';
        let expressaoCalculo = '';

        function atualizarVisor() {
            visorExpressao.textContent = expressaoVisivel;
        }

        // Inserir valor no visor
        function inserir(valor) {
            // Evita começar com operadores inválidos
            if (expressaoVisivel === '' && ['+', '×', '÷', '%', '*', '/'].includes(valor)) return;
            
            // Converte para símbolos visuais bonitos
            let valVisivel = valor;
            let valCalculo = valor;
            
            if (valVisivel === '*') { valVisivel = '×'; valCalculo = '*'; }
            else if (valVisivel === '/') { valVisivel = '÷'; valCalculo = '/'; }
            else if (valVisivel === '-') { valVisivel = '−'; valCalculo = '-'; }
            
            // Se for um número, mantém
            expressaoVisivel += valVisivel;
            expressaoCalculo += valCalculo;
            
            atualizarVisor();
            // Limpa o resultado anterior quando digita algo novo
            visorResultado.textContent = '';
        }

        // Inserir porcentagem
        function inserirPorcentagem() {
            if (expressaoVisivel === '') return;
            
            // Encontra o último número na expressão
            const match = expressaoVisivel.match(/([\d.]+)$/);
            
            if (match) {
                const numero = match[1];
                const posicao = expressaoVisivel.lastIndexOf(numero);
                const antes = expressaoVisivel.substring(0, posicao);
                const depois = expressaoVisivel.substring(posicao + numero.length);
                
                expressaoVisivel = antes + `(${numero}%)` + depois;
                
                // Para o cálculo, converte para (numero/100)
                const antesCalc = expressaoCalculo.substring(0, posicao);
                const depoisCalc = expressaoCalculo.substring(posicao + numero.length);
                expressaoCalculo = antesCalc + `(${numero}/100)` + depoisCalc;
                
                atualizarVisor();
                visorResultado.textContent = '';
            } else {
                expressaoVisivel += '%';
                expressaoCalculo += '%';
                atualizarVisor();
            }
        }

        // Limpar tudo
        function limparVisor() {
            expressaoVisivel = '';
            expressaoCalculo = '';
            visorResultado.textContent = '';
            atualizarVisor();
        }

        // Apagar último caractere
        function apagarUltimo() {
            if (expressaoVisivel.length === 0) return;
            
            // Remove o último caractere da expressão visível
            const ultimoChar = expressaoVisivel.charAt(expressaoVisivel.length - 1);
            
            // Se o último caractere for ')' de porcentagem, remove tudo de uma vez
            if (ultimoChar === ')' && expressaoVisivel.includes('(%)')) {
                // Remove o padrão (numero%)
                const match = expressaoVisivel.match(/\([\d.]+%\)$/);
                if (match) {
                    const remover = match[0];
                    expressaoVisivel = expressaoVisivel.slice(0, -remover.length);
                    // Remove da expressão de cálculo também
                    const matchCalc = expressaoCalculo.match(/\([\d.]+\/100\)$/);
                    if (matchCalc) {
                        expressaoCalculo = expressaoCalculo.slice(0, -matchCalc[0].length);
                    }
                    atualizarVisor();
                    visorResultado.textContent = '';
                    return;
                }
            }
            
            expressaoVisivel = expressaoVisivel.slice(0, -1);
            expressaoCalculo = expressaoCalculo.slice(0, -1);
            atualizarVisor();
            visorResultado.textContent = '';
        }

        // Calcular expressão
        function calcular() {
            try {
                if (expressaoVisivel === '' && expressaoCalculo === '') return;

                let expr = expressaoCalculo;
                
                // Se não tem operador, apenas mostra o número
                if (!expr.includes('+') && !expr.includes('-') && !expr.includes('*') && !expr.includes('/')) {
                    visorResultado.textContent = expr;
                    return;
                }

                // Substitui operadores visuais por operadores JS
                // Usa Function para eval seguro
                const resultado = new Function(`return (${expr})`)();
                
                // Verifica se é um número válido
                if (isNaN(resultado) || !isFinite(resultado)) {
                    visorResultado.textContent = 'Erro';
                    return;
                }
                
                // Formata o resultado
                const resultadoFormatado = Number.isInteger(resultado) ? 
                    resultado.toString() : 
                    resultado.toFixed(8).replace(/\.?0+$/, '');
                
                visorResultado.textContent = `= ${resultadoFormatado}`;
            } catch (e) {
                visorResultado.textContent = 'Erro';
                console.log('Erro ao calcular:', e);
            }
        }

        // Permitir teclado físico também
        document.addEventListener('keydown', function(e) {
            const tecla = e.key;
            
            if (tecla >= '0' && tecla <= '9') {
                inserir(tecla);
                e.preventDefault();
            } else if (tecla === '.') {
                inserir('.');
                e.preventDefault();
            } else if (tecla === '+') {
                inserir('+');
                e.preventDefault();
            } else if (tecla === '-') {
                inserir('−');
                e.preventDefault();
            } else if (tecla === '*') {
                inserir('×');
                e.preventDefault();
            } else if (tecla === '/') {
                inserir('÷');
                e.preventDefault();
            } else if (tecla === '%') {
                inserirPorcentagem();
                e.preventDefault();
            } else if (tecla === 'Enter') {
                calcular();
                e.preventDefault();
            } else if (tecla === 'Backspace') {
                apagarUltimo();
                e.preventDefault();
            } else if (tecla === 'Escape') {
                limparVisor();
                e.preventDefault();
            } else if (tecla === '(' || tecla === ')') {
                inserir(tecla);
                e.preventDefault();
            }
        });
    </script>

</body>
</html>
