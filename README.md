<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mentalize Fácil | Resumos Jurídicos de Alta Retenção</title>
    <style>
        /* DESIGN SYSTEM & VARIABLES */
        :root {
            --azul-marca: #007BFF;
            --azul-escuro: #003366;
            --branco: #FFFFFF;
            --cinza-claro: #F8F9FA;
            --texto: #2D3436;
            --suave-sombra: 0 4px 12px rgba(0,0,0,0.08);
            --transicao: all 0.3s ease;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Inter', -apple-system, sans-serif; }

        body { background-color: var(--branco); color: var(--texto); line-height: 1.6; }

        /* HEADER */
        header {
            position: fixed; top: 0; width: 100%; height: 70px;
            background: var(--branco); display: flex; align-items: center;
            justify-content: center; box-shadow: var(--suave-sombra); z-index: 1000;
        }
        header img { height: 45px; }

        /* LAYOUT */
        main { max-width: 1100px; margin: 100px auto 40px; padding: 0 20px; }
        
        .section-title { 
            font-size: 1.5rem; color: var(--azul-escuro); 
            margin: 40px 0 20px; border-left: 5px solid var(--azul-marca); padding-left: 15px;
            text-transform: uppercase; letter-spacing: 1px;
        }

        .grid-cards { 
            display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); 
            gap: 25px; 
        }

        /* CARDS */
        .card {
            background: var(--branco); border: 1px solid #E1E8ED; border-radius: 12px;
            padding: 25px; display: flex; flex-direction: column;
            transition: var(--transicao); position: relative;
        }
        .card:hover { transform: translateY(-5px); box-shadow: var(--suave-sombra); }

        .card h3 { color: var(--azul-escuro); font-size: 1.2rem; margin-bottom: 15px; min-height: 3rem;}
        
        .subtopicos { font-size: 0.85rem; color: #636E72; margin-bottom: 20px; flex-grow: 1; }
        .subtopicos b { color: var(--azul-marca); }

        /* SELETOR DE PREÇO */
        .price-selector {
            background: var(--cinza-claro); padding: 10px; border-radius: 8px; margin-bottom: 15px;
            display: flex; justify-content: space-around;
        }
        .option { display: flex; align-items: center; gap: 8px; cursor: pointer; font-weight: 600; font-size: 0.9rem;}

        .price-display { 
            font-size: 1.4rem; font-weight: 800; color: var(--azul-escuro); 
            text-align: center; margin-bottom: 5px;
        }
        .pix-tag { 
            display: block; text-align: center; font-size: 0.75rem; 
            color: #00B894; font-weight: bold; margin-bottom: 15px;
        }

        /* BOTÃO COMPRAR */
        .btn-comprar {
            background: var(--azul-escuro); color: var(--branco); text-align: center;
            padding: 14px; border-radius: 8px; text-decoration: none;
            font-weight: bold; transition: var(--transicao); border: none; width: 100%;
            cursor: pointer; font-size: 1rem;
        }
        .btn-comprar:hover { background: var(--azul-marca); }

        /* ESTADO EM PRODUÇÃO */
        .em-producao { opacity: 0.6; pointer-events: none; filter: grayscale(0.5); }
        .badge-breve {
            position: absolute; top: 10px; right: 10px; background: #B2BEC3;
            color: white; padding: 4px 10px; border-radius: 20px; font-size: 0.7rem; font-weight: bold;
        }

        @media (max-width: 600px) { .grid-cards { grid-template-columns: 1fr; } }
    </style>
</head>
<body>

    <header>
        <img src="logo.png" alt="Mentalize Fácil">
    </header>

    <main>
        <h2 class="section-title">1º Semestre</h2>
        <div class="grid-cards">
            
            <article class="card">
                <h3>Ciência Política e Teoria Geral do Estado</h3>
                <div class="subtopicos">
                    <b>Parte 1:</b> Temática central, objeto de estudo - Paulo Bonavides, O que é Sociedade?, Estado vs Nação, População vs povo, Formas de governo, sistema de governo. <br>
                    <b>Parte 2:</b> Sufrágio, Voto, Sistema Eleitorais, Partidos Políticos.
                </div>
                <div class="price-container" data-materia="Ciência Política">
                    <div class="price-selector">
                        <label class="option"><input type="radio" name="cp" value="55" checked onclick="updatePrice(this)"> Digital (PDF)</label>
                        <label class="option"><input type="radio" name="cp" value="65" onclick="updatePrice(this)"> Impresso</label>
                    </div>
                    <div class="price-display">R$ 55,00</div>
                    <span class="pix-tag">Pagamento via PIX</span>
                    <button class="btn-comprar" onclick="checkout(this)">COMPRAR AGORA</button>
                </div>
            </article>

            <article class="card">
                <h3>Criminologia</h3>
                <div class="subtopicos">
                    Teoria do consenso, Teoria do conflito, Teoria da subcultura delinquente, Anomia, Direito penal mínimo e pena, modos de adaptação, vitimologia e classificação.
                </div>
                <div class="price-container" data-materia="Criminologia">
                    <div class="price-selector">
                        <label class="option"><input type="radio" name="crim" value="55" checked onclick="updatePrice(this)"> Digital (PDF)</label>
                        <label class="option"><input type="radio" name="crim" value="65" onclick="updatePrice(this)"> Impresso</label>
                    </div>
                    <div class="price-display">R$ 55,00</div>
                    <span class="pix-tag">Pagamento via PIX</span>
                    <button class="btn-comprar" onclick="checkout(this)">COMPRAR AGORA</button>
                </div>
            </article>

            <article class="card">
                <h3>História do Direito</h3>
                <div class="subtopicos">
                    O direito na Antiguidade, Código de Hamurabi, Direito Hebreu e Legislação, Direito Grego, Direito na Idade média, Direito Canônico, Revalorização da escrita, O feudalismo e Magna Carta, Contexto geral na Idade Moderna, Reforma protestante (século XVI), renascimento (Século XIV a VXI), Iluminismo (Século XVIII), Césare Beccaria e a Reforma do direito penal, constituições.
                </div>
                <div class="price-container" data-materia="História do Direito">
                    <div class="price-selector">
                        <label class="option"><input type="radio" name="hd" value="55" checked onclick="updatePrice(this)"> Digital (PDF)</label>
                        <label class="option"><input type="radio" name="hd" value="65" onclick="updatePrice(this)"> Impresso</label>
                    </div>
                    <div class="price-display">R$ 55,00</div>
                    <span class="pix-tag">Pagamento via PIX</span>
                    <button class="btn-comprar" onclick="checkout(this)">COMPRAR AGORA</button>
                </div>
            </article>

            <article class="card">
                <h3>Psicologia Jurídica e Relações Interpessoais</h3>
                <div class="subtopicos">
                    Mediação Familiar, Resolução de Conflitos, Crianças e adolescentes, Alineação Parental, raízes da violência, Violência de Gênero, Relações Humanas/Interpessoais.
                </div>
                <div class="price-container" data-materia="Psicologia Jurídica">
                    <div class="price-selector">
                        <label class="option"><input type="radio" name="psic" value="55" checked onclick="updatePrice(this)"> Digital (PDF)</label>
                        <label class="option"><input type="radio" name="psic" value="65" onclick="updatePrice(this)"> Impresso</label>
                    </div>
                    <div class="price-display">R$ 55,00</div>
                    <span class="pix-tag">Pagamento via PIX</span>
                    <button class="btn-comprar" onclick="checkout(this)">COMPRAR AGORA</button>
                </div>
            </article>

            <article class="card">
                <h3>Teoria Geral do Direito</h3>
                <div class="subtopicos">
                    <b>Parte 1:</b> Objetividade e Subjetividade, tipos e fontes do conhecimento, Zetética e dogmática, Escolas do direito, Subjetividade Potestativa, Hermeneutica Juritica, Fontes do Direito. <br>
                    <b>Parte 2:</b> Teoria da Norma Jurídica, HIerarquia das Normas, Sanções ou Punições, Teoria do Ordenamento Jurítico, questão temporal, Direito Neoconstitucionalismo, Direitos Humanos.
                </div>
                <div class="price-container" data-materia="Teoria Geral do Direito">
                    <div class="price-selector">
                        <label class="option"><input type="radio" name="tgd" value="55" checked onclick="updatePrice(this)"> Digital (PDF)</label>
                        <label class="option"><input type="radio" name="tgd" value="65" onclick="updatePrice(this)"> Impresso</label>
                    </div>
                    <div class="price-display">R$ 55,00</div>
                    <span class="pix-tag">Pagamento via PIX</span>
                    <button class="btn-comprar" onclick="checkout(this)">COMPRAR AGORA</button>
                </div>
            </article>
        </div>

        <h2 class="section-title">2º Semestre</h2>
        <div class="grid-cards">
            
            <article class="card">
                <h3>Direito Civil - Parte Geral</h3>
                <div class="subtopicos">
                    Conceitos de direito Civil, Código Civil de 2002, Princípios Básicos, Das pessoas Naturais, Capacidade Jurídica e Legitimação, Sujeitos da Relação Jurídica, Teorias, Das incapacidades, Cessação da incapacidade, Da Ausência, Dos bens, Classificação dos bens, Fatos Jurídico, Negócio Jurídico.
                </div>
                <div class="price-container" data-materia="Direito Civil (Parte Geral)">
                    <div class="price-selector">
                        <label class="option"><input type="radio" name="civ1" value="55" checked onclick="updatePrice(this)"> Digital (PDF)</label>
                        <label class="option"><input type="radio" name="civ1" value="65" onclick="updatePrice(this)"> Impresso</label>
                    </div>
                    <div class="price-display">R$ 55,00</div>
                    <span class="pix-tag">Pagamento via PIX</span>
                    <button class="btn-comprar" onclick="checkout(this)">COMPRAR AGORA</button>
                </div>
            </article>

            <article class="card">
                <h3>Direito Constitucional</h3>
                <div class="subtopicos">
                    Direito Publico e privado, Conceito do direito Constitucional, Limitação do poder do Estado, Conceito da Constituição, Concepções da constituição, Classificação da Constituição, O que é Constitucionalismo, desdobramentos, Neocontitucionalismo, Jusnaturalismo, Positivismo, Poder constituinte, Aplicabilidade das normas constitucionais, Bloco de Constitucionalidade, Métodos de Interpretação Constitucional.
                </div>
                <div class="price-container" data-materia="Direito Constitucional">
                    <div class="price-selector">
                        <label class="option"><input type="radio" name="const" value="55" checked onclick="updatePrice(this)"> Digital (PDF)</label>
                        <label class="option"><input type="radio" name="const" value="65" onclick="updatePrice(this)"> Impresso</label>
                    </div>
                    <div class="price-display">R$ 55,00</div>
                    <span class="pix-tag">Pagamento via PIX</span>
                    <button class="btn-comprar" onclick="checkout(this)">COMPRAR AGORA</button>
                </div>
            </article>

            <article class="card">
                <h3>Direito Criminal - Penal 1</h3>
                <div class="subtopicos">
                    Introdução e principios fundamentais, Divisões do Direito Penal, Fases Históricas da Pena, Período Humanitário, Escola Penais, Fundamentos Constitucionais do Direito Penal, Direito pena Moderno, Princípios limitadores do poder punitívo, Conceito e função da norma penal, Normas penais inconpletas ou imperfeitas, fontes do direito penal, tipos de norma penais, interpretação da lei, Lei penal no tempo, Lei penal no espaço.
                </div>
                <div class="price-container" data-materia="Direito Criminal (Penal 1)">
                    <div class="price-selector">
                        <label class="option"><input type="radio" name="pen1" value="55" checked onclick="updatePrice(this)"> Digital (PDF)</label>
                        <label class="option"><input type="radio" name="pen1" value="65" onclick="updatePrice(this)"> Impresso</label>
                    </div>
                    <div class="price-display">R$ 55,00</div>
                    <span class="pix-tag">Pagamento via PIX</span>
                    <button class="btn-comprar" onclick="checkout(this)">COMPRAR AGORA</button>
                </div>
            </article>
        </div>

        <h2 class="section-title">3º Semestre (Em Produção)</h2>
        <div class="grid-cards">
            <article class="card em-producao">
                <span class="badge-breve">Em Breve</span>
                <h3>Direito Civil - Obrigações e Resp. Civil</h3>
                <div class="subtopicos">Material em Produção - Aguarde</div>
            </article>
            <article class="card em-producao">
                <span class="badge-breve">Em Breve</span>
                <h3>Direito Constitucional - Org. Estado</h3>
                <div class="subtopicos">Material em Produção - Aguarde</div>
            </article>
            <article class="card em-producao">
                <span class="badge-breve">Em Breve</span>
                <h3>Direito Criminal - Penal 2</h3>
                <div class="subtopicos">Material em Produção - Aguarde</div>
            </article>
            <article class="card em-producao">
                <span class="badge-breve">Em Breve</span>
                <h3>Processual Civil - Parte Geral e Tutela</h3>
                <div class="subtopicos">Material em Produção - Aguarde</div>
            </article>
            <article class="card em-producao">
                <span class="badge-breve">Em Breve</span>
                <h3>Direitos Humanos, Diversidade e Inclusão</h3>
                <div class="subtopicos">Material em Produção - Aguarde</div>
            </article>
        </div>
    </main>

    <script>
        // Lógica de Atualização de Preço
        function updatePrice(radio) {
            const container = radio.closest('.price-container');
            const display = container.querySelector('.price-display');
            display.innerText = `R$ ${radio.value},00`;
        }

        // Lógica de Redirecionamento WhatsApp
        function checkout(btn) {
            const container = btn.closest('.price-container');
            const materia = container.getAttribute('data-materia');
            const formato = container.querySelector('input:checked').parentElement.innerText.trim();
            const preco = container.querySelector('.price-display').innerText;
            
            const telefone = "5569992168120";
            const mensagem = encodeURIComponent(`Olá! Gostaria de comprar o resumo de *${materia}* no formato *${formato}* (${preco}). Aguardo os dados para o PIX.`);
            
            window.location.href = `https://wa.me/${telefone}?text=${mensagem}`;
        }
    </script>
</body>
</html>
