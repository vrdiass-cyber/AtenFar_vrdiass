<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portal AtenFar | UniFAI</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        .gradient-bg { background: linear-gradient(135deg, #1e3a8a 0%, #3b82f6 100%); }
        .card-hover:hover { transform: translateY(-5px); transition: all 0.3s ease; }
        .hidden-quiz { display: none; }
    </style>
</head>
<body class="bg-gray-50 font-sans">

    <header class="gradient-bg text-white p-6 shadow-lg">
        <div class="container mx-auto flex justify-between items-center">
            <div>
                <h1 class="text-2xl font-bold tracking-tight">Atenção Farmacêutica</h1>
                <p class="text-blue-100 text-sm italic">UniFAI - Farmácia (9º Termo)</p>
            </div>
            <nav class="hidden md:block">
                <ul class="flex space-x-6 text-sm">
                    <li><a href="#dashboard" class="hover:underline">Dashboard</a></li>
                    <li><a href="#quiz" class="hover:underline font-bold bg-white text-blue-800 px-3 py-1 rounded">Fazer Quiz</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <main class="container mx-auto px-4 py-8">
        
        <section id="dashboard" class="mb-16">
            <h3 class="text-2xl font-bold text-gray-800 mb-6">Resumo do Conteúdo</h3>
            <div class="grid md:grid-cols-2 gap-6 mb-12">
                <div class="bg-white p-6 rounded-xl shadow-md border-l-4 border-blue-500 card-hover">
                    <div class="flex items-center mb-4">
                        <i class="fas fa-boxes text-blue-500 text-2xl mr-3"></i>
                        <h2 class="text-xl font-bold text-gray-800">Assistência Farmacêutica</h2>
                    </div>
                    <p class="text-gray-600 mb-4 text-sm leading-relaxed">Focada no <strong>medicamento</strong>. Envolve a gestão logística: seleção, programação, aquisição e distribuição.</p>
                </div>

                <div class="bg-white p-6 rounded-xl shadow-md border-l-4 border-green-500 card-hover">
                    <div class="flex items-center mb-4">
                        <i class="fas fa-hand-holding-medical text-green-500 text-2xl mr-3"></i>
                        <h2 class="text-xl font-bold text-gray-800">Atenção Farmacêutica</h2>
                    </div>
                    <p class="text-gray-600 mb-4 text-sm leading-relaxed">Focada no <strong>doente</strong>. É a provisão responsável da farmacoterapia para obter resultados que melhorem a qualidade de vida.</p>
                </div>
            </div>

            <div class="grid md:grid-cols-3 gap-6">
                <div class="bg-red-50 p-6 rounded-lg border border-red-200">
                    <h4 class="font-bold text-red-700 mb-2 italic">1. Necessidade</h4>
                    <p class="text-xs text-red-800">O doente tem um problema de saúde não tratado ou usa um fármaco sem indicação.</p>
                </div>
                <div class="bg-yellow-50 p-6 rounded-lg border border-yellow-200">
                    <h4 class="font-bold text-yellow-700 mb-2 italic">2. Efetividade</h4>
                    <p class="text-xs text-yellow-800">O fármaco não atinge os objetivos terapêuticos ou a dose é insuficiente.</p>
                </div>
                <div class="bg-blue-50 p-6 rounded-lg border border-blue-200">
                    <h4 class="font-bold text-blue-700 mb-2 italic">3. Segurança</h4>
                    <p class="text-xs text-blue-800">O doente sofre reações adversas ou a dose é excessiva (toxicidade).</p>
                </div>
            </div>
        </section>

        <section id="quiz" class="bg-white p-8 rounded-2xl shadow-xl border border-blue-100 max-w-3xl mx-auto">
            <div class="text-center mb-8">
                <span class="bg-blue-100 text-blue-800 text-xs font-bold px-3 py-1 rounded-full uppercase">Interativo</span>
                <h3 class="text-3xl font-bold text-gray-800 mt-2">Quiz de Conhecimentos</h3>
                <p class="text-gray-500 mt-2">Teste o que aprendeu no material do Prof. Dr. Valter Dias</p>
            </div>

            <div id="quiz-container">
                <div class="quiz-step" id="step-1">
                    <p class="text-lg font-semibold text-gray-700 mb-4">1. De acordo com Hepler & Strand (1990), a Atenção Farmacêutica é a provisão responsável da farmacoterapia com o objetivo de:</p>
                    <div class="space-y-3">
                        <button onclick="checkAnswer(1, false)" class="w-full text-left p-4 rounded-lg border border-gray-200 hover:bg-gray-50 transition">Aumentar o stock de medicamentos na farmácia.</button>
                        <button onclick="checkAnswer(1, true)" class="w-full text-left p-4 rounded-lg border border-gray-200 hover:bg-gray-50 transition">Alcançar resultados definidos que melhorem a qualidade de vida do doente.</button>
                        <button onclick="checkAnswer(1, false)" class="w-full text-left p-4 rounded-lg border border-gray-200 hover:bg-gray-50 transition">Garantir apenas a entrega do medicamento prescrito.</button>
                    </div>
                </div>

                <div class="quiz-step hidden-quiz" id="step-2">
                    <p class="text-lg font-semibold text-gray-700 mb-4">2. Se um doente apresenta um problema de saúde por NÃO estar a utilizar um medicamento de que necessita, qual o PRM identificado?</p>
                    <div class="space-y-3">
                        <button onclick="checkAnswer(2, true)" class="w-full text-left p-4 rounded-lg border border-gray-200 hover:bg-gray-50 transition">PRM de Necessidade.</button>
                        <button onclick="checkAnswer(2, false)" class="w-full text-left p-4 rounded-lg border border-gray-200 hover:bg-gray-50 transition">PRM de Efetividade.</button>
                        <button onclick="checkAnswer(2, false)" class="w-full text-left p-4 rounded-lg border border-gray-200 hover:bg-gray-50 transition">PRM de Segurança.</button>
                    </div>
                </div>

                <div class="quiz-step hidden-quiz" id="step-3">
                    <p class="text-lg font-semibold text-gray-700 mb-4">3. Qual destas atividades pertence ao ciclo da Assistência Farmacêutica (Logística) e não à Atenção?</p>
                    <div class="space-y-3">
                        <button onclick="checkAnswer(3, false)" class="w-full text-left p-4 rounded-lg border border-gray-200 hover:bg-gray-50 transition">Seguimento Farmacoterapêutico.</button>
                        <button onclick="checkAnswer(3, true)" class="w-full text-left p-4 rounded-lg border border-gray-200 hover:bg-gray-50 transition">Programação e Aquisição de Medicamentos.</button>
                        <button onclick="checkAnswer(3, false)" class="w-full text-left p-4 rounded-lg border border-gray-200 hover:bg-gray-50 transition">Educação em Saúde ao doente.</button>
                    </div>
                </div>

                <div id="quiz-result" class="hidden-quiz text-center">
                    <div class="text-5xl mb-4">🎉</div>
                    <h4 class="text-2xl font-bold text-gray-800">Incrível!</h4>
                    <p class="text-gray-600 mt-2">Concluiu o simulado de Atenção Farmacêutica.</p>
                    <button onclick="location.reload()" class="mt-6 bg-blue-600 text-white px-6 py-2 rounded-full hover:bg-blue-700">Refazer Quiz</button>
                </div>
            </div>
        </section>

        <footer class="mt-16 text-center text-gray-400 text-sm">
            <p>© 2026 - UniFAI - Adamantina/SP</p>
        </footer>
    </main>

    <script>
        let currentStep = 1;
        const totalSteps = 3;

        function checkAnswer(step, isCorrect) {
            if (isCorrect) {
                alert("Correto! ✅");
                goToNextStep();
            } else {
                alert("Ops, tente novamente! ❌");
            }
        }

        function goToNextStep() {
            document.getElementById(`step-${currentStep}`).classList.add('hidden-quiz');
            currentStep++;
            
            if (currentStep <= totalSteps) {
                document.getElementById(`step-${currentStep}`).classList.remove('hidden-quiz');
            } else {
                document.getElementById('quiz-result').classList.remove('hidden-quiz');
            }
        }
    </script>
</body>
</html>
