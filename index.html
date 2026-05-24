<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>자동차 초음파 센서 혼선 및 보정 시뮬레이터</title>
    <!-- Tailwind CSS (Aesthetic Design) -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Chart.js (Professional Graphing on Coordinate Plane) -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <!-- FontAwesome (Clean Icons) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        physicsDark: '#0f172a',
                        physicsCard: '#1e293b',
                        accentBlue: '#38bdf8',
                        accentRed: '#f43f5e',
                        accentGreen: '#34d399',
                    }
                }
            }
        }
    </script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Pretendard:wght@400;600;700;800&display=swap');
        body {
            font-family: 'Pretendard', sans-serif;
            background-color: #0f172a;
        }
        /* 파동 애니메이션 효과 */
        @keyframes pulse-wave {
            0% { transform: scale(1); opacity: 0.8; }
            100% { transform: scale(3.5); opacity: 0; }
        }
        .sonar-wave {
            position: absolute;
            border: 2px solid;
            border-radius: 50%;
            animation: pulse-wave 1.5s infinite linear;
        }
    </style>
</head>
<body class="text-slate-100 min-h-screen p-4 md:p-8">

    <div class="max-w-6xl mx-auto space-y-6">
        
        <!-- Header Section -->
        <header class="text-center md:text-left flex flex-col md:flex-row items-center justify-between border-b border-slate-700 pb-6">
            <div>
                <span class="px-3 py-1 text-xs font-semibold bg-sky-500/20 text-sky-400 rounded-full border border-sky-500/30">고등학교 물리 I / II 수행평가</span>
                <h1 class="text-3xl md:text-4xl font-extrabold mt-2 tracking-tight">
                    초음파 센서 <span class="text-sky-400">신호 혼선(Crosstalk)</span> 탐구 시뮬레이터
                </h1>
                <p class="text-slate-400 mt-1">파동의 중첩 원리 이해와 소프트웨어적 시간차 제어를 통한 데이터 복구</p>
            </div>
            <div class="mt-4 md:mt-0 flex gap-3">
                <div class="bg-physicsCard border border-slate-700 px-4 py-2 rounded-lg text-sm text-center">
                    <span class="block text-xs text-slate-400">파동 속력 설정</span>
                    <span class="font-semibold text-sky-400">음속 v ≈ 340 m/s</span>
                </div>
            </div>
        </header>

        <!-- Main Interactive Workspace -->
        <div class="grid grid-cols-1 lg:grid-cols-12 gap-6">
            
            <!-- Left Side: Simulator (7 columns) -->
            <div class="lg:col-span-7 space-y-6">
                
                <!-- Card 1: Live Interactive Animation -->
                <div class="bg-physicsCard border border-slate-700 rounded-2xl p-6 shadow-xl relative overflow-hidden">
                    <div class="flex justify-between items-center mb-4">
                        <h2 class="text-lg font-bold flex items-center gap-2">
                            <i class="fa-solid fa-car text-sky-400"></i>
                            차량 접근 및 파동 간섭 애니메이션 (모의 실험)
                        </h2>
                        <span id="crosstalk-alert" class="px-2.5 py-1 text-xs font-bold rounded-md bg-emerald-500/10 text-emerald-400 border border-emerald-500/20">
                            신호 상태 양호
                        </span>
                    </div>

                    <!-- Road and Cars Box -->
                    <div class="bg-slate-950 h-44 rounded-xl relative overflow-hidden flex items-center border border-slate-800">
                        <!-- Road Lines -->
                        <div class="absolute inset-x-0 h-0.5 border-t-2 border-dashed border-slate-700"></div>

                        <!-- Left Car (Transmitter A) -->
                        <div id="car-left" class="absolute left-[10%] z-10 transition-all duration-100 ease-linear" style="transform: translateY(-50%); top: 50%;">
                            <div class="relative flex flex-col items-center">
                                <span class="text-xs bg-rose-500 text-white font-bold px-2 py-0.5 rounded shadow mb-1">차량 A</span>
                                <!-- SVG Stylish Car Left (Facing Right) -->
                                <svg class="w-24 h-12 text-rose-400 drop-shadow-[0_0_8px_rgba(244,63,94,0.5)]" viewBox="0 0 100 50" fill="currentColor">
                                    <path d="M15,30 L85,30 C90,30 95,25 95,20 L95,15 C95,10 85,5 70,5 L30,5 C15,5 5,10 5,15 L5,20 C5,25 10,30 15,30 Z" />
                                    <circle cx="25" cy="35" r="8" fill="#475569" stroke="#1e293b" stroke-width="2"/>
                                    <circle cx="75" cy="35" r="8" fill="#475569" stroke="#1e293b" stroke-width="2"/>
                                    <!-- Sensor indicator -->
                                    <rect x="92" y="12" width="6" height="8" rx="1" fill="#fff" class="animate-pulse"/>
                                </svg>
                                <!-- Sonar Wave Effect A -->
                                <div id="wave-a" class="sonar-wave absolute right-0 top-1/2 border-rose-500/60 w-4 h-4" style="margin-top: -8px; display: none;"></div>
                            </div>
                        </div>

                        <!-- Right Car (Transmitter B) -->
                        <div id="car-right" class="absolute right-[10%] z-10 transition-all duration-100 ease-linear" style="transform: translateY(-50%); top: 50%;">
                            <div class="relative flex flex-col items-center">
                                <span class="text-xs bg-sky-500 text-white font-bold px-2 py-0.5 rounded shadow mb-1">차량 B</span>
                                <!-- SVG Stylish Car Right (Facing Left) -->
                                <svg class="w-24 h-12 text-sky-400 drop-shadow-[0_0_8px_rgba(56,189,248,0.5)]" viewBox="0 0 100 50" fill="currentColor" style="transform: scaleX(-1);">
                                    <path d="M15,30 L85,30 C90,30 95,25 95,20 L95,15 C95,10 85,5 70,5 L30,5 C15,5 5,10 5,15 L5,20 C5,25 10,30 15,30 Z" />
                                    <circle cx="25" cy="35" r="8" fill="#475569" stroke="#1e293b" stroke-width="2"/>
                                    <circle cx="75" cy="35" r="8" fill="#475569" stroke="#1e293b" stroke-width="2"/>
                                    <!-- Sensor indicator -->
                                    <rect x="92" y="12" width="6" height="8" rx="1" fill="#fff" class="animate-pulse"/>
                                </svg>
                                <!-- Sonar Wave Effect B -->
                                <div id="wave-b" class="sonar-wave absolute left-0 top-1/2 border-sky-500/60 w-4 h-4" style="margin-top: -8px; display: none;"></div>
                            </div>
                        </div>

                        <!-- Central Intersection Warning -->
                        <div id="interference-zone" class="absolute inset-0 bg-rose-500/10 flex items-center justify-center opacity-0 transition-opacity duration-300 pointer-events-none">
                            <span class="text-xs font-bold text-rose-500 border border-rose-500/30 px-3 py-1.5 rounded-full bg-slate-950/90 animate-bounce">
                                <i class="fa-solid fa-triangle-exclamation mr-1"></i> 파동 간섭 및 중첩 영역 (혼선 유발 수신부 오류)
                            </span>
                        </div>
                    </div>

                    <!-- Simulation Info Bar -->
                    <div class="grid grid-cols-3 gap-2 mt-4 text-center">
                        <div class="bg-slate-900/60 p-2 rounded-lg border border-slate-800">
                            <span class="block text-xs text-slate-400">현재 실제 거리</span>
                            <span id="current-distance" class="text-lg font-bold text-sky-400">150 cm</span>
                        </div>
                        <div class="bg-slate-900/60 p-2 rounded-lg border border-slate-800">
                            <span class="block text-xs text-slate-400">차량 충돌 확률</span>
                            <span id="risk-factor" class="text-lg font-bold text-emerald-400">0%</span>
                        </div>
                        <div class="bg-slate-900/60 p-2 rounded-lg border border-slate-800">
                            <span class="block text-xs text-slate-400">LED 경보등</span>
                            <span id="warning-led" class="inline-block mt-1 w-4 h-4 rounded-full bg-emerald-500 shadow-[0_0_10px_rgba(16,185,129,0.6)]"></span>
                        </div>
                    </div>
                </div>

                <!-- Card 2: Interactive Controls -->
                <div class="bg-physicsCard border border-slate-700 rounded-2xl p-6 shadow-xl">
                    <h3 class="text-base font-bold mb-4 flex items-center gap-2">
                        <i class="fa-solid fa-sliders text-sky-400"></i>
                        시뮬레이션 조작 패널
                    </h3>
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <!-- Left Side: Controls -->
                        <div class="space-y-4">
                            <!-- Toggle Mode (The Core Physics Problem-Solving Switch) -->
                            <div>
                                <label class="block text-xs font-medium text-slate-400 mb-1.5">아두이노 소스코드 제어 필터</label>
                                <div class="grid grid-cols-2 gap-2 bg-slate-900 p-1 rounded-xl border border-slate-800">
                                    <button onclick="setCorrectionMode(false)" id="btn-mode-raw" class="py-2.5 rounded-lg text-sm font-bold transition-all bg-rose-500 text-white shadow-md">
                                        보정 전 (오작동)
                                    </button>
                                    <button onclick="setCorrectionMode(true)" id="btn-mode-fixed" class="py-2.5 rounded-lg text-sm font-bold transition-all text-slate-400 hover:text-white">
                                        보정 후 (정상 작동)
                                    </button>
                                </div>
                            </div>
                        </div>

                        <!-- Right Side: Action Buttons -->
                        <div class="flex flex-col justify-end gap-2">
                            <div class="grid grid-cols-2 gap-2">
                                <button onclick="toggleSimulation()" id="btn-play" class="bg-sky-500 hover:bg-sky-600 text-slate-950 font-bold py-3 px-4 rounded-xl transition-all shadow-lg shadow-sky-500/20 flex items-center justify-center gap-2">
                                    <i class="fa-solid fa-play"></i> 시뮬레이션 시작
                                </button>
                                <button onclick="resetSimulation()" class="bg-slate-700 hover:bg-slate-600 text-white font-semibold py-3 px-4 rounded-xl transition-all border border-slate-600 flex items-center justify-center gap-2">
                                    <i class="fa-solid fa-rotate-left"></i> 초기화
                                </button>
                            </div>
                        </div>
                    </div>
                </div>

            </div>

            <!-- Right Side: Professional Coordinate Plane Graph (5 columns) -->
            <div class="lg:col-span-5 space-y-6">
                
                <!-- Card 3: Coordinate Graph -->
                <div class="bg-physicsCard border border-slate-700 rounded-2xl p-6 shadow-xl flex flex-col justify-between">
                    <div>
                        <div class="flex justify-between items-center mb-1">
                            <h2 class="text-lg font-bold flex items-center gap-2">
                                <i class="fa-solid fa-chart-line text-sky-400"></i>
                                센서 수신 거리 측정 좌표평면
                            </h2>
                        </div>
                        <p class="text-xs text-slate-400 mb-4">X축: 수신 샘플 타임라인, Y축: 계산된 상대 물리적 거리 (cm)</p>
                    </div>

                    <!-- Real Canvas Graph -->
                    <div class="bg-slate-950 p-3 rounded-xl border border-slate-800 h-[280px] flex items-center justify-center">
                        <canvas id="realtimeChart" class="w-full h-full"></canvas>
                    </div>

                    <!-- Graph Legends & Insights -->
                    <div class="mt-4 text-xs space-y-2 border-t border-slate-800 pt-4">
                        <div class="flex justify-between items-center">
                            <div class="flex items-center gap-1.5">
                                <span class="w-3 h-0.5 bg-rose-500 inline-block"></span>
                                <span class="text-slate-300 font-medium">측정된 가공 데이터 (Raw Data)</span>
                            </div>
                            <span id="graph-deviation-text" class="text-rose-400 font-bold">오차 발생 가능</span>
                        </div>
                        <p class="text-slate-400 leading-relaxed">
                            <strong class="text-slate-300">물리적 원리:</strong> 두 센서의 측정 주기 불일치 및 공진으로 발생한 파동 중첩이 트리거 신호를 교란하여 거리 변동(Spike)이 일어납니다.
                        </p>
                    </div>
                </div>

            </div>

        </div>

        <!-- Bottom Tabs Section (Arduino Code & Physics Principles for Homework report) -->
        <div class="bg-physicsCard border border-slate-700 rounded-2xl p-6 shadow-xl">
            <div class="flex border-b border-slate-700 gap-4 mb-4">
                <button onclick="switchTab('tab-physics')" id="btn-tab-physics" class="pb-3 text-sm font-bold border-b-2 border-sky-400 text-sky-400 transition-all">
                    물리적 현상 분석 (보고서용 내용)
                </button>
                <button onclick="switchTab('tab-arduino')" id="btn-tab-arduino" class="pb-3 text-sm font-bold text-slate-400 hover:text-white transition-all">
                    아두이노 해결 코드 및 회로도
                </button>
            </div>

            <!-- Tab content 1: Physics Principles -->
            <div id="tab-physics" class="space-y-4">
                <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                    <div class="bg-slate-900/50 p-4 rounded-xl border border-slate-800">
                        <h4 class="font-bold text-sky-400 mb-2"><i class="fa-solid fa-wave-square mr-1"></i> 파동의 독립성과 중첩 원리</h4>
                        <p class="text-sm text-slate-300 leading-relaxed">
                            두 개의 초음파(음파)는 서로 마주 보고 진행하더라도 독립적으로 진행 방향을 유지합니다. 그러나 겹치는 순간, 파동의 매질 변위는 두 변위의 벡터 합과 같은 <strong>중첩 원리</strong>를 따릅니다.
                        </p>
                    </div>
                    <div class="bg-slate-900/50 p-4 rounded-xl border border-slate-800">
                        <h4 class="font-bold text-rose-400 mb-2"><i class="fa-solid fa-triangle-exclamation mr-1"></i> 센서 신호 혼선(Crosstalk)</h4>
                        <p class="text-sm text-slate-300 leading-relaxed">
                            차량 A에서 발사한 고유의 펄스 음파를 차량 B의 수신부(Echo)가 자신인 보낸 반사파로 착각하여 타이밍 연산을 조기 차단함으로써, 거리가 극도로 가깝거나(0) 비정상적인 값으로 측정되는 오류를 범하게 됩니다.
                        </p>
                    </div>
                    <div class="bg-slate-900/50 p-4 rounded-xl border border-slate-800">
                        <h4 class="font-bold text-emerald-400 mb-2"><i class="fa-solid fa-shield-halved mr-1"></i> 시간 분할 제어 (Multiplexing)</h4>
                        <p class="text-sm text-slate-300 leading-relaxed">
                            해결 방법은 간단합니다. 차량 A의 센서 동작 타이밍과 차량 B의 동작 타이밍 사이에 충분한 <strong>물리적 소멸 시간(지연, Delay)</strong>을 인위적으로 주어, 음파 잔여 에너지가 소멸한 뒤 신호를 발사하게 처리합니다.
                        </p>
                    </div>
                </div>
            </div>

            <!-- Tab content 2: Arduino Code -->
            <div id="tab-arduino" class="hidden space-y-4">
                <div class="bg-slate-900/90 p-4 rounded-xl border border-slate-800 font-mono text-xs overflow-x-auto text-emerald-400">
                    <span class="text-slate-400 block mb-2">// 아두이노 보정 코드 - 각 센서 발사 간격을 벌려 혼선을 원천 방지함</span>
