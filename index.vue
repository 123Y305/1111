<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>🎄圣诞祝福🎄</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'PingFang SC', 'Microsoft YaHei', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #1a2a3a 0%, #0d1520 100%);
            color: #fff;
            min-height: 100vh;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 500px;
            width: 100%;
            background: rgba(255, 255, 255, 0.08);
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
            overflow: hidden;
        }
        
        .snowflake {
            position: absolute;
            color: rgba(255, 255, 255, 0.8);
            font-size: 20px;
            animation: fall linear infinite;
            z-index: 0;
        }
        
        @keyframes fall {
            to {
                transform: translateY(100vh) rotate(360deg);
            }
        }
        
        .header {
            text-align: center;
            margin-bottom: 30px;
            position: relative;
            z-index: 1;
        }
        
        h1 {
            font-size: 28px;
            color: #FFD700;
            text-shadow: 0 0 10px rgba(255, 215, 0, 0.5);
            margin-bottom: 10px;
            background: linear-gradient(90deg, #FFD700, #FFA500, #FF6347);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .subtitle {
            font-size: 16px;
            color: #b0c4de;
            margin-bottom: 20px;
        }
        
        .step {
            display: none;
            position: relative;
            z-index: 1;
        }
        
        .step.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .question {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 20px;
            margin-bottom: 20px;
        }
        
        h2 {
            font-size: 20px;
            margin-bottom: 15px;
            color: #7fffd4;
        }
        
        .options {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }
        
        .option {
            background: rgba(255, 255, 255, 0.15);
            border: none;
            border-radius: 10px;
            padding: 15px;
            color: white;
            font-size: 16px;
            text-align: left;
            cursor: pointer;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .option:hover {
            background: rgba(255, 255, 255, 0.25);
            transform: translateY(-2px);
        }
        
        .option.selected {
            background: rgba(46, 204, 113, 0.3);
            border: 2px solid #2ecc71;
        }
        
        .next-btn {
            display: block;
            width: 100%;
            background: linear-gradient(90deg, #FF416C, #FF4B2B);
            border: none;
            border-radius: 10px;
            padding: 18px;
            color: white;
            font-size: 18px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 20px;
            box-shadow: 0 5px 15px rgba(255, 65, 108, 0.4);
        }
        
        .next-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(255, 65, 108, 0.6);
        }
        
        .next-btn:disabled {
            background: #666;
            cursor: not-allowed;
            transform: none;
            box-shadow: none;
        }
        
        .result {
            text-align: center;
            padding: 20px;
        }
        
        .result-icon {
            font-size: 70px;
            margin-bottom: 20px;
            animation: bounce 1s infinite alternate;
        }
        
        @keyframes bounce {
            from { transform: translateY(0); }
            to { transform: translateY(-15px); }
        }
        
        .result-text {
            font-size: 22px;
            margin-bottom: 15px;
            line-height: 1.5;
        }
        
        .result-desc {
            font-size: 16px;
            color: #b0c4de;
            line-height: 1.6;
            margin-bottom: 25px;
        }
        
        .share-btn {
            background: linear-gradient(90deg, #1E90FF, #00BFFF);
            border: none;
            border-radius: 10px;
            padding: 15px 25px;
            color: white;
            font-size: 16px;
            cursor: pointer;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            box-shadow: 0 5px 15px rgba(30, 144, 255, 0.4);
        }
        
        .share-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(30, 144, 255, 0.6);
        }
        
        .progress-bar {
            height: 6px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 3px;
            margin-bottom: 25px;
            overflow: hidden;
        }
        
        .progress {
            height: 100%;
            background: linear-gradient(90deg, #FFD700, #FFA500);
            border-radius: 3px;
            width: 0%;
            transition: width 0.5s ease;
        }
        
        .footer {
            text-align: center;
            margin-top: 30px;
            font-size: 14px;
            color: #888;
            position: relative;
            z-index: 1;
        }
        
        .loading {
            text-align: center;
            padding: 40px 20px;
        }
        
        .spinner {
            border: 5px solid rgba(255, 255, 255, 0.1);
            border-top: 5px solid #FFD700;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            animation: spin 1s linear infinite;
            margin: 0 auto 20px;
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        @media (max-width: 480px) {
            .container {
                padding: 20px;
            }
            
            h1 {
                font-size: 24px;
            }
            
            .result-icon {
                font-size: 60px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- 雪花效果 -->
        <div id="snowflakes-container"></div>
        
        <div class="header">
            <h1><i class="fas fa-tree"></i> 圣诞节祝福 <i class="fas fa-gift"></i></h1>
            <p class="subtitle">测测你的圣诞老人会给你带来什么礼物？</p>
            <div class="progress-bar">
                <div class="progress" id="progress"></div>
            </div>
        </div>
        
        <!-- 步骤1：开始页面 -->
        <div class="step active" id="step1">
            <div class="question">
                <h2>欢迎参加圣诞祝福！</h2>
                <p style="line-height: 1.6; margin-bottom: 15px;">这是一份特别的圣诞祝福，通过几个简单问题，我们将为你生成专属的圣诞祝福和礼物预测！</p>
                <p style="line-height: 1.6; color: #FFD700;">温馨提示：请确保周围环境安全，本包含惊喜元素！</p>
            </div>
            <button class="next-btn" id="startBtn">开始 <i class="fas fa-play"></i></button>
        </div>
        
        <!-- 步骤2：问题1 -->
        <div class="step" id="step2">
            <div class="question">
                <h2>问题1：你认为圣诞节最重要的是什么？</h2>
                <div class="options">
                    <button class="option" data-value="family">与家人团聚的温馨时刻</button>
                    <button class="option" data-value="gift">收到惊喜礼物的快乐</button>
                    <button class="option" data-value="food">享受丰盛的圣诞大餐</button>
                    <button class="option" data-value="love">传递爱与祝福的氛围</button>
                </div>
            </div>
            <button class="next-btn" id="nextBtn1" disabled>下一题 <i class="fas fa-arrow-right"></i></button>
        </div>
        
        <!-- 步骤3：问题2 -->
        <div class="step" id="step3">
            <div class="question">
                <h2>问题2：你希望圣诞老人送你什么礼物？</h2>
                <div class="options">
                    <button class="option" data-value="tech">最新科技产品</button>
                    <button class="option" data-value="travel">一次梦幻旅行</button>
                    <button class="option" data-value="money">实实在在的金钱</button>
                    <button class="option" data-value="health">健康与平安</button>
                </div>
            </div>
            <button class="next-btn" id="nextBtn2" disabled>下一题 <i class="fas fa-arrow-right"></i></button>
        </div>
        
        <!-- 步骤4：问题3 -->
        <div class="step" id="step4">
            <div class="question">
                <h2>问题3：圣诞节你最想和谁一起过？</h2>
                <div class="options">
                    <button class="option" data-value="family">家人</button>
                    <button class="option" data-value="friend">朋友</button>
                    <button class="option" data-value="lover">爱人</button>
                    <button class="option" data-value="alone">独自享受宁静</button>
                </div>
            </div>
            <button class="next-btn" id="nextBtn3" disabled>查看结果 <i class="fas fa-gift"></i></button>
        </div>
        
        <!-- 步骤5：加载页面 -->
        <div class="step" id="step5">
            <div class="loading">
                <div class="spinner"></div>
                <h2>正在分析你的答案...</h2>
                <p>圣诞老人正在查看你的愿望清单</p>
                <p id="loading-text" style="margin-top: 20px; font-style: italic; color: #FFD700;">检测到强烈的好运信号！</p>
            </div>
        </div>
        
        <!-- 步骤6：整蛊结果页面 -->
        <div class="step" id="step6">
            <div class="result">
                <div class="result-icon">🎅</div>
                <h2 class="result-text">恭喜！圣诞老人特别关注了你！</h2>
                <div class="result-desc">
                    <p>根据你的回答，圣诞老人决定给你一份<strong style="color:#FFD700;">特别大礼</strong>！</p>
                    <p>但领取前需要完成一个小任务：</p>
                    <p style="margin-top: 15px; font-size: 18px; color: #FF6347;">对着手机大声说三遍<br>"小郑同学最美丽！"</p>
                    <p style="margin-top: 15px;">（放心，我们不会真的录音，但周围人可能会用奇怪的眼神看你哦😜）</p>
                </div>
                <button class="share-btn" id="shareBtn">
                    <i class="fas fa-share-alt"></i> 分享给朋友一起玩
                </button>
            </div>
        </div>
        
        <div class="footer">
            <p>🎄 圣诞快乐！此内容仅供娱乐 🎄</p>
            <p style="font-size: 12px; margin-top: 5px;">设计目标：在节日中带来欢乐笑声</p>
        </div>
    </div>

    <script>
        // 创建雪花效果
        function createSnowflakes() {
            const container = document.getElementById('snowflakes-container');
            const snowflakeCount = 25;
            
            for (let i = 0; i < snowflakeCount; i++) {
                const snowflake = document.createElement('div');
                snowflake.classList.add('snowflake');
                snowflake.innerHTML = '❄';
                
                // 随机大小
                const size = Math.random() * 15 + 10;
                snowflake.style.fontSize = `${size}px`;
                
                // 随机起始位置
                const startX = Math.random() * 100;
                const startY = Math.random() * -20;
                snowflake.style.left = `${startX}vw`;
                snowflake.style.top = `${startY}px`;
                
                // 随机动画时长
                const duration = Math.random() * 10 + 10;
                snowflake.style.animationDuration = `${duration}s`;
                
                // 随机动画延迟
                const delay = Math.random() * 5;
                snowflake.style.animationDelay = `${delay}s`;
                
                container.appendChild(snowflake);
            }
        }
        
        // 初始化
        document.addEventListener('DOMContentLoaded', function() {
            createSnowflakes();
            
            // 获取DOM元素
            const startBtn = document.getElementById('startBtn');
            const nextBtn1 = document.getElementById('nextBtn1');
            const nextBtn2 = document.getElementById('nextBtn2');
            const nextBtn3 = document.getElementById('nextBtn3');
            const shareBtn = document.getElementById('shareBtn');
            const progressBar = document.getElementById('progress');
            const loadingText = document.getElementById('loading-text');
            
            const steps = document.querySelectorAll('.step');
            let currentStep = 1;
            const totalSteps = 6;
            
            const answers = {};
            const loadingMessages = [
                "正在检查你的圣诞袜尺寸...",
                "驯鹿们正在准备起飞...",
                "圣诞老人正在打包礼物...",
                "检测到强烈的好运信号！",
                "你的礼物正在穿越烟囱...",
                "即将生成专属圣诞祝福！"
            ];
            
            // 开始测试
            startBtn.addEventListener('click', function() {
                goToStep(2);
                updateProgress(2);
            });
            
            // 选项选择逻辑
            document.querySelectorAll('.option').forEach(option => {
                option.addEventListener('click', function() {
                    // 移除同组其他选项的选中状态
                    const parent = this.parentElement;
                    parent.querySelectorAll('.option').forEach(opt => {
                        opt.classList.remove('selected');
                    });
                    
                    // 选中当前选项
                    this.classList.add('selected');
                    
                    // 启用下一题按钮
                    const stepId = this.closest('.step').id;
                    let nextBtn;
                    
                    switch(stepId) {
                        case 'step2':
                            nextBtn = nextBtn1;
                            answers.q1 = this.dataset.value;
                            break;
                        case 'step3':
                            nextBtn = nextBtn2;
                            answers.q2 = this.dataset.value;
                            break;
                        case 'step4':
                            nextBtn = nextBtn3;
                            answers.q3 = this.dataset.value;
                            break;
                    }
                    
                    if(nextBtn) {
                        nextBtn.disabled = false;
                    }
                });
            });
            
            // 下一题按钮逻辑
            nextBtn1.addEventListener('click', function() {
                goToStep(3);
                updateProgress(3);
            });
            
            nextBtn2.addEventListener('click', function() {
                goToStep(4);
                updateProgress(4);
            });
            
            nextBtn3.addEventListener('click', function() {
                goToStep(5);
                updateProgress(5);
                
                // 模拟加载过程
                let messageIndex = 0;
                const messageInterval = setInterval(() => {
                    loadingText.textContent = loadingMessages[messageIndex];
                    messageIndex++;
                    
                    if (messageIndex >= loadingMessages.length) {
                        clearInterval(messageInterval);
                        
                        // 3秒后显示结果
                        setTimeout(() => {
                            goToStep(6);
                            updateProgress(6);
                        }, 3000);
                    }
                }, 500);
            });
            
            // 分享按钮
            shareBtn.addEventListener('click', function() {
                // 微信分享提示
                alert('感谢分享！\n\n请点击右上角"..."选择"发送给朋友"或"分享到朋友圈"，让更多朋友体验圣诞欢乐！\n\n圣诞快乐！🎄');
            });
            
            // 跳转到指定步骤
            function goToStep(stepNumber) {
                steps.forEach(step => {
                    step.classList.remove('active');
                });
                
                const stepElement = document.getElementById(`step${stepNumber}`);
                if(stepElement) {
                    stepElement.classList.add('active');
                    currentStep = stepNumber;
                }
            }
            
            // 更新进度条
            function updateProgress(stepNumber) {
                const progressPercentage = (stepNumber / totalSteps) * 100;
                progressBar.style.width = `${progressPercentage}%`;
            }
            
            // 添加一些额外效果
            document.querySelectorAll('.option').forEach(btn => {
                btn.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateY(-3px) scale(1.02)';
                });
                
                btn.addEventListener('mouseleave', function() {
                    if(!this.classList.contains('selected')) {
                        this.style.transform = 'translateY(0) scale(1)';
                    }
                });
            });
            
            // 添加点击音效（视觉反馈代替音频）
            document.querySelectorAll('button').forEach(btn => {
                btn.addEventListener('click', function() {
                    this.style.transform = 'scale(0.98)';
                    setTimeout(() => {
                        this.style.transform = '';
                    }, 150);
                });
            });
        });
    </script>
</body>
</html>
