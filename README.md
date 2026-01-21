<html lang="th" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>คณิตศาสตร์การเงิน ป.5</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Prompt:wght@400;500;600;700&amp;display=swap" rel="stylesheet">
  <style>
    body {
      box-sizing: border-box;
    }
    * {
      font-family: 'Prompt', sans-serif;
    }
    .coin-bounce {
      animation: bounce 0.5s ease infinite alternate;
    }
    @keyframes bounce {
      from { transform: translateY(0); }
      to { transform: translateY(-8px); }
    }
    .correct-answer {
      animation: pulse-green 0.5s ease;
    }
    @keyframes pulse-green {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.05); }
    }
    .wrong-answer {
      animation: shake 0.5s ease;
    }
    @keyframes shake {
      0%, 100% { transform: translateX(0); }
      25% { transform: translateX(-10px); }
      75% { transform: translateX(10px); }
    }
    .fade-in {
      animation: fadeIn 0.3s ease;
    }
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .glass-card {
      background: rgba(255, 255, 255, 0.15);
      backdrop-filter: blur(12px);
      border: 1px solid rgba(255, 255, 255, 0.2);
      box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
    }
    .glass-card:hover {
      background: rgba(255, 255, 255, 0.25);
      border: 1px solid rgba(255, 255, 255, 0.3);
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
 </head>
 <body class="h-full">
  <div id="app" class="h-full w-full overflow-auto" style="background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);"><!-- หน้าหลัก -->
   <div id="home-screen" class="min-h-full p-4 md:p-8">
    <div class="max-w-4xl mx-auto"><!-- Header -->
     <div class="text-center mb-8">
      <div class="inline-flex items-center justify-center w-20 h-20 rounded-full mb-4" style="background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 100%); box-shadow: 0 8px 16px rgba(251, 191, 36, 0.4);">
       <svg class="w-12 h-12 coin-bounce" viewbox="0 0 24 24" fill="none"><circle cx="12" cy="12" r="10" fill="#fef3c7" /> <text x="12" y="16" text-anchor="middle" font-size="10" font-weight="bold" fill="#92400e">
         ฿
        </text>
       </svg>
      </div>
      <h1 id="app-title" class="text-3xl md:text-4xl font-bold mb-2" style="color: #ffffff; text-shadow: 0 2px 10px rgba(0,0,0,0.2);">คณิตศาสตร์การเงิน ป.5</h1>
      <p id="welcome-msg" class="text-lg" style="color: #fef3c7;">เลือกบทเรียนที่ต้องการฝึก</p>
      <div class="mt-4 inline-block px-4 py-2 rounded-lg glass-card">
       <p class="text-sm" style="color: #ffffff;">ผู้สร้าง: เด็กชาย ภัทรชนน พงษ์ญวน</p>
       <p class="text-xs" style="color: #fef3c7;">ชั้น ป.5 MEP</p>
      </div>
     </div><!-- Score Display -->
     <div class="flex justify-center gap-4 mb-8">
      <div class="px-6 py-3 rounded-xl glass-card"><span style="color: #ffffff;">คะแนนรวม: </span> <span id="total-score" class="font-bold text-xl" style="color: #fbbf24;">0</span>
      </div>
     </div><!-- Lesson Cards -->
     <div class="grid grid-cols-1 md:grid-cols-2 gap-6"><!-- บทที่ 1: รู้จักเงิน --> <button onclick="startLesson(1)" class="p-6 rounded-2xl text-left transition-all hover:scale-105 glass-card">
       <div class="flex items-center gap-4 mb-3">
        <div class="w-14 h-14 rounded-xl flex items-center justify-center" style="background: linear-gradient(135deg, #10b981 0%, #059669 100%); box-shadow: 0 4px 12px rgba(16, 185, 129, 0.3);"><span class="text-3xl">🪙</span>
        </div>
        <div>
         <h3 class="text-xl font-bold" style="color: #ffffff;">บทที่ 1</h3>
         <p class="font-semibold" style="color: #fef3c7;">รู้จักเงินไทย</p>
        </div>
       </div><p class="text-sm" style="color: rgba(255, 255, 255, 0.8);">เรียนรู้ค่าของธนบัตรและเหรียญ</p></button> <!-- บทที่ 2: การบวกเงิน --> <button onclick="startLesson(2)" class="p-6 rounded-2xl text-left transition-all hover:scale-105 glass-card">
       <div class="flex items-center gap-4 mb-3">
        <div class="w-14 h-14 rounded-xl flex items-center justify-center" style="background: linear-gradient(135deg, #3b82f6 0%, #2563eb 100%); box-shadow: 0 4px 12px rgba(59, 130, 246, 0.3);"><span class="text-3xl">➕</span>
        </div>
        <div>
         <h3 class="text-xl font-bold" style="color: #ffffff;">บทที่ 2</h3>
         <p class="font-semibold" style="color: #fef3c7;">การบวกเงิน</p>
        </div>
       </div><p class="text-sm" style="color: rgba(255, 255, 255, 0.8);">ฝึกรวมจำนวนเงิน</p></button> <!-- บทที่ 3: การลบเงิน --> <button onclick="startLesson(3)" class="p-6 rounded-2xl text-left transition-all hover:scale-105 glass-card">
       <div class="flex items-center gap-4 mb-3">
        <div class="w-14 h-14 rounded-xl flex items-center justify-center" style="background: linear-gradient(135deg, #f59e0b 0%, #d97706 100%); box-shadow: 0 4px 12px rgba(245, 158, 11, 0.3);"><span class="text-3xl">➖</span>
        </div>
        <div>
         <h3 class="text-xl font-bold" style="color: #ffffff;">บทที่ 3</h3>
         <p class="font-semibold" style="color: #fef3c7;">การลบเงิน</p>
        </div>
       </div><p class="text-sm" style="color: rgba(255, 255, 255, 0.8);">ฝึกหาเงินทอน</p></button> <!-- บทที่ 4: โจทย์ปัญหา --> <button onclick="startLesson(4)" class="p-6 rounded-2xl text-left transition-all hover:scale-105 glass-card">
       <div class="flex items-center gap-4 mb-3">
        <div class="w-14 h-14 rounded-xl flex items-center justify-center" style="background: linear-gradient(135deg, #ec4899 0%, #db2777 100%); box-shadow: 0 4px 12px rgba(236, 72, 153, 0.3);"><span class="text-3xl">🧮</span>
        </div>
        <div>
         <h3 class="text-xl font-bold" style="color: #ffffff;">บทที่ 4</h3>
         <p class="font-semibold" style="color: #fef3c7;">โจทย์ปัญหา</p>
        </div>
       </div><p class="text-sm" style="color: rgba(255, 255, 255, 0.8);">แก้ปัญหาเรื่องเงินในชีวิตจริง</p></button>
     </div>
    </div>
   </div><!-- หน้าแบบฝึกหัด -->
   <div id="quiz-screen" class="min-h-full p-4 md:p-8 hidden">
    <div class="max-w-2xl mx-auto"><!-- Header -->
     <div class="flex items-center justify-between mb-6"><button onclick="goHome()" class="flex items-center gap-2 px-4 py-2 rounded-lg transition-colors glass-card" style="color: #ffffff;">
       <svg class="w-5 h-5" fill="none" stroke="currentColor" viewbox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
       </svg> กลับ </button>
      <div class="px-4 py-2 rounded-lg glass-card"><span style="color: #ffffff;">ข้อ </span> <span id="current-q" class="font-bold" style="color: #fbbf24;">1</span> <span style="color: #ffffff;"> / </span> <span id="total-q" style="color: #ffffff;">5</span>
      </div>
     </div><!-- Progress Bar -->
     <div class="h-3 rounded-full mb-8 overflow-hidden" style="background: rgba(255, 255, 255, 0.2);">
      <div id="progress-bar" class="h-full rounded-full transition-all duration-500" style="background: linear-gradient(90deg, #fbbf24 0%, #f59e0b 100%); width: 0%;"></div>
     </div><!-- Question Card -->
     <div id="question-card" class="rounded-2xl p-6 md:p-8 fade-in glass-card">
      <div id="lesson-badge" class="inline-block px-3 py-1 rounded-full text-sm font-medium mb-4" style="background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 100%); color: #ffffff; box-shadow: 0 2px 8px rgba(251, 191, 36, 0.3);">
       บทที่ 1
      </div>
      <h2 id="question-text" class="text-xl md:text-2xl font-semibold mb-6" style="color: #ffffff;">คำถามจะแสดงที่นี่</h2><!-- Money Display -->
      <div id="money-display" class="flex flex-wrap gap-3 justify-center mb-6 p-4 rounded-xl" style="background: rgba(255, 255, 255, 0.1);">
      </div><!-- Answer Options -->
      <div id="answer-options" class="grid grid-cols-2 gap-4">
      </div><!-- Input Answer -->
      <div id="input-answer" class="hidden">
       <div class="flex gap-3"><input type="number" id="answer-input" class="flex-1 px-4 py-3 rounded-xl text-xl text-center font-bold outline-none glass-card" style="color: #ffffff;" placeholder="พิมพ์คำตอบ"> <button onclick="checkInputAnswer()" class="px-6 py-3 rounded-xl font-bold transition-colors" style="background: linear-gradient(135deg, #10b981 0%, #059669 100%); color: #ffffff; box-shadow: 0 4px 12px rgba(16, 185, 129, 0.3);"> ตรวจ </button>
       </div>
      </div>
     </div><!-- Feedback -->
     <div id="feedback" class="hidden mt-6 p-6 rounded-2xl text-center fade-in">
      <div id="feedback-icon" class="text-5xl mb-3"></div>
      <p id="feedback-text" class="text-xl font-semibold mb-2"></p>
      <p id="feedback-explain" class="text-sm mb-4" style="color: rgba(255, 255, 255, 0.9);"></p><button onclick="nextQuestion()" id="next-btn" class="px-8 py-3 rounded-xl font-bold transition-colors" style="background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 100%); color: #ffffff; box-shadow: 0 4px 12px rgba(251, 191, 36, 0.3);"> ข้อถัดไป </button>
     </div>
    </div>
   </div><!-- หน้าผลลัพธ์ -->
   <div id="result-screen" class="min-h-full p-4 md:p-8 hidden">
    <div class="max-w-md mx-auto text-center">
     <div class="rounded-2xl p-8 glass-card">
      <div class="text-6xl mb-4">
       🎉
      </div>
      <h2 class="text-2xl font-bold mb-2" style="color: #ffffff;">จบบทเรียน!</h2>
      <p class="mb-6" style="color: #fef3c7;">คุณทำแบบฝึกหัดครบแล้ว</p>
      <div class="p-6 rounded-xl mb-6" style="background: rgba(255, 255, 255, 0.1);">
       <p style="color: #fef3c7;">คะแนนที่ได้</p>
       <p class="text-4xl font-bold" style="color: #fbbf24;"><span id="lesson-score">0</span>/<span id="lesson-total">5</span></p>
      </div>
      <div id="result-stars" class="flex justify-center gap-2 mb-6 text-4xl">
      </div>
      <div class="grid grid-cols-2 gap-4"><button onclick="restartLesson()" class="px-4 py-3 rounded-xl font-bold transition-colors" style="background: linear-gradient(135deg, #3b82f6 0%, #2563eb 100%); color: #ffffff; box-shadow: 0 4px 12px rgba(59, 130, 246, 0.3);"> เล่นอีกครั้ง </button> <button onclick="goHome()" class="px-4 py-3 rounded-xl font-bold transition-colors" style="background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 100%); color: #ffffff; box-shadow: 0 4px 12px rgba(251, 191, 36, 0.3);"> หน้าหลัก </button>
      </div>
     </div>
    </div>
   </div>
  </div>
  <script>
    // Default config
    const defaultConfig = {
      app_title: 'คณิตศาสตร์การเงิน ป.5',
      welcome_message: 'เลือกบทเรียนที่ต้องการฝึก',
      primary_color: '#ffffff',
      secondary_color: '#fef3c7',
      text_color: '#ffffff',
      accent_color: '#fbbf24',
      bg_gradient_start: '#667eea',
      bg_gradient_end: '#f093fb'
    };

    let config = { ...defaultConfig };

    // Game state
    let currentLesson = 1;
    let currentQuestion = 0;
    let score = 0;
    let totalScore = 0;
    let questions = [];

    // Money data
    const moneyValues = [
      { value: 1000, name: 'ธนบัตร 1000', emoji: '💵', color: '#8b5cf6' },
      { value: 500, name: 'ธนบัตร 500', emoji: '💵', color: '#a78bfa' },
      { value: 100, name: 'ธนบัตร 100', emoji: '💵', color: '#ef4444' },
      { value: 50, name: 'ธนบัตร 50', emoji: '💵', color: '#3b82f6' },
      { value: 20, name: 'ธนบัตร 20', emoji: '💵', color: '#10b981' },
      { value: 10, name: 'เหรียญ 10', emoji: '🪙', color: '#fbbf24' },
      { value: 5, name: 'เหรียญ 5', emoji: '🪙', color: '#d1d5db' },
      { value: 2, name: 'เหรียญ 2', emoji: '🪙', color: '#f59e0b' },
      { value: 1, name: 'เหรียญ 1', emoji: '🪙', color: '#9ca3af' },
      { value: 0.5, name: 'เหรียญ 50 สต.', emoji: '🪙', color: '#f59e0b' },
      { value: 0.25, name: 'เหรียญ 25 สต.', emoji: '🪙', color: '#9ca3af' }
    ];

    // Generate questions based on lesson
    function generateQuestions(lesson) {
      const qs = [];
      
      if (lesson === 1) {
        const items = [
          { money: [1000], answer: 1000 },
          { money: [500], answer: 500 },
          { money: [100, 100], answer: 200 },
          { money: [50, 20], answer: 70 },
          { money: [10, 5, 2], answer: 17 }
        ];
        items.forEach((item, i) => {
          qs.push({
            type: 'choice',
            question: 'จำนวนเงินทั้งหมดเท่ากับเท่าไร?',
            money: item.money,
            answer: item.answer,
            options: generateOptions(item.answer)
          });
        });
      } else if (lesson === 2) {
        const problems = [
          { a: 150, b: 75, text: 'มีเงิน 150 บาท ได้รับเพิ่ม 75 บาท รวมมีเงินเท่าไร?' },
          { a: 250, b: 180, text: 'พ่อให้เงิน 250 บาท แม่ให้ 180 บาท รวมได้เท่าไร?' },
          { a: 320, b: 95, text: 'ออมเงินได้ 320 บาท ได้ค่าขนม 95 บาท รวมมีเท่าไร?' },
          { a: 500, b: 275, text: 'มีเงิน 500 บาท ขายของได้ 275 บาท รวมมีเท่าไร?' },
          { a: 1250, b: 380, text: 'มีเงิน 1,250 บาท ได้รับ 380 บาท รวมเท่าไร?' }
        ];
        problems.forEach(p => {
          qs.push({
            type: 'input',
            question: p.text,
            money: [],
            answer: p.a + p.b
          });
        });
      } else if (lesson === 3) {
        const problems = [
          { paid: 100, cost: 45, text: 'ซื้อขนม 45 บาท จ่าย 100 บาท ได้เงินทอนเท่าไร?' },
          { paid: 200, cost: 85, text: 'ซื้อหนังสือ 85 บาท จ่าย 200 บาท ได้เงินทอนเท่าไร?' },
          { paid: 500, cost: 235, text: 'ซื้อของเล่น 235 บาท จ่าย 500 บาท ได้เงินทอนเท่าไร?' },
          { paid: 1000, cost: 650, text: 'ซื้อรองเท้า 650 บาท จ่าย 1,000 บาท ได้เงินทอนเท่าไร?' },
          { paid: 500, cost: 127, text: 'ซื้ออาหาร 127 บาท จ่าย 500 บาท ได้เงินทอนเท่าไร?' }
        ];
        problems.forEach(p => {
          qs.push({
            type: 'input',
            question: p.text,
            money: [],
            answer: p.paid - p.cost
          });
        });
      } else if (lesson === 4) {
        const problems = [
          { q: 'น้องมีเงิน 500 บาท ซื้อสมุด 35 บาท ซื้อดินสอ 15 บาท เหลือเงินเท่าไร?', a: 450 },
          { q: 'แม่ให้เงิน 200 บาท พ่อให้ 150 บาท ซื้อขนม 80 บาท เหลือเงินเท่าไร?', a: 270 },
          { q: 'มีเงิน 1,000 บาท ซื้อเสื้อ 350 บาท ซื้อกางเกง 420 บาท เหลือเงินเท่าไร?', a: 230 },
          { q: 'ออมเงินวันละ 25 บาท ออม 4 วัน รวมเป็นเงินเท่าไร?', a: 100 },
          { q: 'มีเงิน 800 บาท ได้รับ 250 บาท ใช้ไป 175 บาท เหลือเงินเท่าไร?', a: 875 }
        ];
        problems.forEach(p => {
          qs.push({
            type: 'input',
            question: p.q,
            money: [],
            answer: p.a
          });
        });
      }
      
      return qs;
    }

    function generateOptions(correct) {
      const opts = [correct];
      while (opts.length < 4) {
        const offset = Math.floor(Math.random() * 50) - 25;
        const opt = correct + offset;
        if (opt > 0 && !opts.includes(opt)) {
          opts.push(opt);
        }
      }
      return opts.sort(() => Math.random() - 0.5);
    }

    function startLesson(lesson) {
      currentLesson = lesson;
      currentQuestion = 0;
      score = 0;
      questions = generateQuestions(lesson);
      
      document.getElementById('home-screen').classList.add('hidden');
      document.getElementById('quiz-screen').classList.remove('hidden');
      document.getElementById('result-screen').classList.add('hidden');
      
      updateLessonBadge();
      showQuestion();
    }

    function updateLessonBadge() {
      const badge = document.getElementById('lesson-badge');
      const gradients = [
        'linear-gradient(135deg, #10b981 0%, #059669 100%)',
        'linear-gradient(135deg, #3b82f6 0%, #2563eb 100%)',
        'linear-gradient(135deg, #f59e0b 0%, #d97706 100%)',
        'linear-gradient(135deg, #ec4899 0%, #db2777 100%)'
      ];
      const names = ['รู้จักเงินไทย', 'การบวกเงิน', 'การลบเงิน', 'โจทย์ปัญหา'];
      badge.textContent = `บทที่ ${currentLesson}: ${names[currentLesson - 1]}`;
      badge.style.background = gradients[currentLesson - 1];
    }

    function showQuestion() {
      const q = questions[currentQuestion];
      document.getElementById('current-q').textContent = currentQuestion + 1;
      document.getElementById('total-q').textContent = questions.length;
      document.getElementById('progress-bar').style.width = `${(currentQuestion / questions.length) * 100}%`;
      document.getElementById('question-text').textContent = q.question;
      document.getElementById('feedback').classList.add('hidden');
      
      const moneyDisplay = document.getElementById('money-display');
      if (q.money && q.money.length > 0) {
        moneyDisplay.classList.remove('hidden');
        moneyDisplay.innerHTML = q.money.map(val => {
          const m = moneyValues.find(v => v.value === val);
          return `<div class="flex flex-col items-center p-3 rounded-xl" style="background: rgba(255, 255, 255, 0.2); backdrop-filter: blur(8px); border: 2px solid ${m.color};">
            <span class="text-2xl">${m.emoji}</span>
            <span class="text-sm font-bold" style="color: #ffffff;">${val >= 1 ? val + ' บาท' : val * 100 + ' สต.'}</span>
          </div>`;
        }).join('');
      } else {
        moneyDisplay.classList.add('hidden');
      }
      
      const optionsDiv = document.getElementById('answer-options');
      const inputDiv = document.getElementById('input-answer');
      
      if (q.type === 'choice') {
        optionsDiv.classList.remove('hidden');
        inputDiv.classList.add('hidden');
        optionsDiv.innerHTML = q.options.map(opt => `
          <button onclick="checkAnswer(${opt})" class="p-4 rounded-xl text-lg font-bold transition-all hover:scale-105" style="background: rgba(255, 255, 255, 0.2); backdrop-filter: blur(8px); color: #ffffff; border: 2px solid rgba(255, 255, 255, 0.3);">
            ${opt} บาท
          </button>
        `).join('');
      } else {
        optionsDiv.classList.add('hidden');
        inputDiv.classList.remove('hidden');
        document.getElementById('answer-input').value = '';
        document.getElementById('answer-input').focus();
      }
      
      const card = document.getElementById('question-card');
      card.classList.remove('fade-in');
      void card.offsetWidth;
      card.classList.add('fade-in');
    }

    function checkAnswer(selected) {
      const q = questions[currentQuestion];
      const isCorrect = selected === q.answer;
      showFeedback(isCorrect, q.answer);
    }

    function checkInputAnswer() {
      const input = document.getElementById('answer-input');
      const q = questions[currentQuestion];
      const answer = parseFloat(input.value);
      const isCorrect = answer === q.answer;
      showFeedback(isCorrect, q.answer);
    }

    function showFeedback(isCorrect, correctAnswer) {
      const feedback = document.getElementById('feedback');
      const icon = document.getElementById('feedback-icon');
      const text = document.getElementById('feedback-text');
      const explain = document.getElementById('feedback-explain');
      const card = document.getElementById('question-card');
      
      if (isCorrect) {
        score++;
        totalScore++;
        document.getElementById('total-score').textContent = totalScore;
        feedback.style.background = 'linear-gradient(135deg, #10b981 0%, #059669 100%)';
        feedback.style.boxShadow = '0 4px 12px rgba(16, 185, 129, 0.3)';
        icon.textContent = '🎉';
        text.textContent = 'ถูกต้อง!';
        text.style.color = '#ffffff';
        explain.textContent = 'เก่งมาก!';
        card.classList.add('correct-answer');
      } else {
        feedback.style.background = 'linear-gradient(135deg, #ec4899 0%, #db2777 100%)';
        feedback.style.boxShadow = '0 4px 12px rgba(236, 72, 153, 0.3)';
        icon.textContent = '😢';
        text.textContent = 'ไม่ถูกต้อง';
        text.style.color = '#ffffff';
        explain.textContent = `คำตอบที่ถูกคือ ${correctAnswer} บาท`;
        card.classList.add('wrong-answer');
      }
      
      feedback.classList.remove('hidden');
      feedback.classList.add('fade-in');
      
      setTimeout(() => {
        card.classList.remove('correct-answer', 'wrong-answer');
      }, 500);
      
      const nextBtn = document.getElementById('next-btn');
      if (currentQuestion >= questions.length - 1) {
        nextBtn.textContent = 'ดูผลลัพธ์';
      } else {
        nextBtn.textContent = 'ข้อถัดไป';
      }
    }

    function nextQuestion() {
      currentQuestion++;
      if (currentQuestion >= questions.length) {
        showResults();
      } else {
        showQuestion();
      }
    }

    function showResults() {
      document.getElementById('quiz-screen').classList.add('hidden');
      document.getElementById('result-screen').classList.remove('hidden');
      
      document.getElementById('lesson-score').textContent = score;
      document.getElementById('lesson-total').textContent = questions.length;
      
      const starsDiv = document.getElementById('result-stars');
      const starCount = Math.ceil((score / questions.length) * 3);
      starsDiv.innerHTML = '';
      for (let i = 0; i < 3; i++) {
        starsDiv.innerHTML += `<span style="color: ${i < starCount ? '#fbbf24' : 'rgba(255, 255, 255, 0.3)'}; filter: drop-shadow(0 2px 4px rgba(0,0,0,0.2));">⭐</span>`;
      }
    }

    function restartLesson() {
      startLesson(currentLesson);
    }

    function goHome() {
      document.getElementById('home-screen').classList.remove('hidden');
      document.getElementById('quiz-screen').classList.add('hidden');
      document.getElementById('result-screen').classList.add('hidden');
    }

    document.addEventListener('DOMContentLoaded', () => {
      const answerInput = document.getElementById('answer-input');
      if (answerInput) {
        answerInput.addEventListener('keypress', (e) => {
          if (e.key === 'Enter') {
            checkInputAnswer();
          }
        });
      }
    });

    // Element SDK integration
    function onConfigChange(cfg) {
      config = { ...defaultConfig, ...cfg };
      
      const titleEl = document.getElementById('app-title');
      if (titleEl) {
        titleEl.textContent = config.app_title || defaultConfig.app_title;
        titleEl.style.color = config.primary_color || defaultConfig.primary_color;
      }
      
      const welcomeEl = document.getElementById('welcome-msg');
      if (welcomeEl) {
        welcomeEl.textContent = config.welcome_message || defaultConfig.welcome_message;
        welcomeEl.style.color = config.secondary_color || defaultConfig.secondary_color;
      }
    }

    function mapToCapabilities(cfg) {
      return {
        recolorables: [
          {
            get: () => cfg.bg_gradient_start || defaultConfig.bg_gradient_start,
            set: (value) => {
              cfg.bg_gradient_start = value;
              if (window.elementSdk) window.elementSdk.setConfig({ bg_gradient_start: value });
            }
          },
          {
            get: () => cfg.bg_gradient_end || defaultConfig.bg_gradient_end,
            set: (value) => {
              cfg.bg_gradient_end = value;
              if (window.elementSdk) window.elementSdk.setConfig({ bg_gradient_end: value });
            }
          },
          {
            get: () => cfg.text_color || defaultConfig.text_color,
            set: (value) => {
              cfg.text_color = value;
              if (window.elementSdk) window.elementSdk.setConfig({ text_color: value });
            }
          },
          {
            get: () => cfg.primary_color || defaultConfig.primary_color,
            set: (value) => {
              cfg.primary_color = value;
              if (window.elementSdk) window.elementSdk.setConfig({ primary_color: value });
            }
          },
          {
            get: () => cfg.accent_color || defaultConfig.accent_color,
            set: (value) => {
              cfg.accent_color = value;
              if (window.elementSdk) window.elementSdk.setConfig({ accent_color: value });
            }
          }
        ],
        borderables: [],
        fontEditable: undefined,
        fontSizeable: undefined
      };
    }

    function mapToEditPanelValues(cfg) {
      return new Map([
        ['app_title', cfg.app_title || defaultConfig.app_title],
        ['welcome_message', cfg.welcome_message || defaultConfig.welcome_message]
      ]);
    }

    if (window.elementSdk) {
      window.elementSdk.init({
        defaultConfig,
        onConfigChange,
        mapToCapabilities,
        mapToEditPanelValues
      });
    }
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9c1352028185731c',t:'MTc2ODk2MTkwMC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