<pre>
const int trigA = 2; // 차량 A 송신기 Trigger
const int echoA = 3; // 차량 A 수신기 Echo
const int trigB = 4; // 차량 B 송신기 Trigger
const int echoB = 5; // 차량 B 수신기 Echo
const int ledAlert = 13; // 충돌 알림 LED

void setup() {
  Serial.begin(9600);
  pinMode(trigA, OUTPUT); pinMode(echoA, INPUT);
  pinMode(trigB, OUTPUT); pinMode(echoB, INPUT);
  pinMode(ledAlert, OUTPUT);
}

void loop() {
  long durationA, distanceA;
  long durationB, distanceB;

  // --- 1. 차량 A 측정 실시 ---
  digitalWrite(trigA, LOW); delayMicroseconds(2);
  digitalWrite(trigA, HIGH); delayMicroseconds(10);
  digitalWrite(trigA, LOW);
  durationA = pulseIn(echoA, HIGH);
  distanceA = durationA * 0.034 / 2; // 거리 계산 공식

  // 💥 핵심 포인트: 차량 A의 초음파 에너지가 공기 중에서 완전히 소멸되도록 50ms 대기 (혼선 제거 필터)
  delay(50); 

  // --- 2. 차량 B 측정 실시 ---
  digitalWrite(trigB, LOW); delayMicroseconds(2);
  digitalWrite(trigB, HIGH); delayMicroseconds(10);
  digitalWrite(trigB, LOW);
  durationB = pulseIn(echoB, HIGH);
  distanceB = durationB * 0.034 / 2;

  // 컴퓨터 화면에 거리 전달
  Serial.print(distanceA);
  Serial.print(",");
  Serial.println(distanceB);

  // 물리적 안전 거리 진입 유무 판단 (30cm 이하 경보 활성화)
  if ((distanceA > 0 && distanceA < 30) || (distanceB > 0 && distanceB < 30)) {
    digitalWrite(ledAlert, HIGH); // 경보 켬
  } else {
    digitalWrite(ledAlert, LOW);  // 경보 끔
  }
  delay(100);
}
</pre>
                </div>
            </div>
        </div>

    </div>

    <!-- Scripting for Live Animation & Graphs -->
    <script>
        // Simulation Global State
        let isSimulating = false;
        let isCorrected = false; // Mode toggle: False = Raw(Uncorrected), True = Corrected
        let currentDistance = 150; // Starting physical distance in cm
        let timeStep = 0;
        let simInterval = null;
        let chartInstance = null;

        // Initialize Chart.js Graph
        function initChart() {
            const ctx = document.getElementById('realtimeChart').getContext('2d');
            chartInstance = new Chart(ctx, {
                type: 'line',
                data: {
                    labels: [], // Time series data (Time steps)
                    datasets: [{
                        label: '측정 거리 (cm)',
                        data: [],
                        borderColor: '#f43f5e', // Uncorrected Red
                        backgroundColor: 'rgba(244, 63, 94, 0.1)',
                        borderWidth: 3,
                        pointRadius: 2,
                        fill: true,
                        tension: 0.15
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    scales: {
                        x: {
                            grid: { color: 'rgba(255, 255, 255, 0.05)' },
                            title: { display: true, text: '샘플 주기 (Time Steps)', color: '#94a3b8' },
                            ticks: { color: '#94a3b8' }
                        },
                        y: {
                            min: 0,
                            max: 160,
                            grid: { color: 'rgba(255, 255, 255, 0.1)' },
                            title: { display: true, text: '거리 측정값 (cm)', color: '#94a3b8' },
                            ticks: { 
                                stepSize: 20,
                                color: '#94a3b8'
                            }
                        }
                    },
                    plugins: {
                        legend: { display: false }
                    }
                }
            });
        }

        // Start/Pause Toggle Simulation
        function toggleSimulation() {
            const playBtn = document.getElementById('btn-play');
            if (isSimulating) {
                // Pause simulation
                clearInterval(simInterval);
                isSimulating = false;
                playBtn.innerHTML = '<i class="fa-solid fa-play"></i> 시뮬레이션 시작';
                playBtn.className = playBtn.className.replace('bg-amber-500', 'bg-sky-500').replace('hover:bg-amber-600', 'hover:bg-sky-600');
                // Turn off waves
                document.getElementById('wave-a').style.display = 'none';
                document.getElementById('wave-b').style.display = 'none';
            } else {
                // Start simulation
                isSimulating = true;
                playBtn.innerHTML = '<i class="fa-solid fa-pause"></i> 일시 정지';
                playBtn.className = playBtn.className.replace('bg-sky-500', 'bg-amber-500').replace('hover:bg-sky-600', 'hover:bg-amber-600');
                
                // Show wave indicators
                document.getElementById('wave-a').style.display = 'block';
                document.getElementById('wave-b').style.display = 'block';

                simInterval = setInterval(runSimulationCycle, 150);
            }
        }

        // Running Simulation Algorithm
        function runSimulationCycle() {
            if (currentDistance <= 15) {
                // Terminate at close safety critical zone
                clearInterval(simInterval);
                isSimulating = false;
                document.getElementById('btn-play').innerHTML = '<i class="fa-solid fa-flag-checkered"></i> 종료 완료';
                document.getElementById('btn-play').disabled = true;
                document.getElementById('wave-a').style.display = 'none';
                document.getElementById('wave-b').style.display = 'none';
                return;
            }

            // Move cars toward each other
            currentDistance -= 1.5;
            timeStep++;

            // Update car DOM position
            // Starting from 10% on left and right, they meet near the center.
            const movementPercent = 10 + (150 - currentDistance) * 0.23; // Adjusted range mapping
            document.getElementById('car-left').style.left = `${movementPercent}%`;
            document.getElementById('car-right').style.right = `${movementPercent}%`;

            // Calculate measured distance
            let measuredVal = currentDistance;
            
            // Simulation physics logic for interference:
            if (!isCorrected) {
                // Under raw/uncorrected condition:
                // Interference occurs heavily when vehicles are closer than 80 cm, as waves collide and echo timers get false-triggered
                if (currentDistance < 80) {
                    document.getElementById('interference-zone').style.opacity = '1';
                    document.getElementById('crosstalk-alert').innerText = '⚠️ 상쇄간섭 및 혼선 감지';
                    document.getElementById('crosstalk-alert').className = 'px-2.5 py-1 text-xs font-bold rounded-md bg-rose-500/10 text-rose-400 border border-rose-500/20';

                    // Random spike modeling: simulating timer mismatch in HC-SR04
                    if (Math.random() < 0.35) {
                        // Sensor misreads distance either as 0 (echo triggered instantly) or 150 (timeout)
                        measuredVal = Math.random() > 0.5 ? 2.5 : 155; 
                    }
                } else {
                    document.getElementById('interference-zone').style.opacity = '0';
                    document.getElementById('crosstalk-alert').innerText = '신호 상태 양호';
                    document.getElementById('crosstalk-alert').className = 'px-2.5 py-1 text-xs font-bold rounded-md bg-emerald-500/10 text-emerald-400 border border-emerald-500/20';
                }
            } else {
                // Corrected mode (stable performance throughout)
                document.getElementById('interference-zone').style.opacity = '0';
                document.getElementById('crosstalk-alert').innerText = '🛡️ 시차 필터 보정중';
                document.getElementById('crosstalk-alert').className = 'px-2.5 py-1 text-xs font-bold rounded-md bg-sky-500/10 text-sky-400 border border-sky-500/20';
            }

            // Update safety LED indicators based on actual (and possibly faulty) measured value
            const led = document.getElementById('warning-led');
            if (measuredVal < 30) {
                // Danger
                led.className = 'inline-block mt-1 w-4 h-4 rounded-full bg-rose-500 shadow-[0_0_12px_rgba(244,63,94,0.8)] animate-ping';
                document.getElementById('risk-factor').innerText = '위험 (충돌)';
                document.getElementById('risk-factor').className = 'text-lg font-bold text-rose-400';
            } else if (measuredVal >= 30 && measuredVal < 80) {
                // Caution
                led.className = 'inline-block mt-1 w-4 h-4 rounded-full bg-amber-500 shadow-[0_0_10px_rgba(245,158,11,0.6)]';
                document.getElementById('risk-factor').innerText = '주의';
                document.getElementById('risk-factor').className = 'text-lg font-bold text-amber-400';
            } else {
                // Safe
                led.className = 'inline-block mt-1 w-4 h-4 rounded-full bg-emerald-500 shadow-[0_0_10px_rgba(16,185,129,0.6)]';
                document.getElementById('risk-factor').innerText = '안전';
                document.getElementById('risk-factor').className = 'text-lg font-bold text-emerald-400';
            }

            // Feed Data to Graphics Interface
            document.getElementById('current-distance').innerText = `${Math.round(measuredVal)} cm`;
            
            chartInstance.data.labels.push(timeStep);
            chartInstance.data.datasets[0].data.push(measuredVal);
            
            // Auto slide logic for chart to maintain visibility
            if (chartInstance.data.labels.length > 25) {
                chartInstance.data.labels.shift();
                chartInstance.data.datasets[0].data.shift();
            }
            chartInstance.update();
        }

        // Toggle Correction Filter Function (Changes UI and behavior instantly)
        function setCorrectionMode(corrected) {
            isCorrected = corrected;
            const btnRaw = document.getElementById('btn-mode-raw');
            const btnFixed = document.getElementById('btn-mode-fixed');
            
            if (corrected) {
                // Corrected Mode Active
                btnFixed.className = 'py-2.5 rounded-lg text-sm font-bold transition-all bg-sky-500 text-slate-950 shadow-md';
                btnRaw.className = 'py-2.5 rounded-lg text-sm font-bold transition-all text-slate-400 hover:text-white';
                chartInstance.data.datasets[0].borderColor = '#38bdf8'; // Blue
                chartInstance.data.datasets[0].backgroundColor = 'rgba(56, 189, 248, 0.1)';
                document.getElementById('graph-deviation-text').innerText = '오차 제거 완료';
                document.getElementById('graph-deviation-text').className = 'text-sky-400 font-bold';
            } else {
                // Raw Mode Active
                btnRaw.className = 'py-2.5 rounded-lg text-sm font-bold transition-all bg-rose-500 text-white shadow-md';
                btnFixed.className = 'py-2.5 rounded-lg text-sm font-bold transition-all text-slate-400 hover:text-white';
                chartInstance.data.datasets[0].borderColor = '#f43f5e'; // Red
                chartInstance.data.datasets[0].backgroundColor = 'rgba(244, 63, 94, 0.1)';
                document.getElementById('graph-deviation-text').innerText = '오차 발생 가능';
                document.getElementById('graph-deviation-text').className = 'text-rose-400 font-bold';
            }
            chartInstance.update();
        }

        // Reset Simulator
        function resetSimulation() {
            clearInterval(simInterval);
            isSimulating = false;
            currentDistance = 150;
            timeStep = 0;
            
            // Reset DOM UI elements
            document.getElementById('car-left').style.left = '10%';
            document.getElementById('car-right').style.right = '10%';
            document.getElementById('current-distance').innerText = '150 cm';
            document.getElementById('risk-factor').innerText = '안전';
            document.getElementById('risk-factor').className = 'text-lg font-bold text-emerald-400';
            document.getElementById('warning-led').className = 'inline-block mt-1 w-4 h-4 rounded-full bg-emerald-500 shadow-[0_0_10px_rgba(16,185,129,0.6)]';
            document.getElementById('interference-zone').style.opacity = '0';
            document.getElementById('crosstalk-alert').innerText = '신호 상태 양호';
            document.getElementById('crosstalk-alert').className = 'px-2.5 py-1 text-xs font-bold rounded-md bg-emerald-500/10 text-emerald-400 border border-emerald-500/20';

            const playBtn = document.getElementById('btn-play');
            playBtn.innerHTML = '<i class="fa-solid fa-play"></i> 시뮬레이션 시작';
            playBtn.disabled = false;
            playBtn.className = 'bg-sky-500 hover:bg-sky-600 text-slate-950 font-bold py-3 px-4 rounded-xl transition-all shadow-lg shadow-sky-500/20 flex items-center justify-center gap-2';

            document.getElementById('wave-a').style.display = 'none';
            document.getElementById('wave-b').style.display = 'none';

            // Clear Chart
            chartInstance.data.labels = [];
            chartInstance.data.datasets[0].data = [];
            chartInstance.update();
        }

        // Sub-tabs handling inside card
        function switchTab(tabId) {
            const tabPhysics = document.getElementById('tab-physics');
            const tabArduino = document.getElementById('tab-arduino');
            const btnPhysics = document.getElementById('btn-tab-physics');
            const btnArduino = document.getElementById('btn-tab-arduino');

            if (tabId === 'tab-physics') {
                tabPhysics.classList.remove('hidden');
                tabArduino.classList.add('hidden');
                btnPhysics.className = 'pb-3 text-sm font-bold border-b-2 border-sky-400 text-sky-400 transition-all';
                btnArduino.className = 'pb-3 text-sm font-bold text-slate-400 hover:text-white transition-all';
            } else {
                tabArduino.classList.remove('hidden');
                tabPhysics.classList.add('hidden');
                btnArduino.className = 'pb-3 text-sm font-bold border-b-2 border-sky-400 text-sky-400 transition-all';
                btnPhysics.className = 'pb-3 text-sm font-bold text-slate-400 hover:text-white transition-all';
            }
        }

        // Window onload initialization
        window.onload = function() {
            initChart();
        }
    </script>
</body>
</html>
