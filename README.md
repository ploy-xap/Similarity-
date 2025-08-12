# Similarity-
<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>เกมทดสอบความรู้: ความคล้าย ม.3</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Sarabun:wght@300;400;600;700&display=swap');
        body { font-family: 'Sarabun', sans-serif; }
        .question-card {
            transform: translateY(20px);
            opacity: 0;
            animation: slideIn 0.5s ease-out forwards;
        }
        @keyframes slideIn {
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }
        .correct-answer {
            background: linear-gradient(135deg, #10b981, #059669);
            animation: pulse 0.6s ease-in-out;
        }
        .wrong-answer {
            background: linear-gradient(135deg, #ef4444, #dc2626);
            animation: shake 0.5s ease-in-out;
        }
        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }
        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(-5px); }
            75% { transform: translateX(5px); }
        }
        .progress-bar {
            transition: width 0.3s ease-in-out;
        }
        .qr-code {
            background: white;
            padding: 10px;
            border-radius: 10px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }
    </style>
</head>
<body class="bg-gradient-to-br from-purple-600 via-blue-600 to-indigo-700 min-h-screen">
    <div class="container mx-auto px-4 py-8">
        <!-- Header -->
        <div class="text-center mb-8">
            <h1 class="text-4xl font-bold text-white mb-4">🧮 เกมทดสอบความรู้</h1>
            <h2 class="text-2xl font-semibold text-blue-100 mb-2">ความคล้าย (Similarity)</h2>
            <p class="text-blue-200">สำหรับนักเรียนมัธยมศึกษาปีที่ 3</p>
        </div>

        <!-- Game Container -->
        <div id="gameContainer" class="max-w-4xl mx-auto">
            <!-- Start Screen -->
            <div id="startScreen" class="bg-white rounded-2xl shadow-2xl p-8 text-center">
                <div class="mb-6">
                    <div class="text-6xl mb-4">📐</div>
                    <h3 class="text-2xl font-bold text-gray-800 mb-4">ยินดีต้อนรับสู่เกมความคล้าย!</h3>
                    <p class="text-gray-600 mb-6">ทดสอบความรู้เรื่องรูปสามเหลี่ยมคล้าย การหาอัตราส่วน และการประยุกต์ใช้</p>
                </div>

                <!-- Share Links -->
                <div class="bg-gray-50 rounded-xl p-6 mb-6">
                    <h4 class="text-lg font-semibold text-gray-800 mb-4">🔗 แชร์เกมนี้</h4>
                    <div class="grid md:grid-cols-2 gap-6">
                        <div>
                            <p class="text-sm text-gray-600 mb-2">ลิงค์เว็บไซต์:</p>
                            <div class="bg-white border-2 border-dashed border-gray-300 rounded-lg p-3">
                                <code class="text-sm text-blue-600 break-all">https://similarity-game-m3.canva.site</code>
                            </div>
                            <button onclick="copyLink()" class="mt-2 bg-blue-500 hover:bg-blue-600 text-white px-4 py-2 rounded-lg text-sm transition-colors">
                                📋 คัดลอกลิงค์
                            </button>
                        </div>
                        <div class="flex flex-col items-center">
                            <p class="text-sm text-gray-600 mb-2">สแกน QR Code:</p>
                            <div class="qr-code">
                                <svg width="120" height="120" viewBox="0 0 120 120">
                                    <!-- QR Code Pattern -->
                                    <rect width="120" height="120" fill="white"/>
                                    <!-- Corner squares -->
                                    <rect x="0" y="0" width="21" height="21" fill="black"/>
                                    <rect x="3" y="3" width="15" height="15" fill="white"/>
                                    <rect x="6" y="6" width="9" height="9" fill="black"/>
                                    
                                    <rect x="99" y="0" width="21" height="21" fill="black"/>
                                    <rect x="102" y="3" width="15" height="15" fill="white"/>
                                    <rect x="105" y="6" width="9" height="9" fill="black"/>
                                    
                                    <rect x="0" y="99" width="21" height="21" fill="black"/>
                                    <rect x="3" y="102" width="15" height="15" fill="white"/>
                                    <rect x="6" y="105" width="9" height="9" fill="black"/>
                                    
                                    <!-- Data pattern -->
                                    <rect x="30" y="6" width="3" height="3" fill="black"/>
                                    <rect x="36" y="6" width="3" height="3" fill="black"/>
                                    <rect x="42" y="9" width="3" height="3" fill="black"/>
                                    <rect x="48" y="6" width="3" height="3" fill="black"/>
                                    <rect x="54" y="9" width="3" height="3" fill="black"/>
                                    <rect x="60" y="6" width="3" height="3" fill="black"/>
                                    <rect x="66" y="9" width="3" height="3" fill="black"/>
                                    <rect x="72" y="6" width="3" height="3" fill="black"/>
                                    <rect x="78" y="9" width="3" height="3" fill="black"/>
                                    <rect x="84" y="6" width="3" height="3" fill="black"/>
                                    
                                    <rect x="6" y="30" width="3" height="3" fill="black"/>
                                    <rect x="9" y="36" width="3" height="3" fill="black"/>
                                    <rect x="12" y="42" width="3" height="3" fill="black"/>
                                    <rect x="15" y="48" width="3" height="3" fill="black"/>
                                    <rect x="18" y="54" width="3" height="3" fill="black"/>
                                    <rect x="21" y="60" width="3" height="3" fill="black"/>
                                    <rect x="24" y="66" width="3" height="3" fill="black"/>
                                    <rect x="27" y="72" width="3" height="3" fill="black"/>
                                    <rect x="30" y="78" width="3" height="3" fill="black"/>
                                    <rect x="33" y="84" width="3" height="3" fill="black"/>
                                    
                                    <!-- More data patterns -->
                                    <rect x="36" y="30" width="3" height="3" fill="black"/>
                                    <rect x="42" y="33" width="3" height="3" fill="black"/>
                                    <rect x="48" y="36" width="3" height="3" fill="black"/>
                                    <rect x="54" y="39" width="3" height="3" fill="black"/>
                                    <rect x="60" y="42" width="3" height="3" fill="black"/>
                                    <rect x="66" y="45" width="3" height="3" fill="black"/>
                                    <rect x="72" y="48" width="3" height="3" fill="black"/>
                                    <rect x="78" y="51" width="3" height="3" fill="black"/>
                                    <rect x="84" y="54" width="3" height="3" fill="black"/>
                                    <rect x="90" y="57" width="3" height="3" fill="black"/>
                                    
                                    <rect x="30" y="90" width="3" height="3" fill="black"/>
                                    <rect x="36" y="93" width="3" height="3" fill="black"/>
                                    <rect x="42" y="96" width="3" height="3" fill="black"/>
                                    <rect x="48" y="99" width="3" height="3" fill="black"/>
                                    <rect x="54" y="102" width="3" height="3" fill="black"/>
                                    <rect x="60" y="105" width="3" height="3" fill="black"/>
                                    <rect x="66" y="108" width="3" height="3" fill="black"/>
                                    <rect x="72" y="111" width="3" height="3" fill="black"/>
                                    <rect x="78" y="114" width="3" height="3" fill="black"/>
                                    <rect x="84" y="117" width="3" height="3" fill="black"/>
                                </svg>
                            </div>
                        </div>
                    </div>
                </div>

                <button onclick="startGame()" class="bg-gradient-to-r from-purple-600 to-blue-600 hover:from-purple-700 hover:to-blue-700 text-white font-bold py-4 px-8 rounded-xl text-xl transition-all transform hover:scale-105 shadow-lg">
                    🚀 เริ่มเกม
                </button>
            </div>

            <!-- Game Screen -->
            <div id="gameScreen" class="hidden">
                <!-- Progress Bar -->
                <div class="bg-white rounded-xl p-4 mb-6 shadow-lg">
                    <div class="flex justify-between items-center mb-2">
                        <span class="text-sm font-semibold text-gray-600">ความคืบหน้า</span>
                        <span class="text-sm font-semibold text-gray-600"><span id="currentQ">1</span>/10</span>
                    </div>
                    <div class="w-full bg-gray-200 rounded-full h-3">
                        <div id="progressBar" class="progress-bar bg-gradient-to-r from-purple-500 to-blue-500 h-3 rounded-full" style="width: 10%"></div>
                    </div>
                </div>

                <!-- Score Display -->
                <div class="bg-white rounded-xl p-4 mb-6 shadow-lg text-center">
                    <div class="flex justify-center items-center space-x-6">
                        <div>
                            <div class="text-2xl font-bold text-green-600" id="score">0</div>
                            <div class="text-sm text-gray-600">คะแนน</div>
                        </div>
                        <div>
                            <div class="text-2xl font-bold text-blue-600" id="streak">0</div>
                            <div class="text-sm text-gray-600">ต่อเนื่อง</div>
                        </div>
                    </div>
                </div>

                <!-- Question Card -->
                <div id="questionCard" class="question-card bg-white rounded-2xl shadow-2xl p-8">
                    <div class="text-center mb-6">
                        <div class="text-4xl mb-4" id="questionIcon">📐</div>
                        <h3 class="text-xl font-bold text-gray-800 mb-4" id="questionText"></h3>
                        <div id="questionImage" class="mb-4"></div>
                    </div>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4" id="answersContainer">
                        <!-- Answers will be inserted here -->
                    </div>
                </div>
            </div>

            <!-- Results Screen -->
            <div id="resultsScreen" class="hidden bg-white rounded-2xl shadow-2xl p-8 text-center">
                <div class="mb-6">
                    <div class="text-6xl mb-4" id="resultIcon">🎉</div>
                    <h3 class="text-3xl font-bold text-gray-800 mb-4" id="resultTitle">ยินดีด้วย!</h3>
                    <div class="text-6xl font-bold text-purple-600 mb-2" id="finalScore">0</div>
                    <p class="text-gray-600 mb-4">คะแนนรวม</p>
                    <div id="resultMessage" class="text-lg text-gray-700 mb-6"></div>
                </div>

                <div class="bg-gray-50 rounded-xl p-6 mb-6">
                    <h4 class="text-lg font-semibold text-gray-800 mb-4">📊 สรุปผลการเล่น</h4>
                    <div class="grid grid-cols-3 gap-4 text-center">
                        <div>
                            <div class="text-2xl font-bold text-green-600" id="correctCount">0</div>
                            <div class="text-sm text-gray-600">ถูก</div>
                        </div>
                        <div>
                            <div class="text-2xl font-bold text-red-600" id="wrongCount">0</div>
                            <div class="text-sm text-gray-600">ผิด</div>
                        </div>
                        <div>
                            <div class="text-2xl font-bold text-blue-600" id="maxStreak">0</div>
                            <div class="text-sm text-gray-600">ต่อเนื่องสูงสุด</div>
                        </div>
                    </div>
                </div>

                <div class="space-y-4">
                    <button onclick="restartGame()" class="bg-gradient-to-r from-purple-600 to-blue-600 hover:from-purple-700 hover:to-blue-700 text-white font-bold py-3 px-6 rounded-xl transition-all transform hover:scale-105 shadow-lg">
                        🔄 เล่นอีกครั้ง
                    </button>
                    <button onclick="showStartScreen()" class="bg-gray-500 hover:bg-gray-600 text-white font-bold py-3 px-6 rounded-xl transition-all ml-4">
                        🏠 กลับหน้าแรก
                    </button>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Game state
        let currentQuestion = 0;
        let score = 0;
        let streak = 0;
        let maxStreak = 0;
        let correctAnswers = 0;
        let wrongAnswers = 0;

        // Questions database
        const questions = [
            {
                icon: "📐",
                text: "รูปสามเหลี่ยม ABC และ DEF คล้ายกัน หาก AB = 6 cm, BC = 8 cm, DE = 9 cm แล้ว EF เท่ากับเท่าใด?",
                image: `<svg width="300" height="200" viewBox="0 0 300 200" class="mx-auto">
                    <polygon points="50,150 150,50 200,150" fill="lightblue" stroke="blue" stroke-width="2"/>
                    <text x="100" y="170" text-anchor="middle" class="text-sm">ABC</text>
                    <text x="40" y="100" class="text-xs">6</text>
                    <text x="175" y="110" class="text-xs">8</text>
                </svg>`,
                answers: ["10 cm", "12 cm", "15 cm", "18 cm"],
                correct: 1
            },
            {
                icon: "📏",
                text: "ถ้ารูปสามเหลี่ยมสองรูปคล้ายกัน และอัตราส่วนของด้านที่สอดคล้องกันเท่ากับ 2:3 แล้วอัตราส่วนของพื้นที่เท่ากับเท่าใด?",
                answers: ["2:3", "4:9", "6:9", "8:12"],
                correct: 1
            },
            {
                icon: "🔺",
                text: "ในรูปสามเหลี่ยม ABC มี DE // BC หาก AD = 4 cm, DB = 6 cm, AE = 6 cm แล้ว EC เท่ากับเท่าใด?",
                image: `<svg width="300" height="200" viewBox="0 0 300 200" class="mx-auto">
                    <polygon points="50,50 250,50 150,150" fill="lightgreen" stroke="green" stroke-width="2"/>
                    <line x1="100" y1="75" x2="200" y2="75" stroke="red" stroke-width="2"/>
                    <text x="150" y="40" text-anchor="middle" class="text-sm">A</text>
                    <text x="40" y="60" class="text-sm">B</text>
                    <text x="260" y="60" class="text-sm">C</text>
                    <text x="90" y="90" class="text-xs">D</text>
                    <text x="210" y="90" class="text-xs">E</text>
                </svg>`,
                answers: ["8 cm", "9 cm", "10 cm", "12 cm"],
                correct: 1
            },
            {
                icon: "📐",
                text: "รูปสามเหลี่ยมคล้ายมีคุณสมบัติใดต่อไปนี้?",
                answers: ["มุมที่สอดคล้องกันเท่ากัน", "ด้านที่สอดคล้องกันเป็นสัดส่วน", "ทั้ง ก และ ข", "ไม่มีข้อใดถูก"],
                correct: 2
            },
            {
                icon: "🔢",
                text: "หากรูปสามเหลี่ยม PQR และ STU คล้ายกัน โดย PQ:ST = 3:5 และพื้นที่ของรูปสามเหลี่ยม PQR = 18 ตร.ซม. แล้วพื้นที่ของรูปสามเหลี่ยม STU เท่ากับเท่าใด?",
                answers: ["30 ตร.ซม.", "45 ตร.ซม.", "50 ตร.ซม.", "75 ตร.ซม."],
                correct: 2
            },
            {
                icon: "📏",
                text: "ในรูปสามเหลี่ยม ABC มี MN // BC หาก AM:MB = 2:3 และ BC = 15 cm แล้ว MN เท่ากับเท่าใด?",
                answers: ["6 cm", "9 cm", "10 cm", "12 cm"],
                correct: 0
            },
            {
                icon: "🔺",
                text: "รูปสามเหลี่ยมสองรูปจะคล้ายกันเมื่อใด?",
                answers: ["มีมุมหนึ่งมุมเท่ากัน", "มีด้านสองด้านเป็นสัดส่วน", "มีมุมสองมุมเท่ากัน", "มีด้านหนึ่งด้านเท่ากัน"],
                correct: 2
            },
            {
                icon: "📐",
                text: "หากรูปสามเหลี่ยม ABC ~ รูปสามเหลี่ยม DEF และ AB = 8 cm, DE = 12 cm, AC = 6 cm แล้ว DF เท่ากับเท่าใด?",
                answers: ["4 cm", "9 cm", "10 cm", "16 cm"],
                correct: 1
            },
            {
                icon: "🔢",
                text: "ถ้าอัตราส่วนของด้านที่สอดคล้องกันของรูปสามเหลี่ยมคล้ายสองรูปเท่ากับ 4:7 แล้วอัตราส่วนของเส้นรอบรูปเท่ากับเท่าใด?",
                answers: ["4:7", "8:14", "16:49", "2:3.5"],
                correct: 0
            },
            {
                icon: "📏",
                text: "ในรูปสามเหลี่ยมมุมฉาก ABC (มุม C = 90°) มี CD ⊥ AB หาก AD = 4 cm, DB = 9 cm แล้ว CD เท่ากับเท่าใด?",
                image: `<svg width="300" height="200" viewBox="0 0 300 200" class="mx-auto">
                    <polygon points="50,150 250,150 150,50" fill="lightyellow" stroke="orange" stroke-width="2"/>
                    <line x1="150" y1="50" x2="150" y2="150" stroke="red" stroke-width="2"/>
                    <text x="40" y="170" class="text-sm">A</text>
                    <text x="260" y="170" class="text-sm">B</text>
                    <text x="150" y="40" class="text-sm">C</text>
                    <text x="150" y="170" class="text-xs">D</text>
                </svg>`,
                answers: ["5 cm", "6 cm", "7 cm", "8 cm"],
                correct: 1
            }
        ];

        function startGame() {
            document.getElementById('startScreen').classList.add('hidden');
            document.getElementById('gameScreen').classList.remove('hidden');
            currentQuestion = 0;
            score = 0;
            streak = 0;
            maxStreak = 0;
            correctAnswers = 0;
            wrongAnswers = 0;
            showQuestion();
        }

        function showQuestion() {
            const question = questions[currentQuestion];
            document.getElementById('currentQ').textContent = currentQuestion + 1;
            document.getElementById('progressBar').style.width = ((currentQuestion + 1) / questions.length * 100) + '%';
            document.getElementById('questionIcon').textContent = question.icon;
            document.getElementById('questionText').textContent = question.text;
            document.getElementById('questionImage').innerHTML = question.image || '';
            
            const answersContainer = document.getElementById('answersContainer');
            answersContainer.innerHTML = '';
            
            question.answers.forEach((answer, index) => {
                const button = document.createElement('button');
                button.className = 'bg-gray-100 hover:bg-gray-200 text-gray-800 font-semibold py-4 px-6 rounded-xl transition-all transform hover:scale-105 text-left';
                button.innerHTML = `<span class="font-bold text-purple-600">${String.fromCharCode(65 + index)}.</span> ${answer}`;
                button.onclick = () => selectAnswer(index, button);
                answersContainer.appendChild(button);
            });

            // Animate question card
            const questionCard = document.getElementById('questionCard');
            questionCard.style.transform = 'translateY(20px)';
            questionCard.style.opacity = '0';
            setTimeout(() => {
                questionCard.style.transform = 'translateY(0)';
                questionCard.style.opacity = '1';
            }, 100);
        }

        function selectAnswer(selectedIndex, button) {
            const question = questions[currentQuestion];
            const allButtons = document.querySelectorAll('#answersContainer button');
            
            // Disable all buttons
            allButtons.forEach(btn => btn.disabled = true);
            
            if (selectedIndex === question.correct) {
                button.className = 'correct-answer text-white font-semibold py-4 px-6 rounded-xl text-left';
                score += 10;
                streak++;
                correctAnswers++;
                if (streak > maxStreak) maxStreak = streak;
            } else {
                button.className = 'wrong-answer text-white font-semibold py-4 px-6 rounded-xl text-left';
                allButtons[question.correct].className = 'correct-answer text-white font-semibold py-4 px-6 rounded-xl text-left';
                streak = 0;
                wrongAnswers++;
            }
            
            // Update score display
            document.getElementById('score').textContent = score;
            document.getElementById('streak').textContent = streak;
            
            setTimeout(() => {
                currentQuestion++;
                if (currentQuestion < questions.length) {
                    showQuestion();
                } else {
                    showResults();
                }
            }, 2000);
        }

        function showResults() {
            document.getElementById('gameScreen').classList.add('hidden');
            document.getElementById('resultsScreen').classList.remove('hidden');
            
            document.getElementById('finalScore').textContent = score;
            document.getElementById('correctCount').textContent = correctAnswers;
            document.getElementById('wrongCount').textContent = wrongAnswers;
            document.getElementById('maxStreak').textContent = maxStreak;
            
            let resultIcon = '🎉';
            let resultTitle = 'ยินดีด้วย!';
            let resultMessage = '';
            
            const percentage = (score / (questions.length * 10)) * 100;
            
            if (percentage >= 90) {
                resultIcon = '🏆';
                resultTitle = 'เยี่ยมมาก!';
                resultMessage = 'คุณเป็นเซียนเรื่องความคล้าย! คะแนนเกือบเต็ม 🌟';
            } else if (percentage >= 70) {
                resultIcon = '🎉';
                resultTitle = 'ดีมาก!';
                resultMessage = 'คุณมีความเข้าใจเรื่องความคล้ายเป็นอย่างดี 👏';
            } else if (percentage >= 50) {
                resultIcon = '👍';
                resultTitle = 'ดี!';
                resultMessage = 'คุณผ่านเกมแล้ว ลองฝึกฝนเพิ่มเติมนะ 📚';
            } else {
                resultIcon = '💪';
                resultTitle = 'ลองใหม่!';
                resultMessage = 'อย่าท้อ! ลองเล่นอีกครั้งและศึกษาเพิ่มเติม 🔥';
            }
            
            document.getElementById('resultIcon').textContent = resultIcon;
            document.getElementById('resultTitle').textContent = resultTitle;
            document.getElementById('resultMessage').textContent = resultMessage;
        }

        function restartGame() {
            document.getElementById('resultsScreen').classList.add('hidden');
            startGame();
        }

        function showStartScreen() {
            document.getElementById('resultsScreen').classList.add('hidden');
            document.getElementById('startScreen').classList.remove('hidden');
        }

        function copyLink() {
            const link = 'https://similarity-game-m3.canva.site';
            navigator.clipboard.writeText(link).then(() => {
                const button = event.target;
                const originalText = button.textContent;
                button.textContent = '✅ คัดลอกแล้ว!';
                button.className = 'mt-2 bg-green-500 hover:bg-green-600 text-white px-4 py-2 rounded-lg text-sm transition-colors';
                setTimeout(() => {
                    button.textContent = originalText;
                    button.className = 'mt-2 bg-blue-500 hover:bg-blue-600 text-white px-4 py-2 rounded-lg text-sm transition-colors';
                }, 2000);
            }).catch(() => {
                alert('ไม่สามารถคัดลอกลิงค์ได้ กรุณาคัดลอกด้วยตนเอง');
            });
        }
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'96dd1d2843df4b8f',t:'MTc1NDk3MTczMS4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
