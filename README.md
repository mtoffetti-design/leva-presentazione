# leva-presentazione
<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LEVA: dall'aula all'avatar</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            overflow: hidden;
        }

        .presentation-container {
            width: 100vw;
            height: 100vh;
            position: relative;
        }

        .slide {
            width: 100%;
            height: 100%;
            display: none;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 60px;
            background: rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(10px);
            position: absolute;
            top: 0;
            left: 0;
        }

        .slide.active {
            display: flex;
            animation: fadeIn 0.8s ease-in-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .slide h1 {
            font-size: 3.5em;
            margin-bottom: 30px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
            background: linear-gradient(45deg, #fff, #f0f0f0);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .slide h2 {
            font-size: 2.8em;
            margin-bottom: 25px;
            color: #ffd700;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
        }

        .slide h3 {
            font-size: 1.8em;
            margin-bottom: 20px;
            color: #e6e6fa;
            font-weight: 300;
        }

        .slide p {
            font-size: 1.4em;
            line-height: 1.6;
            margin-bottom: 20px;
            max-width: 900px;
        }

        .slide ul {
            list-style: none;
            font-size: 1.3em;
            line-height: 1.8;
            max-width: 800px;
        }

        .slide li {
            margin-bottom: 15px;
            padding-left: 30px;
            position: relative;
        }

        .slide li:before {
            content: "✦";
            position: absolute;
            left: 0;
            color: #ffd700;
            font-size: 1.2em;
        }

        .quote {
            font-style: italic;
            font-size: 1.5em;
            border-left: 4px solid #ffd700;
            padding-left: 30px;
            margin: 30px 0;
            background: rgba(255, 255, 255, 0.1);
            padding: 30px;
            border-radius: 10px;
        }

        .leva-letter {
            display: inline-block;
            font-size: 4em;
            color: #ffd700;
            margin-right: 20px;
            text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.5);
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }

        .navigation {
            position: fixed;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 15px;
            z-index: 1000;
        }

        button {
            padding: 12px 25px;
            background: rgba(255, 255, 255, 0.2);
            border: 2px solid rgba(255, 255, 255, 0.3);
            color: white;
            cursor: pointer;
            border-radius: 25px;
            font-size: 1em;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }

        button:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-2px);
        }

        button:disabled {
            opacity: 0.5;
            cursor: not-allowed;
        }

        .slide-counter {
            position: fixed;
            top: 30px;
            right: 30px;
            background: rgba(255, 255, 255, 0.2);
            padding: 10px 20px;
            border-radius: 20px;
            backdrop-filter: blur(10px);
            font-size: 1.1em;
        }

        .title-slide {
            background: linear-gradient(135deg, #2c3e50 0%, #4a6741 50%, #2c3e50 100%);
        }

        .leva-slide {
            background: linear-gradient(135deg, #8b5cf6 0%, #06b6d4 100%);
        }

        .final-slide {
            background: linear-gradient(135deg, #1e1e2e 0%, #3d4f7c 100%);
        }

        .lantern-icon {
            font-size: 3em;
            color: #ffd700;
            margin: 20px 0;
            animation: glow 3s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { text-shadow: 0 0 20px #ffd700; }
            to { text-shadow: 0 0 40px #ffd700, 0 0 60px #ffd700; }
        }

        .question-slide {
            font-size: 1.2em;
        }

        .question-slide h2 {
            color: #ff6b6b;
        }
    </style>
</head>
<body>
    <div class="presentation-container">
        <div class="slide-counter">
            <span id="current-slide">1</span> / <span id="total-slides">14</span>
        </div>

        <!-- Slide 1: Titolo -->
        <div class="slide active title-slide">
            <h1>LEVA: dall'aula all'avatar</h1>
            <h3>Una proposta psicopedagogica per ritrovare l'umano nell'educazione con intelligenza artificiale</h3>
            <div class="lantern-icon">🏮</div>
        </div>

        <!-- Slide 2: La Nuova Realtà -->
        <div class="slide">
            <h2>Oltre i confini di gesso e legno</h2>
            <ul>
                <li>L'insegnamento si smaterializza, il sapere corre nel digitale</li>
                <li>Le aule si disciolgono, i docenti diventano icone</li>
                <li>Gli studenti si specchiano in schermi che osservano</li>
            </ul>
            <p style="margin-top: 40px; font-style: italic; color: #e6e6fa;">
                "Viviamo in un tempo in cui l'insegnamento ha smesso di avere confini di gesso e legno..."
            </p>
        </div>

        <!-- Slide 3: La Domanda Cruciale -->
        <div class="slide question-slide">
            <h2>Che cosa stiamo diventando?</h2>
            <ul>
                <li>Un vero potenziamento o una nuova dipendenza?</li>
                <li>Efficienza, ottimizzazione, progresso...</li>
                <li>...o solo una maschera per la disumanizzazione?</li>
            </ul>
        </div>

        <!-- Slide 4: Heidegger -->
        <div class="slide">
            <h2>La tecnica e il rischio di "inquadrare"</h2>
            <div class="quote">
                "L'essenza della tecnica moderna non è tecnica, ma un modo di 'inquadrare' la realtà, di pro-vocarla a mostrarsi come risorsa disponibile."
                <br><em>— M. Heidegger</em>
            </div>
            <p><strong>L'educazione può essere ridotta a calcolo o ottimizzata come un algoritmo?</strong></p>
        </div>

        <!-- Slide 5: Essenza dell'Apprendimento -->
        <div class="slide">
            <h2>L'Apprendimento è...</h2>
            <ul>
                <li>Lentezza, inciampo, silenzio</li>
                <li>Il tempo dell'errore, della meraviglia, del dubbio</li>
                <li>L'abbraccio di un insegnante che comprende</li>
                <li>L'empatia, insimulabile da una macchina</li>
            </ul>
        </div>

        <!-- Slide 6: Non Rifiutare -->
        <div class="slide">
            <h2>Integrare, non rigettare</h2>
            <ul>
                <li>Non siamo qui per rigettare la tecnologia. Sarebbe cieco.</li>
                <li>Siamo qui per restituirle un senso</li>
                <li>Quale posto le spetta nella casa dell'umano?</li>
            </ul>
        </div>

        <!-- Slide 7: Presentazione LEVA -->
        <div class="slide leva-slide">
            <h2>Il Modello LEVA</h2>
            <h3>Una Postura per l'Educazione</h3>
            <p>Non un protocollo. Non un'app. È una postura. Un orientamento dell'anima.</p>
            <div style="font-size: 5em; margin: 30px 0; text-shadow: 4px 4px 8px rgba(0,0,0,0.5);">
                L E V A
            </div>
        </div>

        <!-- Slide 8: L - Lentezza -->
        <div class="slide leva-slide">
            <div class="leva-letter">L</div>
            <h2>Lentezza</h2>
            <p>Perché imparare è anche perdersi, non solo arrivare. Favorisce la riflessione e la profondità.</p>
            <div style="font-size: 3em; margin: 30px 0;">🐌</div>
        </div>

        <!-- Slide 9: E - Empatia -->
        <div class="slide leva-slide">
            <div class="leva-letter">E</div>
            <h2>Empatia</h2>
            <p>Perché educare è prima di tutto incontrare l'altro. Riconosce il valore dell'interazione umana autentica.</p>
            <div style="font-size: 3em; margin: 30px 0;">💝</div>
        </div>

        <!-- Slide 10: V - Verità -->
        <div class="slide leva-slide">
            <div class="leva-letter">V</div>
            <h2>Verità</h2>
            <p>Perché non tutto ciò che funziona è vero, e non tutto ciò che è vero è misurabile. Supera la logica dell'ottimizzazione algoritmica.</p>
            <div style="font-size: 3em; margin: 30px 0;">⚖️</div>
        </div>

        <!-- Slide 11: A - Autonomia -->
        <div class="slide leva-slide">
            <div class="leva-letter">A</div>
            <h2>Autonomia</h2>
            <p>Perché formare non è riempire, ma accendere. Promuove il pensiero critico e l'indipendenza.</p>
            <div style="font-size: 3em; margin: 30px 0;">🔥</div>
        </div>

        <!-- Slide 12: LEVA Lanterna -->
        <div class="slide">
            <h2>LEVA: La nostra Lanterna nel buio digitale</h2>
            <div class="lantern-icon">🏮</div>
            <ul>
                <li>La forza gentile che solleva l'educazione dal rischio della disumanizzazione</li>
                <li>La lanterna che cerca ancora mani per brillare</li>
            </ul>
        </div>

        <!-- Slide 13: La Scelta -->
        <div class="slide final-slide">
            <h2>La Nostra Scelta Oggi</h2>
            <p>Consegnarsi all'omologazione di un apprendimento standardizzato e algoritmico...</p>
            <p style="margin: 40px 0; font-size: 1.6em; color: #ffd700;"><strong>...oppure...</strong></p>
            <p>Restare custodi di uno spazio fragile, umano, irriducibile, in cui il sapere non è solo un prodotto, ma un incontro.</p>
        </div>

        <!-- Slide 14: Invito -->
        <div class="slide final-slide">
            <h1>Io scelgo la lanterna.</h1>
            <div class="lantern-icon">🏮</div>
            <h2 style="margin-top: 50px; color: #ffd700;">Voi?</h2>
        </div>

        <div class="navigation">
            <button id="prev-btn" onclick="previousSlide()">← Precedente</button>
            <button id="next-btn" onclick="nextSlide()">Successiva →</button>
        </div>
    </div>

    <script>
        let currentSlide = 0;
        const slides = document.querySelectorAll('.slide');
        const totalSlides = slides.length;
        
        document.getElementById('total-slides').textContent = totalSlides;

        function showSlide(n) {
            slides[currentSlide].classList.remove('active');
            currentSlide = (n + totalSlides) % totalSlides;
            slides[currentSlide].classList.add('active');
            
            document.getElementById('current-slide').textContent = currentSlide + 1;
            
            // Update navigation buttons
            document.getElementById('prev-btn').disabled = currentSlide === 0;
            document.getElementById('next-btn').disabled = currentSlide === totalSlides - 1;
        }

        function nextSlide() {
            if (currentSlide < totalSlides - 1) {
                showSlide(currentSlide + 1);
            }
        }

        function previousSlide() {
            if (currentSlide > 0) {
                showSlide(currentSlide - 1);
            }
        }

        // Keyboard navigation
        document.addEventListener('keydown', function(e) {
            if (e.key === 'ArrowRight' || e.key === ' ') {
                nextSlide();
            } else if (e.key === 'ArrowLeft') {
                previousSlide();
            } else if (e.key === 'Home') {
                showSlide(0);
            } else if (e.key === 'End') {
                showSlide(totalSlides - 1);
            }
        });

        // Initialize
        showSlide(0);
    </script>
</body>
</html>
