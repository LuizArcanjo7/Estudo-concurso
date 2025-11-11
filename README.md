<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>App de Estudos - TCE/MG Engenharia</title>
    <!-- Carrega o Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Carrega a biblioteca de ícones Lucide -->
    <script type="module" src="https://unpkg.com/lucide-react@latest/dist/umd/lucide.js"></script>
    <script src="https://unpkg.com/lucide-react@latest/dist/umd/lucide.js"></script>

    <style>
        /* Fonte Inter */
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap');
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f1f5f9; /* slate-100 */
        }
        /* Estilo customizado para o scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
            height: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f5f9;
            border-radius: 10px;
        }
        ::-webkit-scrollbar-thumb {
            background: #94a3b8; /* slate-400 */
            border-radius: 10px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #64748b; /* slate-500 */
        }
        /* Animação de carregamento */
        .loader {
            border: 4px solid #f3f3f3;
            border-top: 4px solid #4f46e5; /* indigo-600 */
            border-radius: 50%;
            width: 40px;
            height: 40px;
            animation: spin 1s linear infinite;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
    </style>
</head>
<body class="text-slate-800">

    <div class="container mx-auto p-4 md:p-8 max-w-7xl">
        <!-- Cabeçalho -->
        <header class="mb-8 p-6 bg-white rounded-lg shadow-md">
            <h1 class="text-3xl font-bold text-indigo-700">Plano de Estudos Interativo</h1>
            <p class="text-lg text-slate-600">Analista de Controle Externo – Engenharia (TCE/MG)</p>
        </header>

        <!-- Seção de Matérias Gerais -->
        <section class="mb-10">
            <h2 class="text-2xl font-semibold mb-4 text-slate-700">Conhecimentos Gerais (P1)</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <!-- Card de Matéria -->
                <div class="bg-white rounded-lg shadow-md p-5 flex flex-col justify-between hover:shadow-lg transition-shadow">
                    <div>
                        <h3 class="text-xl font-semibold text-indigo-800">Língua Portuguesa</h3>
                        <p class="text-sm text-slate-500 mb-4">10 Questões (12.5%)</p>
                    </div>
                    <button onclick="openModal('portugues')" class="w-full bg-indigo-600 text-white font-medium py-2 px-4 rounded-lg hover:bg-indigo-700 transition-colors">
                        Estudar
                    </button>
                </div>
                <!-- Card de Matéria -->
                <div class="bg-white rounded-lg shadow-md p-5 flex flex-col justify-between hover:shadow-lg transition-shadow">
                    <div>
                        <h3 class="text-xl font-semibold text-indigo-800">Direito Administrativo</h3>
                        <p class="text-sm text-slate-500 mb-4">6 Questões (7.5%)</p>
                    </div>
                    <button onclick="openModal('admin')" class="w-full bg-indigo-600 text-white font-medium py-2 px-4 rounded-lg hover:bg-indigo-700 transition-colors">
                        Estudar
                    </button>
                </div>
                <!-- Card de Matéria -->
                <div class="bg-white rounded-lg shadow-md p-5 flex flex-col justify-between hover:shadow-lg transition-shadow">
                    <div>
                        <h3 class="text-xl font-semibold text-indigo-800">Controle Externo</h3>
                        <p class="text-sm text-slate-500 mb-4">6 Questões (7.5%)</p>
                    </div>
                    <button onclick="openModal('controle')" class="w-full bg-indigo-600 text-white font-medium py-2 px-4 rounded-lg hover:bg-indigo-700 transition-colors">
                        Estudar
                    </button>
                </div>
                <!-- Card de Matéria -->
                <div class="bg-white rounded-lg shadow-md p-5 flex flex-col justify-between hover:shadow-lg transition-shadow">
                    <div>
                        <h3 class="text-xl font-semibold text-indigo-800">Direito Constitucional</h3>
                        <p class="text-sm text-slate-500 mb-4">4 Questões (5.0%)</p>
                    </div>
                    <button onclick="openModal('constitucional')" class="w-full bg-indigo-600 text-white font-medium py-2 px-4 rounded-lg hover:bg-indigo-700 transition-colors">
                        Estudar
                    </button>
                </div>
                <!-- Card de Matéria -->
                <div class="bg-white rounded-lg shadow-md p-5 flex flex-col justify-between hover:shadow-lg transition-shadow">
                    <div>
                        <h3 class="text-xl font-semibold text-indigo-800">Noções de Direitos Humanos</h3>
                        <p class="text-sm text-slate-500 mb-4">4 Questões (5.0%)</p>
                    </div>
                    <button onclick="openModal('humanos')" class="w-full bg-indigo-600 text-white font-medium py-2 px-4 rounded-lg hover:bg-indigo-700 transition-colors">
                        Estudar
                    </button>
                </div>
            </div>
        </section>

        <!-- Seção de Matérias Específicas -->
        <section>
            <h2 class="text-2xl font-semibold mb-4 text-slate-700">Conhecimentos Específicos (P2)</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <!-- Card de Matéria -->
                <div class="bg-white rounded-lg shadow-md p-5 flex flex-col justify-between hover:shadow-lg transition-shadow">
                    <div>
                        <h3 class="text-xl font-semibold text-blue-800">Obras - Planejamento, Normas...</h3>
                        <p class="text-sm text-slate-500 mb-4">14 Questões (17.5%)</p>
                    </div>
                    <button onclick="openModal('obrasPlanejamento')" class="w-full bg-blue-600 text-white font-medium py-2 px-4 rounded-lg hover:bg-blue-700 transition-colors">
                        Estudar
                    </button>
                </div>
                <!-- Card de Matéria -->
                <div class="bg-white rounded-lg shadow-md p-5 flex flex-col justify-between hover:shadow-lg transition-shadow">
                    <div>
                        <h3 class="text-xl font-semibold text-blue-800">Obras de Edificações</h3>
                        <p class="text-sm text-slate-500 mb-4">12 Questões (15.0%)</p>
                    </div>
                    <button onclick="openModal('obrasEdificacoes')" class="w-full bg-blue-600 text-white font-medium py-2 px-4 rounded-lg hover:bg-blue-700 transition-colors">
                        Estudar
                    </button>
                </div>
                <!-- Card de Matéria -->
                <div class="bg-white rounded-lg shadow-md p-5 flex flex-col justify-between hover:shadow-lg transition-shadow">
                    <div>
                        <h3 class="text-xl font-semibold text-blue-800">Obras Hídricas</h3>
                        <p class="text-sm text-slate-500 mb-4">8 Questões (10.0%)</p>
                    </div>
                    <button onclick="openModal('obrasHidricas')" class="w-full bg-blue-600 text-white font-medium py-2 px-4 rounded-lg hover:bg-blue-700 transition-colors">
                        Estudar
                    </button>
                </div>
                <!-- Card de Matéria -->
                <div class="bg-white rounded-lg shadow-md p-5 flex flex-col justify-between hover:shadow-lg transition-shadow">
                    <div>
                        <h3 class="text-xl font-semibold text-blue-800">Obras Rodoviárias</h3>
                        <p class="text-sm text-slate-500 mb-4">8 Questões (10.0%)</p>
                    </div>
                    <button onclick="openModal('obrasRodoviarias')" class="w-full bg-blue-600 text-white font-medium py-2 px-4 rounded-lg hover:bg-blue-700 transition-colors">
                        Estudar
                    </button>
                </div>
                <!-- Card de Matéria -->
                <div class="bg-white rounded-lg shadow-md p-5 flex flex-col justify-between hover:shadow-lg transition-shadow">
                    <div>
                        <h3 class="text-xl font-semibold text-blue-800">Auditoria do Setor Público</h3>
                        <p class="text-sm text-slate-500 mb-4">8 Questões (10.0%)</p>
                    </div>
                    <button onclick="openModal('auditoria')" class="w-full bg-blue-600 text-white font-medium py-2 px-4 rounded-lg hover:bg-blue-700 transition-colors">
                        Estudar
                    </button>
                </div>
            </div>
        </section>
    </div>

    <!-- Modal de Estudo -->
    <div id="studyModal" class="fixed inset-0 bg-black bg-opacity-60 hidden flex items-center justify-center p-4 z-50 backdrop-blur-sm">
        <div class="bg-white rounded-xl shadow-2xl w-full max-w-4xl max-h-[90vh] flex flex-col overflow-hidden">
            <!-- Cabeçalho do Modal -->
            <div class="flex justify-between items-center p-5 border-b border-slate-200">
                <h2 id="modalTitle" class="text-2xl font-bold text-indigo-700"></h2>
                <button onclick="closeModal()" class="text-slate-400 hover:text-red-600 transition-colors">
                    <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path></svg>
                </button>
            </div>

            <!-- Conteúdo do Modal -->
            <div class="p-6 flex-grow overflow-y-auto grid grid-cols-1 lg:grid-cols-2 gap-6">
                <!-- Coluna 1: Gerador de Conteúdo -->
                <div class="flex flex-col space-y-4">
                    <h3 class="text-xl font-semibold text-slate-700 border-b pb-2">Gerador de Estudo Interativo</h3>
                    <p class="text-sm text-slate-500">Selecione um tópico do edital para gerar um flashcard ou uma questão de múltipla escolha.</p>
                    
                    <div>
                        <label for="topicSelect" class="block text-sm font-medium text-slate-700 mb-1">Tópico do Edital:</label>
                        <select id="topicSelect" class="w-full p-2 border border-slate-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-indigo-500">
                            <!-- Tópicos serão inseridos aqui via JS -->
                        </select>
                    </div>
                    
                    <div class="flex flex-col sm:flex-row gap-3">
                        <button id="generateQuestionBtn" onclick="handleGenerateContent('questao')" class="flex-1 bg-indigo-600 text-white font-medium py-2 px-4 rounded-lg hover:bg-indigo-700 transition-colors flex items-center justify-center gap-2">
                            <i data-lucide="file-question"></i>
                            Gerar Questão
                        </button>
                        <button id="generateFlashcardBtn" onclick="handleGenerateContent('flashcard')" class="flex-1 bg-blue-600 text-white font-medium py-2 px-4 rounded-lg hover:bg-blue-700 transition-colors flex items-center justify-center gap-2">
                            <i data-lucide="layers"></i>
                            Gerar Flashcard
                        </button>
                    </div>

                    <!-- Área de Conteúdo Gerado -->
                    <div id="generatedContentArea" class="border-2 border-dashed border-slate-300 rounded-lg p-4 bg-slate-50 min-h-[300px] flex items-center justify-center">
                        <span class="text-slate-400 text-center">O conteúdo gerado aparecerá aqui.</span>
                    </div>
                </div>

                <!-- Coluna 2: Checklist do Edital -->
                <div class="flex flex-col">
                    <h3 class="text-xl font-semibold text-slate-700 border-b pb-2 mb-4">Checklist de Conteúdo</h3>
                    <div id="checklistArea" class="space-y-3 overflow-y-auto max-h-[500px] pr-2">
                        <!-- Checklist será inserido aqui via JS -->
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Inicializa os ícones do Lucide
        lucide.createIcons();

        // --- Banco de Dados dos Tópicos do Edital ---
        // (Baseado no plano de estudos)
        const materiasData = {
            portugues: {
                title: "Língua Portuguesa",
                topics: [
                    "Compreensão e interpretação de textos",
                    "Tipologia e gêneros textuais",
                    "Ortografia",
                    "Coesão textual (referenciação, conectores, tempos verbais)",
                    "Estrutura morfossintática (classes de palavras, pontuação, concordância, regência, crase)",
                    "Reescrita de frases (significação, substituição, reorganização)"
                ]
            },
            admin: {
                title: "Direito Administrativo",
                topics: [
                    "Noções de organização administrativa (Centralização, descentralização)",
                    "Ato administrativo (Conceito, requisitos, atributos)",
                    "Agentes públicos (Cargo, emprego, função)",
                    "Poderes administrativos (Hierárquico, disciplinar, de polícia)",
                    "Licitação (Princípios, contratação direta, modalidades - Foco na Lei nº 14.133/2021)",
                    "Controle da administração pública (Administrativo, judicial, legislativo)",
                    "Responsabilidade civil do Estado",
                    "Contratos administrativos (Foco na Lei nº 14.133/2021)",
                    "Desapropriação",
                    "Súmulas e jurisprudência (STF e STJ)",
                    "Acesso à Informação (Lei nº 12.527/2011)",
                    "Lei Geral de Proteção de Dados (Lei nº 13.709/2018)"
                ]
            },
            controle: {
                title: "Controle Externo",
                topics: [
                    "Conceito, tipos e formas de controle (Interno, externo, parlamentar)",
                    "Lei de Improbidade Administrativa (Lei nº 8.429/1992)",
                    "Sistemas de controle jurisdicional",
                    "Tribunal de Contas (TCU, TCs)",
                    "TCE/MG na Constituição Estadual",
                    "Lei Orgânica do TCE/MG (Lei Complementar nº 102/2008)",
                    "Regimento Interno do TCE/MG (Resolução nº 24/2023)"
                ]
            },
            constitucional: {
                title: "Direito Constitucional",
                topics: [
                    "Princípios fundamentais (Art. 1º ao 4º)",
                    "Aplicabilidade das normas constitucionais",
                    "Direitos e garantias fundamentais (Art. 5º)",
                    "Direitos sociais, nacionalidade, políticos",
                    "Organização político-administrativa (União, estados, municípios)",
                    "Administração pública (Art. 37 ao 41)",
                    "Poder Executivo",
                    "Poder Legislativo (Processo legislativo, fiscalização contábil/financeira)",
                    "Poder Judiciário",
                    "Funções essenciais à justiça",
                    "Constituição do Estado de Minas Gerais (Tópicos pertinentes)"
                ]
            },
            humanos: {
                title: "Noções de Direitos Humanos",
                topics: [
                    "Teoria geral dos direitos fundamentais",
                    "Direitos Humanos vs. Direitos Fundamentais",
                    "Declaração Universal dos Direitos Humanos",
                    "Agenda 2030 da ONU",
                    "Estatuto da Pessoa com Deficiência (Lei nº 13.146/2015)",
                    "Acessibilidade (Lei nº 10.098/2000)",
                    "Atendimento prioritário (Lei nº 10.048/2000)",
                    "Estatuto da Igualdade Racial (Lei nº 12.288/2010)"
                ]
            },
            auditoria: {
                title: "Auditoria do Setor Público",
                topics: [
                    "Conceito, finalidade, objetivo, abrangência",
                    "Auditoria interna e externa: papéis",
                    "Instrumentos de fiscalização (auditoria, levantamento, monitoramento)",
                    "Tipos de auditoria (Conformidade, Operacional, Financeira)",
                    "Normas de auditoria do TCU",
                    "Normas da INTOSAI (ISSAIs 100, 200, 300, 400)",
                    "Normas Brasileiras de Auditoria do Setor Público (NBASP)",
                    "Planejamento de auditoria (Escopo, Materialidade, risco, relevância)",
                    "Amostragem estatística em auditoria",
                    "Matriz de planejamento",
                    "Execução da auditoria (Programas, Papéis de trabalho, Testes)",
                    "Técnicas e procedimentos (exame documental, inspeção física, etc.)",
                    "Evidências e Caracterização de achados de auditoria",
                    "Matriz de Achados e Matriz de Responsabilização",
                    "Relatórios de auditoria"
                ]
            },
            obrasPlanejamento: {
                title: "Obras - Planejamento, Normas, Fiscalização",
                topics: [
                    "Planejamento, programação e controle de projetos e obras",
                    "Viabilidade técnico-econômica e físico-financeira",
                    "Análise de documentação (Editais, contratos, aditivos, projetos)",
                    "Compatibilização de Projetos",
                    "Segurança e higiene do trabalho (NRs)",
                    "Fiscalização de obras (Medições, reajustamento, diário de obras, recebimento)",
                    "Avaliação de custos (Orçamento, BDI, encargos sociais)",
                    "Licitação de obras públicas (Foco na Lei nº 14.133/2021)",
                    "Projeto Básico e Projeto Executivo (Lei nº 14.133/2021)",
                    "Contratos administrativos de obras (Lei nº 14.133/2021)",
                    "Legislação ambiental (Licenciamento, EIA/RIMA)",
                    "Lei de Concessões (Lei nº 8.987/1995)",
                    "Parcerias Público-Privadas (Lei nº 11.079/2004)"
                ]
            },
            obrasEdificacoes: {
                title: "Obras de Edificações",
                topics: [
                    "Análise orçamentária (Composição de custos, curva ABC)",
                    "SINAPI (Conceitos e aplicação)",
                    "Canteiro de obras e fundações (diretas e indiretas)",
                    "Estruturas de concreto armado e protendido",
                    "Estruturas metálicas",
                    "Impermeabilização (Tipos e aplicação)",
                    "Instalações prediais (elétrica, hidrossanitária, prevenção a incêndio)",
                    "Controle de qualidade de materiais (concreto, aço, etc.)",
                    "Engenharia de Avaliações (NBR 14653)",
                    "Gestão na produção de edificações"
                ]
            },
            obrasHidricas: {
                title: "Obras Hídricas",
                topics: [
                    "Estruturas hidráulicas (Barragens, canais, bueiros)",
                    "Aproveitamento hidrelétrico (Avaliação de potencial, turbinas)",
                    "Irrigação e drenagem",
                    "Obras de saneamento: Abastecimento d'água (captação, adução, ETA)",
                    "Obras de saneamento: Coleta e tratamento de esgoto (ETE, lagoas)",
                    "Obras de saneamento: Drenagem urbana (macrodrenagem, canalização)",
                    "Operação e manutenção de sistemas de saneamento"
                ]
            },
            obrasRodoviarias: {
                title: "Obras Rodoviárias",
                topics: [
                    "Estudos geotécnicos e sondagens",
                    "Ensaios de solo, materiais betuminosos e agregados",
                    "Terraplanagem (cortes, aterros, bota-fora)",
                    "Pavimentação (subleito, sub-base, base, revestimento asfáltico)",
                    "Drenagem rodoviária",
                    "Obras de arte especiais (pontes, viadutos)",
                    "Análise orçamentária (SICRO - Metodologia e conceitos)",
                    "Fiscalização de obras rodoviárias (medições, controle de qualidade)",
                    "Impactos ambientais em obras rodoviárias"
                ]
            }
        };

        // --- Variáveis Globais ---
        const modal = document.getElementById('studyModal');
        const modalTitle = document.getElementById('modalTitle');
        const topicSelect = document.getElementById('topicSelect');
        const checklistArea = document.getElementById('checklistArea');
        const generatedContentArea = document.getElementById('generatedContentArea');
        const generateQuestionBtn = document.getElementById('generateQuestionBtn');
        const generateFlashcardBtn = document.getElementById('generateFlashcardBtn');

        let currentMateriaKey = null;

        // --- Funções do Modal ---
        
        /**
         * Abre o modal e popula com os dados da matéria selecionada.
         * @param {string} materiaKey - A chave da matéria (ex: 'portugues').
         */
        function openModal(materiaKey) {
            currentMateriaKey = materiaKey;
            const data = materiasData[materiaKey];
            
            if (!data) {
                console.error("Matéria não encontrada:", materiaKey);
                return;
            }

            // Limpa conteúdos anteriores
            modalTitle.textContent = data.title;
            topicSelect.innerHTML = '';
            checklistArea.innerHTML = '';
            generatedContentArea.innerHTML = '<span class="text-slate-400 text-center">O conteúdo gerado aparecerá aqui.</span>';

            // Popula o <select> de tópicos
            data.topics.forEach((topic, index) => {
                const option = document.createElement('option');
                option.value = topic;
                option.textContent = topic;
                topicSelect.appendChild(option);
            });

            // Popula o checklist
            data.topics.forEach((topic, index) => {
                const checklistId = `check-${materiaKey}-${index}`;
                const item = document.createElement('label');
                item.htmlFor = checklistId;
                item.className = "flex items-center p-2 rounded-lg hover:bg-slate-100 cursor-pointer";
                item.innerHTML = `
                    <input type="checkbox" id="${checklistId}" class="h-5 w-5 rounded border-slate-300 text-indigo-600 focus:ring-indigo-500 mr-3">
                    <span class="text-slate-700">${topic}</span>
                `;
                checklistArea.appendChild(item);
            });

            // Exibe o modal
            modal.classList.remove('hidden');
        }

        /**
         * Fecha o modal de estudo.
         */
        function closeModal() {
            modal.classList.add('hidden');
            currentMateriaKey = null;
        }

        // --- Funções da API Gemini ---

        /**
         * Manipulador principal para gerar conteúdo (questão ou flashcard).
         * @param {string} type - 'questao' ou 'flashcard'.
         */
        async function handleGenerateContent(type) {
            const selectedTopic = topicSelect.value;
            if (!selectedTopic) {
                alert("Por favor, selecione um tópico.");
                return;
            }

            const data = materiasData[currentMateriaKey];
            const prompt = createPrompt(selectedTopic, type, data.title);
            
            showLoading(true);

            try {
                const textResponse = await callGeminiAPI(prompt);
                displayGeneratedContent(textResponse, type);
            } catch (error) {
                console.error("Erro ao gerar conteúdo:", error);
                displayError("Desculpe, não foi possível gerar o conteúdo no momento. Tente novamente.");
            } finally {
                showLoading(false);
            }
        }

        /**
         * Cria o prompt para a API Gemini.
         * @param {string} topic - O tópico selecionado.
         * @param {string} type - 'questao' ou 'flashcard'.
         * @param {string} subject - O nome da matéria.
         * @returns {string} O prompt formatado.
         */
        function createPrompt(topic, type, subject) {
            if (type === 'questao') {
                return `Você é um especialista em criar questões para concursos da banca CEBRASPE (múltipla escolha, 5 alternativas).
Matenha o idioma da resposta em Português.
Crie uma questão de múltipla escolha (A, B, C, D, E) sobre o seguinte tópico de "${subject}":
TÓPICO: "${topic}"

Formate a resposta EXATAMENTE da seguinte maneira, sem nenhum texto introdutório ou final:
ENUNCIADO: [Texto do enunciado da questão]
A) [Texto da alternativa A]
B) [Texto da alternativa B]
C) [Texto da alternativa C]
D) [Texto da alternativa D]
E) [Texto da alternativa E]
RESPOSTA: [Letra da alternativa correta, ex: A]`;
            } 
            if (type === 'flashcard') {
                return `Você é um especialista em criar flashcards de estudo para concursos.
Matenha o idioma da resposta em Português.
Crie um flashcard (pergunta curta e resposta direta) sobre o seguinte tópico de "${subject}":
TÓPICO: "${topic}"

Formate a resposta EXATAMENTE da seguinte maneira, sem nenhum texto introdutório ou final:
PERGUNTA: [Texto da pergunta do flashcard]
RESPOSTA: [Texto da resposta do flashcard]`;
            }
        }

        /**
         * Chama a API Gemini com retry e exponential backoff.
         * @param {string} userQuery - O prompt para o modelo.
         * @returns {Promise<string>} O texto da resposta do modelo.
         */
        async function callGeminiAPI(userQuery) {
            const apiKey = ""; // Deixe em branco, será tratado pelo ambiente
            const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-09-2025:generateContent?key=${apiKey}`;

            const payload = {
                contents: [{ parts: [{ text: userQuery }] }],
                // Configurações para respostas mais consistentes
                generationConfig: {
                    temperature: 0.5,
                    topK: 1,
                    topP: 1,
                    maxOutputTokens: 2048,
                },
            };

            let response;
            let retries = 3;
            let delay = 1000; // 1 segundo

            while (retries > 0) {
                try {
                    response = await fetch(apiUrl, {
                        method: 'POST',
                        headers: { 'Content-Type': 'application/json' },
                        body: JSON.stringify(payload)
                    });

                    if (!response.ok) {
                        throw new Error(`HTTP error! status: ${response.status}`);
                    }

                    const result = await response.json();
                    
                    if (result.candidates && result.candidates[0].content?.parts?.[0]?.text) {
                        return result.candidates[0].content.parts[0].text;
                    } else {
                        throw new Error("Resposta inesperada ou vazia da API.");
                    }

                } catch (error) {
                    console.warn(`Tentativa falhou. Retentando em ${delay}ms...`);
                    retries--;
                    if (retries === 0) {
                        throw error; // Lança o erro após todas as tentativas
                    }
                    await new Promise(resolve => setTimeout(resolve, delay));
                    delay *= 2; // Exponential backoff
                }
            }
        }

        /**
         * Exibe o conteúdo gerado (questão ou flashcard) na interface.
         * @param {string} text - O texto bruto da API.
         * @param {string} type - 'questao' ou 'flashcard'.
         */
        function displayGeneratedContent(text, type) {
            generatedContentArea.innerHTML = ''; // Limpa a área
            
            if (type === 'questao') {
                displayQuestion(text);
            } else if (type === 'flashcard') {
                displayFlashcard(text);
            }
        }

        /**
         * Formata e exibe uma questão de múltipla escolha.
         * @param {string} text - O texto bruto da API.
         */
        function displayQuestion(text) {
            try {
                const enunciado = text.match(/ENUNCIADO: ([\s\S]*?)\nA\)/)[1].trim();
                const altA = text.match(/A\) ([\s\S]*?)\nB\)/)[1].trim();
                const altB = text.match(/B\) ([\s\S]*?)\nC\)/)[1].trim();
                const altC = text.match(/C\) ([\s\S]*?)\nD\)/)[1].trim();
                const altD = text.match(/D\) ([\s\S]*?)\nE\)/)[1].trim();
                const altE = text.match(/E\) ([\s\S]*?)\nRESPOSTA:/)[1].trim();
                const respostaCorreta = text.match(/RESPOSTA: ([A-E])/)[1].trim();

                const alternatives = [
                    { id: 'A', text: altA },
                    { id: 'B', text: altB },
                    { id: 'C', text: altC },
                    { id: 'D', text: altD },
                    { id: 'E', text: altE }
                ];

                let alternativesHtml = alternatives.map(alt => `
                    <label class="block p-3 rounded-lg border border-slate-300 hover:bg-slate-100 cursor-pointer transition-colors">
                        <input type="radio" name="question" value="${alt.id}" class="mr-3 text-indigo-600 focus:ring-indigo-500">
                        <span class="font-medium">${alt.id})</span> ${alt.text}
                    </label>
                `).join('');

                generatedContentArea.innerHTML = `
                    <div class="w-full text-left space-y-4">
                        <p class="font-semibold text-lg text-slate-800">${enunciado}</p>
                        <div class="space-y-3" id="alternativesContainer">
                            ${alternativesHtml}
                        </div>
                        <button onclick="revealAnswer('${respostaCorreta}')" class="bg-green-600 text-white font-medium py-2 px-4 rounded-lg hover:bg-green-700 transition-colors">
                            Revelar Resposta
                        </button>
                        <div id="answerFeedback" class="hidden mt-3 p-3 rounded-lg"></div>
                    </div>
                `;
            } catch (e) {
                console.error("Erro ao parsear questão:", e, "\nTexto recebido:", text);
                displayError("Erro ao formatar a questão recebida da API. O formato pode ser inesperado.");
            }
        }

        /**
         * Formata e exibe um flashcard.
         * @param {string} text - O texto bruto da API.
         */
        function displayFlashcard(text) {
            try {
                const pergunta = text.match(/PERGUNTA: ([\s\S]*?)\nRESPOSTA:/)[1].trim();
                const resposta = text.match(/RESPOSTA: ([\s\S]*)/)[1].trim();

                generatedContentArea.innerHTML = `
                    <div class="w-full h-full flex flex-col items-center justify-center p-4">
                        <div id="flashcard" class="w-full max-w-md h-64 perspective">
                            <div class="relative w-full h-full transition-transform duration-700 transform-style-3d" id="flashcardInner">
                                <!-- Frente -->
                                <div class="absolute w-full h-full backface-hidden bg-blue-100 border border-blue-300 rounded-lg p-6 flex flex-col justify-center items-center shadow-lg">
                                    <span class="text-sm font-semibold text-blue-700 mb-2">PERGUNTA</span>
                                    <p class="text-lg font-medium text-center text-blue-900">${pergunta}</p>
                                </div>
                                <!-- Verso -->
                                <div class="absolute w-full h-full backface-hidden bg-green-100 border border-green-300 rounded-lg p-6 flex flex-col justify-center items-center shadow-lg rotate-y-180">
                                    <span class="text-sm font-semibold text-green-700 mb-2">RESPOSTA</span>
                                    <p class="text-lg font-medium text-center text-green-900">${resposta}</p>
                                </div>
                            </div>
                        </div>
                        <button onclick="flipCard()" class="mt-6 bg-gray-700 text-white font-medium py-2 px-6 rounded-lg hover:bg-gray-800 transition-colors">
                            Virar Card
                        </button>
                    </div>
                `;
                // Adiciona estilos para o flip do card
                const style = document.createElement('style');
                style.innerHTML = `
                    .perspective { perspective: 1000px; }
                    .transform-style-3d { transform-style: preserve-3d; }
                    .backface-hidden { backface-visibility: hidden; -webkit-backface-visibility: hidden; }
                    .rotate-y-180 { transform: rotateY(180deg); }
                    .flipped { transform: rotateY(180deg); }
                `;
                document.head.appendChild(style);
            } catch (e) {
                console.error("Erro ao parsear flashcard:", e, "\nTexto recebido:", text);
                displayError("Erro ao formatar o flashcard recebido da API. O formato pode ser inesperado.");
            }
        }

        /**
         * Vira o flashcard.
         */
        function flipCard() {
            document.getElementById('flashcardInner').classList.toggle('flipped');
        }

        /**
         * Revela a resposta da questão de múltipla escolha.
         * @param {string} respostaCorreta - A letra da resposta correta (ex: 'A').
         */
        function revealAnswer(respostaCorreta) {
            const selected = document.querySelector('input[name="question"]:checked');
            const feedback = document.getElementById('answerFeedback');
            const alternatives = document.querySelectorAll('#alternativesContainer label');

            if (!selected) {
                feedback.textContent = 'Por favor, selecione uma alternativa.';
                feedback.className = 'p-3 rounded-lg bg-yellow-100 text-yellow-800 border border-yellow-300';
                feedback.classList.remove('hidden');
                return;
            }

            const userAnswer = selected.value;

            alternatives.forEach(label => {
                const input = label.querySelector('input');
                label.classList.remove('bg-red-100', 'border-red-300', 'bg-green-100', 'border-green-300');
                
                if (input.value === respostaCorreta) {
                    label.classList.add('bg-green-100', 'border-green-300');
                } else if (input.value === userAnswer) {
                    label.classList.add('bg-red-100', 'border-red-300');
                }
            });

            if (userAnswer === respostaCorreta) {
                feedback.textContent = `Correto! A resposta é a ${respostaCorreta}.`;
                feedback.className = 'p-3 rounded-lg bg-green-100 text-green-800 border border-green-300';
            } else {
                feedback.textContent = `Incorreto. Você marcou ${userAnswer}, mas a resposta correta é ${respostaCorreta}.`;
                feedback.className = 'p-3 rounded-lg bg-red-100 text-red-800 border border-red-300';
            }
            feedback.classList.remove('hidden');
        }


        /**
         * Exibe ou esconde o indicador de carregamento.
         * @param {boolean} isLoading - Se deve ou não mostrar o loader.
         */
        function showLoading(isLoading) {
            if (isLoading) {
                generatedContentArea.innerHTML = `
                    <div class="flex flex-col items-center justify-center text-slate-500">
                        <div class="loader mb-4"></div>
                        <span>Gerando conteúdo...</span>
                    </div>
                `;
                generateQuestionBtn.disabled = true;
                generateFlashcardBtn.disabled = true;
            } else {
                generateQuestionBtn.disabled = false;
                generateFlashcardBtn.disabled = false;
                // O conteúdo será preenchido por displayGeneratedContent
            }
        }

        /**
         * Exibe uma mensagem de erro na área de conteúdo.
         * @param {string} message - A mensagem de erro.
         */
        function displayError(message) {
            generatedContentArea.innerHTML = `
                <div class="flex flex-col items-center justify-center text-red-600 p-4">
                    <i data-lucide="alert-triangle" class="w-12 h-12 mb-3"></i>
                    <span class="font-medium text-center">${message}</span>
                </div>
            `;
            // Re-inicializa o ícone
            lucide.createIcons();
        }

    </script>
</body>
</html>
