<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mentalize Fácil - Resumos Jurídicos</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --azul-marca: #72CDEE; /* Azul claro do círculo da logo */
            --azul-fundo: #D9EEFB; /* Fundo suave da imagem do site */
            --azul-escuro: #0D47A1; /* Botões de conversão */
            --branco: #FFFFFF;
            --texto: #333333;
            --shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Inter', sans-serif; }

        body { background-color: var(--azul-fundo); color: var(--texto); line-height: 1.6; }

        /* 1. Identidade Visual & UI: Header Fixo */
        header {
            position: fixed;
            top: 0; width: 100%;
            background: var(--branco);
            padding: 10px 5%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
            z-index: 1000;
        }

        header .header-container {
            width: 100%; max-width: 1100px;
            display: flex; align-items: center; gap: 15px;
        }

        header img { height: 45px; border-radius: 50%; }
        header h1 { font-size: 1.2rem; color: var(--azul-escuro); font-weight: 700; }

        /* Estrutura de Catálogo */
        main { padding: 100px 5% 50px; max-width: 1100px; margin: 0 auto; }

        .section-title { 
            font-size: 1.8rem; margin: 40px 0 20px; 
            color: var(--texto); font-weight: 700; 
        }

        /* 5. Responsividade: Grid Mobile-first */
        .card-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
        }

        /* Funcionalidade dos Cards */
        .card {
            background: var(--branco);
            border-radius: 20px;
            padding: 25px;
            box-shadow: var(--shadow);
            transition: transform 0.3s ease;
            position: relative;
            display: flex; flex-direction: column;
        }

        .card:hover { transform: translateY(-5px); }

        .card h3 { font-size: 1.1rem; margin-bottom: 15px; min-height: 50px; color: var(--azul-escuro); }

        /* Seletor de Formato */
        .format-selector {
            display: flex; gap: 10px; margin-bottom: 20px;
        }

        .format-selector label {
            flex: 1; text-align: center;
            padding: 8px; border: 2px solid #f0f0f0;
            border-radius: 10px; cursor: pointer;
            font-size: 0.85rem; font-weight: 600;
            transition: 0.2s;
        }

        .format-selector input { display: none; }

        .format-selector input:checked + label {
            border-color: var(--azul-marca);
            background: #f0faff;
            color: var(--azul-escuro);
        }

        /* Preço e Pagamento */
        .price-tag { font-size: 1.5rem; font-weight: 700; margin-bottom: 5px; }
        .pix-info { font-size: 0.8rem; color: #666; margin-bottom: 15px; display: block; }

        /* Ação do Botão CTA */
        .btn-buy {
            background: var(--azul-escuro);
            color: var(--branco);
            text-decoration: none;
            text-align: center;
            padding: 12px;
            border-radius: 12px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: 0.3s;
        }

        .btn-buy:hover { background: #012d6a; box-shadow: 0 5px 15px rgba(13, 71, 161, 0.3); }

        /* 4. Seção em Produção */
        .card.in-production { opacity: 0.6; pointer-events: none; }
        .badge-soon {
            position: absolute; top: 15px; right: 15px;
            background: #eee; font-size: 0.7rem;
            padding: 4px 10px; border-radius: 20px; font-weight: 700;
        }
        .msg-production { color: #888; font-style: italic; font-size: 0.9rem; margin-top: 10px; }

        @media (max-width: 600px) {
            .section-title { font-size: 1.4rem; text-align: center; }
            header h1 { font-size: 1rem; }
        }
    </style>
</head>
<body>

<header>
    <div class="header-container">
        <img src="shaky-yellow-zogbps963c.edgeone.app" alt="Mentalize Fácil"> <h1>Mentalize Fácil - Resumos Jurídicos</h1>
    </div>
</header>

<main>
    <h2 class="section-title">1º Semestre</h2>
    <div class="card-grid" id="semestre1"></div>

    <h2 class="section-title">2º Semestre</h2>
    <div class="card-grid" id="semestre2"></div>

    <h2 class="section-title">3º Semestre (A caminho)</h2>
    <div class="card-grid" id="semestre3"></div>
</main>

<script>
    const whatsappBase = "https://wa.me/5569992168120";

    const materiasS1 = [
        "Ciência Política e Teoria Geral do Estado", "Criminologia", 
        "História do Direito", "Psychologia Jurídica e Relações Interpessoais", "Teoria Geral do Direito"
    ];

    const materiasS2 = [
        "Direito Civil - Parte Geral", 
        "Direito Constitucional (Teoria da Constituição e Direitos Fundamentais)", 
        "Direito Criminal - Penal 1"
    ];

    const materiasS3 = [
        "Direito Civil - Obrigações e Responsabilidade Civil",
        "Direito Constitucional - Organização do Estado e seus Poderes",
        "Direito Criminal - Penal 2",
        "Direito Processual Civil - Parte Geral e Tutela",
        "Direitos Humanos, Diversidade e Inclusão"
    ];

    function createCard(nome, containerId, isProduction = false) {
        const container = document.getElementById(containerId);
        const cardId = nome.replace(/\s+/g, '-').toLowerCase();

        const card = document.createElement('div');
        card.className = `card ${isProduction ? 'in-production' : ''}`;
        
        if (isProduction) {
            card.innerHTML = `
                <span class="badge-soon">EM BREVE</span>
                <h3>${nome}</h3>
                <p class="msg-production">Material em Produção - Aguarde</p>
            `;
        } else {
            card.innerHTML = `
                <h3>${nome}</h3>
                <div class="format-selector">
                    <input type="radio" name="fmt-${cardId}" id="dig-${cardId}" value="Digital" checked onchange="updatePrice('${cardId}', 55)">
                    <label for="dig-${cardId}">Digital (PDF)</label>
                    <input type="radio" name="fmt-${cardId}" id="imp-${cardId}" value="Impresso" onchange="updatePrice('${cardId}', 65)">
                    <label for="imp-${cardId}">Impresso</label>
                </div>
                <div class="price-tag" id="price-${cardId}">R$ 55,00</div>
                <span class="pix-info">Pagamento via PIX</span>
                <button onclick="buy('${nome}', '${cardId}')" class="btn-buy">Comprar Agora</button>
            `;
        }
        container.appendChild(card);
    }

    function updatePrice(id, price) {
        document.getElementById(`price-${id}`).innerText = `R$ ${price},00`;
    }

    function buy(materia, id) {
        const isImpresso = document.getElementById(`imp-${id}`).checked;
        const formato = isImpresso ? "Impresso" : "Digital (PDF)";
        const valor = isImpresso ? "R$ 65,00" : "R$ 55,00";
        const msg = encodeURIComponent(`Olá! Quero o resumo de: ${materia}\nFormato: ${formato}\nValor: ${valor}\nPagamento: PIX`);
        window.location.href = `${whatsappBase}?text=${msg}`;
    }

    // Inicializar Matérias
    materiasS1.forEach(m => createCard(m, 'semestre1'));
    materiasS2.forEach(m => createCard(m, 'semestre2'));
    materiasS3.forEach(m => createCard(m, 'semestre3', true));
</script>

</body>
</html>



