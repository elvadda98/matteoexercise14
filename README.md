<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Capital Letters Practice</title>
    <style>
        * {
            box-sizing: border-box;
        }
        body {
            font-family: Georgia, 'Times New Roman', serif;
            background: linear-gradient(160deg, #2b1055, #7597de00), #1a1a2e;
            background: linear-gradient(160deg, #2b1055, #4a1e6e);
            margin: 0;
            padding: 25px;
            color: #eee;
            min-height: 100vh;
        }
        .wrap {
            max-width: 860px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.97);
            color: #2b2b2b;
            border-radius: 24px 24px 60px 24px;
            padding: 30px;
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.45);
        }
        header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 12px;
            margin-bottom: 22px;
            padding-bottom: 18px;
            border-bottom: 3px dashed #b980ff;
        }
        h1 {
            font-size: 26px;
            margin: 0;
            color: #5b21b6;
        }
        h1 span {
            color: #ec4899;
        }
        .score-pill {
            background: linear-gradient(135deg, #f472b6, #a855f7);
            color: white;
            font-weight: bold;
            padding: 10px 22px;
            border-radius: 999px;
            font-family: 'Segoe UI', sans-serif;
            font-size: 15px;
            box-shadow: 0 4px 10px rgba(168, 85, 247, 0.4);
        }
        .tabs {
            display: flex;
            gap: 10px;
            margin-bottom: 25px;
            flex-wrap: wrap;
        }
        .tab {
            font-family: 'Segoe UI', sans-serif;
            background: #f3e8ff;
            color: #6b21a8;
            border: 2px solid #d8b4fe;
            padding: 10px 18px;
            border-radius: 14px;
            cursor: pointer;
            font-size: 14px;
            font-weight: 600;
            transition: all 0.25s;
        }
        .tab:hover {
            background: #e9d5ff;
        }
        .tab.active {
            background: linear-gradient(135deg, #a855f7, #6b21a6);
            color: white;
            border-color: transparent;
            box-shadow: 0 5px 12px rgba(168, 85, 247, 0.35);
        }
        .panel {
            display: none;
        }
        .panel.active {
            display: block;
            animation: fadeIn 0.4s ease;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(8px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .task-box {
            background: linear-gradient(135deg, #fdf4ff, #fae8ff);
            border: 2px solid #e9d5ff;
            border-radius: 16px;
            padding: 16px 20px;
            margin-bottom: 24px;
            font-size: 16px;
            font-style: italic;
            color: #581c87;
        }
        .card {
            background: #fff;
            border: 2px solid #e5d5f8;
            border-radius: 14px;
            padding: 16px 18px;
            margin-bottom: 16px;
            transition: border-color 0.25s;
        }
        .card .question {
            font-size: 17px;
            margin: 0 0 10px 0;
        }
        .card .num {
            display: inline-block;
            background: linear-gradient(135deg, #ec4899, #a855f7);
            color: white;
            width: 30px;
            height: 30px;
            line-height: 30px;
            text-align: center;
            border-radius: 50%;
            font-family: 'Segoe UI', sans-serif;
            font-size: 14px;
            font-weight: bold;
            margin-right: 10px;
        }
        .card input[type="text"] {
            width: 100%;
            padding: 11px 14px;
            border: 2px solid #ddd6fe;
            border-radius: 10px;
            font-size: 15px;
            font-family: Georgia, serif;
            outline: none;
            transition: border-color 0.2s;
        }
        .card input[type="text"]:focus {
            border-color: #a855f7;
        }
        .feedback {
            margin-top: 8px;
            font-size: 14px;
            font-family: 'Segoe UI', sans-serif;
            min-height: 18px;
        }
        .ok {
            border-color: #86efac !important;
            background: #f0fdf4 !important;
        }
        .bad {
            border-color: #fca5a5 !important;
            background: #fef2f2 !important;
        }
        .btn-row {
            display: flex;
            gap: 12px;
            margin-top: 20px;
            flex-wrap: wrap;
        }
        .btn {
            font-family: 'Segoe UI', sans-serif;
            font-size: 15px;
            font-weight: 600;
            border: none;
            padding: 12px 26px;
            border-radius: 999px;
            cursor: pointer;
            transition: all 0.25s;
        }
        .btn-primary {
            background: linear-gradient(135deg, #ec4899, #8b5cf6);
            color: white;
            box-shadow: 0 5px 14px rgba(236, 72, 153, 0.4);
        }
        .btn-primary:hover {
            transform: translateY(-2px);
        }
        .btn-ghost {
            background: white;
            color: #7c3aed;
            border: 2px solid #c4b5fd;
        }
        .btn-ghost:hover {
            background: #f5f3ff;
        }
        /* Exercise 2 styles */
        .story-box {
            background: #fffdf5;
            border: 2px dashed #d6c68b;
            border-radius: 16px;
            padding: 24px 26px;
            font-size: 18px;
            line-height: 2.3;
            margin-bottom: 20px;
        }
        .tok {
            cursor: pointer;
            padding: 2px 7px;
            border-radius: 8px;
            transition: all 0.15s;
        }
        .tok:hover {
            background: #fce7f3;
        }
        .tok.marked {
            background: linear-gradient(135deg, #fbcfe8, #e9d5ff);
            color: #6b21a8;
            font-weight: bold;
            border-bottom: 3px solid #ec4899;
        }
        .tok.wrong {
            background: #fee2e2;
            color: #b91c1c;
            border-bottom: 3px solid #ef4444;
            font-weight: normal;
        }
        .tok.missed {
            background: #ffedd5;
            color: #c2410c;
            border-bottom: 3px solid #f97316;
        }
        .story-hint {
            font-family: 'Segoe UI', sans-serif;
            font-size: 14px;
            color: #7c6f4f;
            margin-top: -12px;
            margin-bottom: 18px;
        }
        .result-banner {
            display: none;
            font-family: 'Segoe UI', sans-serif;
            font-size: 16px;
            font-weight: 600;
            padding: 14px 20px;
            border-radius: 12px;
            margin-top: 18px;
        }
    </style>
</head>
<body>
    <div class="wrap">
        <header>
            <h1>Capital Letters <span>Studio 🎨</span></h1>
            <div class="score-pill" id="scorePill">Score: 0 / 31</div>
        </header>

        <div class="tabs">
            <div class="tab active" id="tab1" onclick="showPanel('p1', this)">✍️ Part 1 — Rewrite the Sentences</div>
            <div class="tab" id="tab2" onclick="showPanel('p2', this)">🔍 Part 2 — Fix the Story</div>
        </div>

        <!-- PART 1 -->
        <div class="panel active" id="p1">
            <div class="task-box">
                Rewrite each sentence correctly. Every proper noun — names of people, cities, countries, days, months, and places — must start with a capital letter!
            </div>
            <div class="card">
                <p class="question"><span class="num">1</span>on monday, sofia flew from milan to lisbon.</p>
                <input type="text" id="q1" placeholder="Type the corrected sentence...">
                <div class="feedback" id="f1"></div>
            </div>
            <div class="card">
                <p class="question"><span class="num">2</span>my cousin ben lives near lake como.</p>
                <input type="text" id="q2" placeholder="Type the corrected sentence...">
                <div class="feedback" id="f2"></div>
            </div>
            <div class="card">
                <p class="question"><span class="num">3</span>we watched frozen at the cinema in december.</p>
                <input type="text" id="q3" placeholder="Type the corrected sentence...">
                <div class="feedback" id="f3"></div>
            </div>
            <div class="card">
                <p class="question"><span class="num">4</span>professor grey teaches french at oxford university.</p>
                <input type="text" id="q4" placeholder="Type the corrected sentence...">
                <div class="feedback" id="f4"></div>
            </div>
            <div class="card">
                <p class="question"><span class="num">5</span>last summer, amanda visited the eiffel tower in paris.</p>
                <input type="text" id="q5" placeholder="Type the corrected sentence...">
                <div class="feedback" id="f5"></div>
            </div>
            <div class="btn-row">
                <button class="btn btn-primary" onclick="checkPart1()">✔ Check Answers</button>
                <button class="btn btn-ghost" onclick="resetPart1()">↺ Reset</button>
            </div>
        </div>

        <!-- PART 2 -->
        <div class="panel" id="p2">
            <div class="task-box">
                Read the story and click on <strong>every word</strong> that should start with a capital letter. Click a word again to unselect it. When you're done, check your answers!
            </div>
            <div class="story-box" id="storyBox"></div>
            <div class="story-hint">💡 Tip: look for names of people, cities, countries, languages, days, months, and the word "I"!</div>
            <div class="btn-row">
                <button class="btn btn-primary" onclick="checkPart2()">✔ Check Answers</button>
                <button class="btn btn-ghost" onclick="resetPart2()">↺ Reset</button>
            </div>
            <div class="result-banner" id="banner"></div>
        </div>
    </div>

    <script>
        // ===== PART 1 DATA =====
        const part1Answers = [
            "On Monday, Sofia flew from Milan to Lisbon.",
            "My cousin Ben lives near Lake Como.",
            "We watched Frozen at the cinema in December.",
            "Professor Grey teaches French at Oxford University.",
            "Last summer, Amanda visited the Eiffel Tower in Paris."
        ];

        // ===== PART 2 DATA =====
        const storyText = "dear emma, how are you? my name is luca and i am writing from rome, italy. next friday, my family and i are moving to a new apartment near the colosseum. my sister chiara is very excited because her best friend nina lives on the same street. in october, we will start school at st. patrick academy. i am a little nervous, but i am also happy to make new friends. on weekends, my father wants to visit the vatican museums and my mother wants to try a restaurant called da mario. write back soon! your friend, marco";

        // Words that must be capitalized (exact matches, lowercase in the text)
        const capitalWords = [
            "dear", "emma,", "my", "luca", "i", "i", "rome,", "italy.",
            "next", "friday,", "i", "colosseum.", "chiara", "nina", "in",
            "october,", "we", "st.", "i", "i", "i", "i", "on", "the",
            "my", "da", "write", "your", "marco"
        ];

        // Count expected occurrences per word (multiset)
        const expectedCounts = {};
        capitalWords.forEach(w => {
            expectedCounts[w] = (expectedCounts[w] || 0) + 1;
        });

        let score = 0;
        const TOTAL = 31; // 5 (part 1) + 26 (part 2)
        let part1Scored = [false, false, false, false, false];
        let part2Prev = 0;

        function updateScore() {
            document.getElementById('scorePill').textContent = `Score: ${score} / ${TOTAL}`;
        }

        function showPanel(id, tabEl) {
            document.querySelectorAll('.panel').forEach(p => p.classList.remove('active'));
            document.getElementById(id).classList.add('active');
            document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
            tabEl.classList.add('active');
        }

        // ===== PART 1 =====
        function checkPart1() {
            let gained = 0;
            for (let i = 0; i < part1Answers.length; i++) {
                const input = document.getElementById('q' + (i + 1));
                const fb = document.getElementById('f' + (i + 1));
                const user = input.value.trim().replace(/\s+/g, ' ').replace(/[.!?]+$/, '');
                const target = part1Answers[i].replace(/[.!?]+$/, '');

                if (user.length > 0 && user.toLowerCase() === target.toLowerCase()) {
                    input.className = 'ok';
                    fb.textContent = 'Correct! 🌟';
                    fb.style.color = '#15803d';
                    if (!part1Scored[i]) {
                        part1Scored[i] = true;
                        gained++;
                    }
                } else {
                    input.className = 'bad';
                    fb.textContent = 'Not quite — check every name, place, day and month!';
                    fb.style.color = '#b91c1c';
                    if (part1Scored[i]) {
                        part1Scored[i] = false;
                        gained--;
                    }
                }
            }
            score += gained;
            updateScore();
        }

        function resetPart1() {
            for (let i = 1; i <= 5; i++) {
                const input = document.getElementById('q' + i);
                input.value = '';
                input.className = '';
                document.getElementById('f' + i).textContent = '';
            }
            for (let i = 0; i < 5; i++) {
                if (part1Scored[i]) score--;
                part1Scored[i] = false;
            }
            updateScore();
        }

        // ===== PART 2 =====
        function buildStory() {
            const box = document.getElementById('storyBox');
            box.innerHTML = '';
            storyText.split(' ').forEach(word => {
                const span = document.createElement('span');
                span.className = 'tok';
                span.textContent = word;
                span.onclick = () => span.classList.toggle('marked');
                box.appendChild(span);
                box.appendChild(document.createTextNode(' '));
            });
        }

        function checkPart2() {
            const tokens = document.querySelectorAll('#storyBox .tok');

            // Count how many times each word is marked
            const markedCounts = {};
            let totalMarked = 0;
            tokens.forEach(t => {
                t.classList.remove('wrong', 'missed');
                if (t.classList.contains('marked')) {
                    const key = t.textContent.toLowerCase();
                    markedCounts[key] = (markedCounts[key] || 0) + 1;
                    totalMarked++;
                }
            });

            // Evaluate each token
            let correct = 0;
            let missed = 0;
            let wrong = 0;
            const markedSoFar = {};
            tokens.forEach(t => {
                const key = t.textContent.toLowerCase();
                const expected = expectedCounts[key] || 0;
                const seen = markedSoFar[key] || 0;
                markedSoFar[key] = seen + 1;

                const isMarked = t.classList.contains('marked');
                // This occurrence "deserves" a mark if we haven't exhausted the expected count
                const deserves = seen < expected;

                if (deserves && isMarked) {
                    correct++;
                } else if (deserves && !isMarked) {
                    missed++;
                    t.classList.add('missed');
                } else if (!deserves && isMarked) {
                    wrong++;
                    t.classList.add('wrong');
                    t.classList.remove('marked');
                }
            });

            score = score - part2Prev + correct;
            part2Prev = correct;
            updateScore();

            const totalNeeded = Object.values(expectedCounts).reduce((a, b) => a + b, 0);
            const banner = document.getElementById('banner');
            banner.style.display = 'block';

            if (correct === totalNeeded) {
                banner.style.background = '#dcfce7';
                banner.style.color = '#166534';
                banner.textContent = `🎉 Perfect! You found all ${totalNeeded} words that need a capital letter!`;
            } else {
                banner.style.background = '#ffedd5';
                banner.style.color = '#c2410c';
                banner.textContent = `You found ${correct} of ${totalNeeded} words. ` +
                    (missed > 0 ? `${missed} word(s) you missed are shown in orange. ` : '') +
                    (wrong > 0 ? `${wrong} word(s) marked wrongly are shown in red. ` : '') +
                    `Fix them and check again!`;
            }
        }

        function resetPart2() {
            document.querySelectorAll('#storyBox .tok').forEach(t => {
                t.classList.remove('marked', 'wrong', 'missed');
            });
            score -= part2Prev;
            part2Prev = 0;
            document.getElementById('banner').style.display = 'none';
            updateScore();
        }

        // INIT
        buildStory();
        updateScore();
    </script>
</body>
</html>
