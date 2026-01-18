<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mentalize Fácil | Resumos Jurídicos</title>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;600;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-blue: #72CDEE; /* Azul da Marca */
            --dark-blue: #0A4275;    /* Azul Profissional */
            --bg-light: #E3F2FD;     /* Fundo suave (Premium) */
            --white: #ffffff;
            --text-main: #1A202C;
            --shadow-soft: 0 20px 40px rgba(0, 0, 0, 0.06);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Plus Jakarta Sans', sans-serif; }

        body { 
            background-color: var(--bg-light); 
            color: var(--text-main); 
            padding-bottom: 50px;
        }

        /* HEADER ESTILO PÍLULA COM ÍCONE SVG */
        .header-wrapper {
            padding: 30px 5% 10px;
            display: flex;
            justify-content: center;
        }

        header {
            background: var(--white);
            padding: 12px 30px;
            border-radius: 100px;
            display: flex;
            align-items: center;
            gap: 15px;
            box-shadow: var(--shadow-soft);
            max-width: 700px;
            width: 100%;
        }

        /* Ícone de Cérebro/Lâmpada em SVG para substituir a logo física */
        .logo-icon {
            background: var(--primary-blue);
            width: 45px;
            height: 45px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
        }

        header h1 { font-size: 1.2rem; font-weight: 800; color: var(--dark-blue); letter-spacing: -0.5px; }

        /* SEÇÕES */
        main { max-width: 1100px; margin: 0 auto; padding: 20px; }
        
        .section-header {
            margin: 40px 0 20px;
            font-size: 1.4rem;
            font-weight: 800;
            color: var(--dark-blue);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        /* GRID DE CARDS SOFT UI */
        .card-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 25px;
        }

        .card {
            background: var(--white);
            border-radius: 25px;
            padding: 30px;
            box-shadow: var(--shadow-soft);
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            border: 1px solid rgba(255,255,255,0.7);
            display: flex;
            flex-direction: column;
        }

        .card:hover { transform: translateY(-10px); box-shadow: 0 35px 70px rgba(0, 0, 0, 0.08); }

        .card h3 { font-size: 1.1rem; font-weight: 700; color: var(--dark-blue); margin-bottom: 20px; min-height: 50px; line-height: 1.4; }

        /* SELETOR PREMIUM */
        .selector {
            display: flex;
            background: #F7FAFC;
            padding: 5px;
            border-radius: 15px;
            margin-bottom: 20px;
        }

        .selector label {
            flex: 1;
            text-align: center;
            padding: 10px;
            font-size: 0.8rem;
            font-weight: 700;
            cursor: pointer;
            border-radius: 11px;
            transition: 0.2s;
        }

        .selector input { display: none; }
        .selector input:checked + label {
            background: var(--white);
            color: var(--dark-blue);
            box-shadow: 0 4px 12px rgba(0,0,0,0.06);
        }

        /* PREÇO E CTA */
        .price-container { margin-bottom: 20px; }
        .price { font-size: 1.8rem; font-weight: 800; color: var(--dark-blue); }
        .pix-tag { font-size: 0.7rem; color: #718096; font-weight: 700; margin-top: 4px; display: block; text-transform: uppercase; }

        .btn-buy {
            background: var(--dark-blue);
            color: var(--white);
            text-align: center;
            padding: 18px;
            border-radius: 18px;
            text-decoration: none;
            font-weight: 800;
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: 0.3s;
            border: none;
            cursor: pointer;
        }

        .btn-buy:hover { background: var(--primary-blue); transform: scale(1.02); }

        /* ESTILO EM BREVE */
        .card.soon {
            background: rgba(255, 255, 255, 0.5);
            backdrop-filter: blur(8px);
            opacity: 0.7;
        }

        .badge {
            background: var(--primary-blue);
            color: var(--white);
            font-size: 0.6rem;
            padding: 4px 12px;
            border-radius: 50px;
            font-weight: 800;
            align-self: flex-start;
            margin-bottom: 15px;
        }

        /* RESPONSIVIDADE */
        @media (max-width: 600px) {
            header { padding: 10px 20px; }
            header h1 { font-size: 1rem; }
            .card-grid { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>

<div class="header-wrapper">
    <header>
        <div class="logo-icon">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M9.5 20a2.5 2.5 0 0 1 5 0"/><path d="M12 15V3"/><path d="M8 11a4 4 0 0 1 8 0"/></svg>
        </div>
        <h1>Mentalize Fácil - Resumos</h1>
    </header>
</div>

<main>
    <div class="section-header">1º Semestre</div>
    <div class="card-grid" id="s1"></div>

    <div class="section-header">2º Semestre</div>
    <div class="card-grid" id="s2"></div>

    <div class="section-header">3º Semestre (Em Produção)</div>
    <div class="card-grid" id="s3"></div>
</main>

<script>
    const wa = "https://wa.me/5569992168120";

    const data = {
        s1: ["Ciência Política e Teoria Geral do Estado", "Criminologia", "História do Direito", "Psicologia Jurídica e Relações Interpessoais", "Teoria Geral do Direito"],
        s2: ["Direito Civil - Parte Geral", "Direito Constitucional", "Direito Criminal - Penal 1"],
        s3: ["Direito Civil - Obrigações", "Direito Constitucional - Poderes", "Direito Criminal - Penal 2", "Direito Processual Civil", "Direitos Humanos"]
    };

    function render() {
        // Semestres ativos
        ['s1', 's2'].forEach(sem => {
            const container = document.getElementById(sem);
            data[sem].forEach((mat, i) => {
                const id = `${sem}-${i}`;
                container.innerHTML += `
                    <div class="card">
                        <h3>${mat}</h3>
                        <div class="selector">
                            <input type="radio" name="f-${id}" id="d-${id}" checked onchange="up('${id}', 55)">
                            <label for="d-${id}">Digital (PDF)</label>
                            <input type="radio" name="f-${id}" id="i-${id}" onchange="up('${id}', 65)">
                            <label for="i-${id}">Impresso</label>
                        </div>
                        <div class="price-container">
                            <span class="price" id="p-${id}">R$ 55,00</span>
                            <span class="pix-tag">✓ Pagamento via PIX</span>
                        </div>
                        <button class="btn-buy" onclick="buy('${mat}', '${id}')">COMPRAR AGORA</button>
                    </div>
                `;
            });
        });

        // Semestre em produção
        const s3 = document.getElementById('s3');
        data.s3.forEach(mat => {
            s3.innerHTML += `
                <div class="card soon">
                    <span class="badge">BREVE</span>
                    <h3>${mat}</h3>
                    <p style="color: #718096; font-weight: 700; font-size: 0.85rem;">Em fase de finalização...</p>
                </div>
            `;
        });
    }

    function up(id, v) { document.getElementById(`p-${id}`).innerText = `R$ ${v},00`; }

    function buy(m, id) {
        const p = document.getElementById(`p-${id}`).innerText;
        const f = document.querySelector(`input[name="f-${id}"]:checked`).nextElementSibling.innerText;
        const txt = encodeURIComponent(`Olá! Quero o resumo de:\n📚 *${m}*\n📄 Formato: ${f}\n💰 Valor: ${p}\n\nFavor enviar a chave PIX.`);
        window.location.href = `${wa}?text=${txt}`;
    }

    render();
</script>

</body>
</html>
