<DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mentalize Fácil | Resumos Jurídicos</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --azul-marca: #007BFF;
            --azul-escuro: #003366;
            --branco: #FFFFFF;
            --texto: #1A1A1A;
            --cinza-sub: #636E72;
            --sombra: 0 10px 30px rgba(0,0,0,0.05);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Inter', sans-serif; }
        body { background-color: #FDFDFD; color: var(--texto); overflow-x: hidden; }

        /* HEADER FIXO - REGRA DO MILÉSIMO ZERO */
        header {
            position: fixed; top: 0; width: 100%; height: 70px;
            background: var(--branco); display: flex; align-items: center;
            justify-content: center; box-shadow: 0 2px 10px rgba(0,0,0,0.05); z-index: 1000;
        }
        header img { height: 40px; }

        main { max-width: 1200px; margin: 100px auto 50px; padding: 0 20px; }

        .section-header {
            font-size: 1.4rem; font-weight: 800; color: var(--azul-escuro);
            margin: 40px 0 20px; border-left: 6px solid var(--azul-marca);
            padding-left: 15px; text-transform: uppercase; letter-spacing: -0.5px;
        }

        .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(340px, 1fr)); gap: 30px; }

        /* CARD STYLE - UI/UX SENIOR */
        .card {
            background: var(--branco); border: 1px solid #EEE; border-radius: 16px;
            padding: 28px; display: flex; flex-direction: column;
            transition: transform 0.3s ease; position: relative; box-shadow: var(--sombra);
        }
        .card:hover { transform: translateY(-8px); }

        .card h3 { color: var(--azul-escuro); font-size: 1.25rem; margin-bottom: 15px; line-height: 1.2; min-height: 3rem; }
        
        /* SUBTÓPICOS - PRESERVAÇÃO INTEGRAL DA INFORMAÇÃO */
        .content { font-size: 0.9rem; color: var(--cinza-sub); margin-bottom: 25px; flex-grow: 1; line-height: 1.5; }
        .content b { color: var(--azul-marca); }

        /* SELETOR DE PREÇO - LÓGICA DE VENDA DIRETA */
        .pricing-box { background: #F8FAFC; padding: 15px; border-radius: 12px; margin-top: auto; }
        .options { display: flex; justify-content: space-between; margin-bottom: 12px; }
        .opt { display: flex; align-items: center; gap: 6px; font-weight: 700; font-size: 0.85rem; cursor: pointer; }

        .price-tag { font-size: 1.8rem; font-weight: 800; color: var(--azul-escuro); text-align: center; display: block; }
        .pix-alert { font-size: 0.75rem; color: #27AE60; font-weight: 800; text-align: center; display: block; margin-bottom: 15px; text-transform: uppercase; }

        /* BOTÃO COMPRAR - ALTO CONTRASTE */
        .btn-buy {
            background: var(--azul-escuro); color: var(--branco); text-align: center;
            padding: 18px; border-radius: 10px; text-decoration: none;
            font-weight: 800; border: none; width: 100%; cursor: pointer;
            transition: 0.2s; font-size: 1rem; text-transform: uppercase;
        }
        .btn-buy:hover { background: var(--azul-marca); }

        /* STATUS: EM PRODUÇÃO */
        .locked { opacity: 0.5; filter: grayscale(1); pointer-events: none; }
        .badge {
            position: absolute; top: 15px; right: 15px; background: #DFE6E9;
            color: #636E72; padding: 5px 12px; border-radius: 50px; font-size: 0.7rem; font-weight: 800;
        }

        @media (max-width: 600px) { .grid { grid-template-columns: 1fr; } }
    </style>
</head>
<body>

    <header>
        <img src="logo.png" alt="Mentalize Fácil">
    </header>

    <main>
        <h2 class="section-header">SEÇÃO 1º SEMESTRE</h2>
        <div class="grid">
            <div class="card">
                <h3>Ciência Política e Teoria Geral do Estado</h3>
                <div class="content">
                    <b>Parte 1:</b> Temática central, objeto de estudo - Paulo Bonavides, O que é Sociedade?, Estado vs Nação, População vs povo, Formas de governo, sistema de governo. <br>
                    <b>Parte 2:</b> Sufrágio, Voto, Sistema Eleitorais, Partidos Políticos.
                </div>
                <div class="pricing-box" data-item="Ciência Política">
                    <div class="options">
                        <label class="opt"><input type="radio" name="cp" value="55" checked onchange="v(this)"> Digital (PDF)</label>
                        <label class="opt"><input type="radio" name="cp" value="65" onchange="v(this)"> Impresso</label>
                    </div>
                    <span class="price-tag">R$ 55,00</span>
                    <span class="pix-alert">Pagamento via PIX</span>
                    <button class="btn-buy" onclick="buy(this)">COMPRAR AGORA</button>
                </div>
            </div>

            <div class="card">
                <h3>Criminologia</h3>
                <div class="content">
                    <b>SUBTÓPICOS:</b> Teoria do consenso, Teoria do conflito, Teoria da subcultura delinquente, Anomia, Direito penal mínimo e pena, modos de adaptação, vitimologia e classificação.
                </div>
                <div class="pricing-box" data-item="Criminologia">
                    <div class="options">
                        <label class="opt"><input type="radio" name="cr" value="55" checked onchange="v(this)"> Digital (PDF)</label>
                        <label class="opt"><input type="radio" name="cr" value="65" onchange="v(this)"> Impresso</label>
                    </div>
                    <span class="price-tag">R$ 55,00</span>
                    <span class="pix-alert">Pagamento via PIX</span>
                    <button class="btn-buy" onclick="buy(this)">COMPRAR AGORA</button>
                </div>
            </div>

            <div class="card">
                <h3>História do Direito</h3>
                <div class="content">
                    <b>SUBTÓPICOS:</b> O direito na Antiguidade, Código de Hamurabi, Direito Hebreu e Legislação, Direito Grego, Direito na Idade média, Direito Canônico, Revalorização da escrita, O feudalismo e Magna Carta, Contexto geral na Idade Moderna, Reforma protestante (século XVI), renascimento (Século XIV a VXI), Iluminismo (Século XVIII), Césare Beccaria e a Reforma do direito penal, constituições.
                </div>
                <div class="pricing-box" data-item="História do Direito">
                    <div class="options">
                        <label class="opt"><input type="radio" name="hd" value="55" checked onchange="v(this)"> Digital (PDF)</label>
                        <label class="opt"><input type="radio" name="hd" value="65" onchange="v(this)"> Impresso</label>
                    </div>
                    <span class="price-tag">R$ 55,00</span>
                    <span class="pix-alert">Pagamento via PIX</span>
                    <button class="btn-buy" onclick="buy(this)">COMPRAR AGORA</button>
                </div>
            </div>

            <div class="card">
                <h3>Psicologia Jurídica e Relações Interpessoais</h3>
                <div class="content">
                    <b>SUBTÓPICOS:</b> Mediação Familiar, Resolução de Conflitos, Crianças e adolescentes, Alineação Parental, raízes da violência, Violência de Gênero, Relações Humanas/Interpessoais.
                </div>
                <div class="pricing-box" data-item="Psicologia Jurídica">
                    <div class="options">
                        <label class="opt"><input type="radio" name="pj" value="55" checked onchange="v(this)"> Digital (PDF)</label>
                        <label class="opt"><input type="radio" name="pj" value="65" onchange="v(this)"> Impresso</label>
                    </div>
                    <span class="price-tag">R$ 55,00</span>
                    <span class="pix-alert">Pagamento via PIX</span>
                    <button class="btn-buy" onclick="buy(this)">COMPRAR AGORA</button>
                </div>
            </div>

            <div class="card">
                <h3>Teoria Geral do Direito</h3>
                <div class="content">
                    <b>Parte 1:</b> Objetividade e Subjetividade, tipos e fontes do conhecimento, Zetética e dogmática, Escolas do direito, Subjetividade Potestativa, Hermeneutica Juritica, Fontes do Direito. <br>
                    <b>Parte 2:</b> Teoria da Norma Jurídica, HIerarquia das Normas, Sanções ou Punições, Teoria do Ordenamento Jurítico, questão temporal, Direito Neoconstitucionalismo, Direitos Humanos.
                </div>
                <div class="pricing-box" data-item="Teoria Geral do Direito">
                    <div class="options">
                        <label class="opt"><input type="radio" name="tgd" value="55" checked onchange="v(this)"> Digital (PDF)</label>
                        <label class="opt"><input type="radio" name="tgd" value="65" onchange="v(this)"> Impresso</label>
                    </div>
                    <span class="price-tag">R$ 55,00</span>
                    <span class="pix-alert">Pagamento via PIX</span>
                    <button class="btn-buy" onclick="buy(this)">COMPRAR AGORA</button>
                </div>
            </div>
        </div>

        <h2 class="section-header">SEÇÃO 2º SEMESTRE</h2>
        <div class="grid">
            <div class="card">
                <h3>Direito Civil - Parte Geral</h3>
                <div class="content">
                    <b>Subtópicos:</b> Conceitos de direito Civil, Código Civil de 2002, Princípios Básicos, Das pessoas Naturais, Capacidade Jurídica e Legitimação, Sujeitos da Relação Jurídica, Teorias, Das incapacidades, Cessação da incapacidade, Da Ausência, Dos bens, Classificação dos bens, Fatos Jurídico, Negócio Jurídico.
                </div>
                <div class="pricing-box" data-item="Direito Civil (Geral)">
                    <div class="options">
                        <label class="opt"><input type="radio" name="dc" value="55" checked onchange="v(this)"> Digital (PDF)</label>
                        <label class="opt"><input type="radio" name="dc" value="65" onchange="v(this)"> Impresso</label>
                    </div>
                    <span class="price-tag">R$ 55,00</span>
                    <span class="pix-alert">Pagamento via PIX</span>
                    <button class="btn-buy" onclick="buy(this)">COMPRAR AGORA</button>
                </div>
            </div>

            <div class="card">
                <h3>Direito Constitucional</h3>
                <div class="content">
                    <b>Subtópicos:</b> Direito Publico e privado, Conceito do direito Constitucional, Limitação do poder do Estado, Conceito da Constituição, Concepções da constituição, Classificação da Constituição, O que é Constitucionalismo, desdobramentos, Neocontitucionalismo, Jusnaturalismo, Positivismo, Poder constituinte, Aplicabilidade das normas constitucionais, Bloco de Constitucionalidade, Métodos de Interpretação Constitucional.
                </div>
                <div class="pricing-box" data-item="Direito Constitucional">
                    <div class="options">
                        <label class="opt"><input type="radio" name="dcon" value="55" checked onchange="v(this)"> Digital (PDF)</label>
                        <label class="opt"><input type="radio" name="dcon" value="65" onchange="v(this)"> Impresso</label>
                    </div>
                    <span class="price-tag">R$ 55,00</span>
                    <span class="pix-alert">Pagamento via PIX</span>
                    <button class="btn-buy" onclick="buy(this)">COMPRAR AGORA</button>
                </div>
            </div>

            <div class="card">
                <h3>Direito Criminal - Penal 1</h3>
                <div class="content">
                    <b>Subtópico:</b> Introdução e principios fundamentais, Divisões do Direito Penal, Fases Históricas da Pena, Período Humanitário, Escola Penais, Fundamentos Constitucionais do Direito Penal, Direito pena Moderno, Princípios limitadores do poder punitívo, Conceito e função da norma penal, Normas penais inconpletas ou imperfeitas, fontes do direito penal, tipos de norma penais, interpretação da lei, Lei penal no tempo, Lei penal no espaço.
                </div>
                <div class="pricing-box" data-item="Direito Criminal (Penal 1)">
                    <div class="options">
                        <label class="opt"><input type="radio" name="dp" value="55" checked onchange="v(this)"> Digital (PDF)</label>
                        <label class="opt"><input type="radio" name="dp" value="65" onchange="v(this)"> Impresso</label>
                    </div>
                    <span class="price-tag">R$ 55,00</span>
                    <span class="pix-alert">Pagamento via PIX</span>
                    <button class="btn-buy" onclick="buy(this)">COMPRAR AGORA</button>
                </div>
            </div>
        </div>

        <h2 class="section-header">SEÇÃO 3º SEMESTRE (EM PRODUÇÃO)</h2>
        <div class="grid">
            <div class="card locked">
                <span class="badge">Em Breve</span>
                <h3>Direito Civil - Obrigações e Responsabilidade Civil</h3>
                <p class="content">Material em Produção - Aguarde</p>
            </div>
            <div class="card locked">
                <span class="badge">Em Breve</span>
                <h3>Direito Constitucional - Organização do Estado</h3>
                <p class="content">Material em Produção - Aguarde</p>
            </div>
            <div class="card locked">
                <span class="badge">Em Breve</span>
                <h3>Direito Criminal - Penal 2</h3>
                <p class="content">Material em Produção - Aguarde</p>
            </div>
            <div class="card locked">
                <span class="badge">Em Breve</span>
                <h3>Processual Civil - Parte Geral e Tutela</h3>
                <p class="content">Material em Produção - Aguarde</p>
            </div>
            <div class="card locked">
                <span class="badge">Em Breve</span>
                <h3>Direitos Humanos, Diversidade e Inclusão</h3>
                <p class="content">Material em Produção - Aguarde</p>
            </div>
        </div>
    </main>

    <script>
        // Função para atualizar preço (Curto e Direto)
        function v(el) {
            const p = el.closest('.pricing-box').querySelector('.price-tag');
            p.innerText = `R$ ${el.value},00`;
        }

        // Função de Venda via WhatsApp (Estratégia de Conversão)
        function buy(btn) {
            const box = btn.closest('.pricing-box');
            const mat = box.getAttribute('data-item');
            const form = box.querySelector('input:checked').parentElement.innerText.trim();
            const val = box.querySelector('.price-tag').innerText;
            
            const fone = "5569992168120"; // Seu número
            const texto = encodeURIComponent(`Olá! Quero o resumo de *${mat}* no formato *${form}* (${val}). Como faço o PIX?`);
            window.location.href = `https://wa.me/${fone}?text=${texto}`;
        }
    </script>
</body>
</html>
