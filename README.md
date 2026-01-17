
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mentalize Fácil | Resumos Jurídicos</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap" rel="stylesheet">
    <style>
        /* --- VARIÁVEIS & RESET (Identidade Visual) --- */
        :root {
            --cor-primaria: #4FC3F7; /* Azul Claro - Marca */
            --cor-cta: #01579B;       /* Azul Escuro - Botões */
            --cor-cta-hover: #0277BD; /* Hover Vibrante */
            --cor-fundo: #F4F6F8;     /* Branco/Cinza limpo */
            --cor-texto: #333333;
            --cor-borda: #E0E0E0;
            --sombra-suave: 0 4px 6px -1px rgba(0,0,0,0.1);
            --sombra-hover: 0 10px 15px -3px rgba(0,0,0,0.1);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Roboto', sans-serif;
            background-color: var(--cor-fundo);
            color: var(--cor-texto);
            line-height: 1.6;
            padding-top: 80px; /* Espaço para o header fixo */
        }

        /* --- HEADER --- */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background-color: #FFFFFF;
            height: 70px;
            display: flex;
            align-items: center;
            padding: 0 5%;
            box-shadow: var(--sombra-suave);
            z-index: 1000;
        }

        header img {
            max-height: 40px;
            width: auto;
        }

        /* --- LAYOUT GERAL --- */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .section-title {
            font-size: 1.5rem;
            color: var(--cor-cta);
            border-bottom: 2px solid var(--cor-primaria);
            display: inline-block;
            margin: 40px 0 20px 0;
            padding-bottom: 5px;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-weight: 700;
        }

        /* --- GRID DE CARDS --- */
        .grid-cards {
            display: grid;
            grid-template-columns: 1fr; /* Mobile First: 1 coluna */
            gap: 20px;
        }

        /* Tablet e Desktop */
        @media (min-width: 768px) {
            .grid-cards {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (min-width: 1024px) {
            .grid-cards {
                grid-template-columns: repeat(3, 1fr);
            }
        }

        /* --- ESTILO DO CARD --- */
        .card {
            background: #FFFFFF;
            border-radius: 12px;
            padding: 25px;
            box-shadow: var(--sombra-suave);
            transition: transform 0.2s, box-shadow 0.2s;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            border: 1px solid transparent;
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: var(--sombra-hover);
            border-color: var(--cor-primaria);
        }

        .card h3 {
            font-size: 1.25rem;
            margin-bottom: 15px;
            color: var(--cor-cta);
            min-height: 3.5rem; /* Alinha alturas dos títulos */
        }

        /* --- SELETOR DE FORMATO (Radio Buttons) --- */
        .format-selector {
            margin-bottom: 20px;
            background: #F0F4F8;
            padding: 10px;
            border-radius: 8px;
        }

        .radio-option {
            display: flex;
            align-items: center;
            margin-bottom: 8px;
            cursor: pointer;
            font-size: 0.95rem;
        }

        .radio-option:last-child {
            margin-bottom: 0;
        }

        .radio-option input {
            margin-right: 10px;
            accent-color: var(--cor-cta); /* Cor do check nativo moderno */
            width: 18px;
            height: 18px;
        }

        /* --- PREÇO E CTA --- */
        .price-display {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--cor-texto);
            margin-bottom: 15px;
            text-align: center;
        }

        .btn-buy {
            background-color: var(--cor-cta);
            color: white;
            border: none;
            padding: 15px;
            border-radius: 8px;
            font-size: 1rem;
            font-weight: 700;
            cursor: pointer;
            width: 100%;
            transition: background 0.3s;
            text-transform: uppercase;
        }

        .btn-buy:hover {
            background-color: var(--cor-cta-hover);
        }

        /* --- ESTILO "EM PRODUÇÃO" (3º Semestre) --- */
        .production-card {
            opacity: 0.8;
            background-color: #FAFAFA;
            border: 1px dashed #CCC;
        }

        .production-card h3 {
            color: #777;
        }

        .status-badge {
            display: block;
            background-color: #EEE;
            color: #666;
            text-align: center;
            padding: 10px;
            border-radius: 6px;
            font-weight: 500;
            margin-top: auto; /* Empurra para o fundo do card */
            font-size: 0.9rem;
        }

    </style>
</head>
<body>

    <header>
        <div class="logo-area">
            <img src="logo.png" alt="Mentalize Fácil">
        </div>
    </header>

    <main class="container">

        <h2 class="section-title">1º Semestre</h2>
        <div class="grid-cards" id="semestre-1">
            <div class="card product-card" data-id="cp-tge">
                <h3>Ciência Política e Teoria Geral do Estado</h3>
                <div class="format-selector">
                    <label class="radio-option">
                        <input type="radio" name="format-cp-tge" value="digital" checked onchange="updatePrice(this)">
                        Digital (PDF)
                    </label>
                    <label class="radio-option">
                        <input type="radio" name="format-cp-tge" value="impresso" onchange="updatePrice(this)">
                        Impresso
                    </label>
                </div>
                <div class="price-display">R$ 55,00</div>
                <button class="btn-buy">Comprar Agora</button>
            </div>

            <div class="card product-card" data-id="criminologia">
                <h3>Criminologia</h3>
                <div class="format-selector">
                    <label class="radio-option">
                        <input type="radio" name="format-crim" value="digital" checked onchange="updatePrice(this)">
                        Digital (PDF)
                    </label>
                    <label class="radio-option">
                        <input type="radio" name="format-crim" value="impresso" onchange="updatePrice(this)">
                        Impresso
                    </label>
                </div>
                <div class="price-display">R$ 55,00</div>
                <button class="btn-buy">Comprar Agora</button>
            </div>

            <div class="card product-card" data-id="hist-direito">
                <h3>História do Direito</h3>
                <div class="format-selector">
                    <label class="radio-option">
                        <input type="radio" name="format-hist" value="digital" checked onchange="updatePrice(this)">
                        Digital (PDF)
                    </label>
                    <label class="radio-option">
                        <input type="radio" name="format-hist" value="impresso" onchange="updatePrice(this)">
                        Impresso
                    </label>
                </div>
                <div class="price-display">R$ 55,00</div>
                <button class="btn-buy">Comprar Agora</button>
            </div>

            <div class="card product-card" data-id="psico-jur">
                <h3>Psicologia Jurídica e Relações Interpessoais</h3>
                <div class="format-selector">
                    <label class="radio-option">
                        <input type="radio" name="format-psico" value="digital" checked onchange="updatePrice(this)">
                        Digital (PDF)
                    </label>
                    <label class="radio-option">
                        <input type="radio" name="format-psico" value="impresso" onchange="updatePrice(this)">
                        Impresso
                    </label>
                </div>
                <div class="price-display">R$ 55,00</div>
                <button class="btn-buy">Comprar Agora</button>
            </div>

            <div class="card product-card" data-id="tgd">
                <h3>Teoria Geral do Direito</h3>
                <div class="format-selector">
                    <label class="radio-option">
                        <input type="radio" name="format-tgd" value="digital" checked onchange="updatePrice(this)">
                        Digital (PDF)
                    </label>
                    <label class="radio-option">
                        <input type="radio" name="format-tgd" value="impresso" onchange="updatePrice(this)">
                        Impresso
                    </label>
                </div>
                <div class="price-display">R$ 55,00</div>
                <button class="btn-buy">Comprar Agora</button>
            </div>
        </div>

        <h2 class="section-title">2º Semestre</h2>
        <div class="grid-cards" id="semestre-2">
            
            <div class="card product-card" data-id="civ-geral">
                <h3>Direito Civil - Parte Geral</h3>
                <div class="format-selector">
                    <label class="radio-option">
                        <input type="radio" name="format-civg" value="digital" checked onchange="updatePrice(this)">
                        Digital (PDF)
                    </label>
                    <label class="radio-option">
                        <input type="radio" name="format-civg" value="impresso" onchange="updatePrice(this)">
                        Impresso
                    </label>
                </div>
                <div class="price-display">R$ 55,00</div>
                <button class="btn-buy">Comprar Agora</button>
            </div>

            <div class="card product-card" data-id="const-teoria">
                <h3>Direito Constitucional (Teoria e Fundamentais)</h3>
                <div class="format-selector">
                    <label class="radio-option">
                        <input type="radio" name="format-const" value="digital" checked onchange="updatePrice(this)">
                        Digital (PDF)
                    </label>
                    <label class="radio-option">
                        <input type="radio" name="format-const" value="impresso" onchange="updatePrice(this)">
                        Impresso
                    </label>
                </div>
                <div class="price-display">R$ 55,00</div>
                <button class="btn-buy">Comprar Agora</button>
            </div>

            <div class="card product-card" data-id="penal-1">
                <h3>Direito Criminal - Penal 1</h3>
                <div class="format-selector">
                    <label class="radio-option">
                        <input type="radio" name="format-penal1" value="digital" checked onchange="updatePrice(this)">
                        Digital (PDF)
                    </label>
                    <label class="radio-option">
                        <input type="radio" name="format-penal1" value="impresso" onchange="updatePrice(this)">
                        Impresso
                    </label>
                </div>
                <div class="price-display">R$ 55,00</div>
                <button class="btn-buy">Comprar Agora</button>
            </div>
        </div>

        <h2 class="section-title">3º Semestre <span style="font-size: 0.8rem; color: #777; font-weight: 400; margin-left: 10px;">(Em Breve)</span></h2>
        <div class="grid-cards" id="semestre-3">
            
            <div class="card production-card">
                <h3>Direito Civil - Obrigações e Resp. Civil</h3>
                <div class="status-badge">Material em Produção - Aguarde</div>
            </div>

            <div class="card production-card">
                <h3>Direito Constitucional - Org. do Estado e Poderes</h3>
                <div class="status-badge">Material em Produção - Aguarde</div>
            </div>

            <div class="card production-card">
                <h3>Direito Criminal - Penal 2</h3>
                <div class="status-badge">Material em Produção - Aguarde</div>
            </div>

            <div class="card production-card">
                <h3>Direito Processual Civil - Parte Geral e Tutela</h3>
                <div class="status-badge">Material em Produção - Aguarde</div>
            </div>

            <div class="card production-card">
                <h3>Direitos Humanos, Diversidade e Inclusão</h3>
                <div class="status-badge">Material em Produção - Aguarde</div>
            </div>

        </div>

        <br><br><br> </main>

    <script>
        /**
         * Atualiza o preço baseado na seleção do Radio Button.
         * Esta função é chamada diretamente pelo evento 'onchange' no HTML.
         */
        function updatePrice(radioInput) {
            // 1. Encontra o card pai do input selecionado
            const card = radioInput.closest('.card');
            
            // 2. Encontra o elemento de display de preço dentro desse card
            const priceDisplay = card.querySelector('.price-display');
            
            // 3. Define os preços
            const priceDigital = "R$ 55,00";
            const pricePrinted = "R$ 65,00";

            // 4. Lógica de atualização com feedback visual suave
            if (radioInput.value === 'digital') {
                priceDisplay.style.opacity = 0; // Fade out rápido
                setTimeout(() => {
                    priceDisplay.textContent = priceDigital;
                    priceDisplay.style.opacity = 1; // Fade in
                }, 150);
            } else if (radioInput.value === 'impresso') {
                priceDisplay.style.opacity = 0;
                setTimeout(() => {
                    priceDisplay.textContent = pricePrinted;
                    priceDisplay.style.opacity = 1;
                }, 150);
            }
        }
    </script>
</body>
</html>
