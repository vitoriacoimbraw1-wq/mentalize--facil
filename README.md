<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mentalize Fácil | Resumos Jurídicos</title>
    <link href="https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --azul-claro: #72CDEE; /* Cor da sua logo */
            --azul-escuro: #003366; /* Cor de autoridade/botões */
            --branco: #ffffff;
            --fundo-suave: #f0f7fa;
            --texto: #2c3e50;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Open Sans', sans-serif; }

        body { background-color: var(--fundo-suave); color: var(--texto); scroll-behavior: smooth; }

        /* HEADER ESTRATÉGICO */
        header {
            position: fixed; top: 0; width: 100%;
            background: var(--branco);
            padding: 10px 5%;
            display: flex; align-items: center;
            box-shadow: 0 2px 15px rgba(0,0,0,0.08);
            z-index: 1000;
        }
        .header-content { display: flex; align-items: center; gap: 15px; max-width: 1200px; margin: 0 auto; width: 100%; }
        header img { height: 50px; width: 50px; border-radius: 50%; }
        header h1 { font-size: 1.1rem; color: var(--azul-escuro); text-transform: uppercase; letter-spacing: 1px; }

        main { padding: 100px 5% 40px; max-width: 1200px; margin: 0 auto; }

        .semestre-secao { margin-bottom: 50px; }
        .titulo-secao { 
            font-size: 1.8rem; margin-bottom: 25px; 
            color: var(--azul-escuro); border-left: 6px solid var(--azul-claro);
            padding-left: 15px;
        }

        /* GRID RESPONSIVO (MOBILE-FIRST) */
        .grid-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
        }

        /* CARD DE ALTA CONVERSÃO */
        .card {
            background: var(--branco);
            border-radius: 18px;
            padding: 25px;
            box-shadow: 0 8px 25px rgba(0,0,0,0.05);
            transition: transform 0.2s ease;
            display: flex; flex-direction: column; justify-content: space-between;
        }
        .card:hover { transform: translateY(-5px); }

        .card h3 { font-size: 1.2rem; margin-bottom: 15px; color: var(--azul-escuro); height: 3.5rem; overflow: hidden; }

        /* SELETOR DIGITAL / IMPRESSO */
        .seletor { margin-bottom: 20px; }
        .radio-group { display: flex; gap: 10px; margin-top: 10px; }
        .radio-label {
            flex: 1; text-align: center; padding: 10px;
            border: 2px solid #edf2f7; border-radius: 10px;
            cursor: pointer; font-size: 0.9rem; font-weight: 600;
            transition: 0.2s;
        }
        input[type="radio"] { display: none; }
        input[type="radio"]:checked + .radio-label {
            border-color: var(--azul-claro); background: #eefbff; color: var(--azul-escuro);
        }

        .preco { font-size: 1.8rem; font-weight: 700; color: #27ae60; margin-bottom: 5px; }
        .pix-tag { font-size: 0.75rem; color: #7f8c8d; margin-bottom: 15px; display: block; }

        /* CTA AZUL ESCURO */
        .btn-comprar {
            background: var(--azul-escuro);
            color: var(--branco);
            text-decoration: none; text-align: center;
            padding: 15px; border-radius: 12px;
            font-weight: 700; text-transform: uppercase;
            transition: 0.3s; cursor: pointer; border: none;
        }
        .btn-comprar:hover { background: var(--azul-claro); color: var(--azul-escuro); transform: scale(1.02); }

        /* ESTILO EM PRODUÇÃO */
        .card-producao { opacity: 0.6; background: #fafafa; border: 1px dashed #cbd5e0; position: relative; }
        .tag-breve { 
            position: absolute; top: 15px; right: 15px; 
            background: #cbd5e0; padding: 4px 10px; border-radius: 20px; 
            font-size: 0.7rem; font-weight: 700; 
        }
        .msg-aguarde { font-style: italic; color: #718096; margin-top: 20px; text-align: center; font-weight: 600; }

        @media (max-width: 600px) {
            .grid-cards { grid-template-columns: 1fr; }
            header h1 { font-size: 0.9rem; }
        }
    </style>
</head>
<body>

<header>
    <div class="header-content">
        <img src="logo.png" alt="Logo Mentalize Fácil">
        <h1>Mentalize Fácil</h1>
    </div>
</header>

<main>
    <section class="semestre-secao">
        <h2 class="titulo-secao">1º Semestre</h2>
        <div class="grid-cards" id="grid-1"></div>
    </section>

    <section class="semestre-secao">
        <h2 class="titulo-secao">2º Semestre</h2>
        <div class="grid-cards" id="grid-2"></div>
    </section>

    <section class="semestre-secao">
        <h2 class="titulo-secao">3º Semestre (Em Produção)</h2>
        <div class="grid-cards" id="grid-3"></div>
    </section>
</main>

<script>
    const whatsappLink = "https://wa.me/5569992168120";

    const s1 = ["Ciência Política e Teoria Geral do Estado", "Criminologia", "História do Direito", "Psicologia Jurídica e Relações Interpessoais", "Teoria Geral do Direito"];
    const s2 = ["Direito Civil - Parte Geral", "Direito Constitucional (Teoria da Constituição e Direitos Fundamentais)", "Direito Criminal - Penal 1"];
    const s3 = ["Direito Civil - Obrigações e Responsabilidade Civil", "Direito Constitucional - Organização do Estado e seus Poderes", "Direito Criminal - Penal 2", "Direito Processual Civil - Parte Geral e Tutela", "Direitos Humanos, Diversidade e Inclusão"];

    function createCard(materia, gridId, isProduction = false) {
        const grid = document.getElementById(gridId);
        const id = materia.replace(/\s+/g, '-').toLowerCase();
        const card = document.createElement('div');
        card.className = isProduction ? 'card card-producao' : 'card';

        if(isProduction) {
            card.innerHTML = `<span class="tag-breve">EM BREVE</span><h3>${materia}</h3><p class="msg-aguarde">Material em Produção - Aguarde</p>`;
        } else {
            card.innerHTML = `
                <h3>${materia}</h3>
                <div class="seletor">
                    <div class="radio-group">
                        <input type="radio" name="fmt-${id}" id="dig-${id}" value="55" checked onchange="updatePrice('${id}', 55)">
                        <label class="radio-label" for="dig-${id}">Digital (PDF)</label>
                        <input type="radio" name="fmt-${id}" id="imp-${id}" value="65" onchange="updatePrice('${id}', 65)">
                        <label class="radio-label" for="imp-${id}">Impresso</label>
                    </div>
                </div>
                <div class="preco" id="price-${id}">R$ 55,00</div>
                <span class="pix-info">Pagamento via PIX</span>
                <button onclick="comprar('${materia}', '${id}')" class="btn-comprar">Comprar Agora</button>
            `;
        }
        grid.appendChild(card);
    }

    function updatePrice(id, valor) {
        document.getElementById(`price-${id}`).innerText = `R$ ${valor},00`;
    }

    function comprar(materia, id) {
        const preco = document.getElementById(`price-${id}`).innerText;
        const formato = document.querySelector(`input[name="fmt-${id}"]:checked`).nextElementSibling.innerText;
        const msg = encodeURIComponent(`Olá! Quero adquirir o resumo:\n📚 Matéria: ${materia}\n📄 Formato: ${formato}\n💰 Valor: ${preco}\n✅ Pagamento via PIX.`);
        window.location.href = `${whatsappLink}?text=${msg}`;
    }

    // Gerar Matérias
    s1.forEach(m => createCard(m, 'grid-1'));
    s2.forEach(m => createCard(m, 'grid-2'));
    s3.forEach(m => createCard(m, 'grid-3', true));
</script>

</body>
</html>
