<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>公司展示页面 - 银杏主题</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        /* 页面全屏布局 */
        html, body {
            height: 100%;
            overflow: hidden;
            font-family: "Microsoft Yahei", sans-serif;
        }

        /* 银杏树背景层 */
        .bg-container {
            position: relative;
            width: 100%;
            height: 100%;
            background: url("https://images.unsplash.com/photo-1549880338-65ddcdfd017b?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80") no-repeat center center;
            background-size: cover;
            filter: brightness(0.9);
        }

        /* 树叶飘落容器（用于承载所有动态树叶） */
        .leaves-container {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none; /* 不遮挡公司信息的交互 */
        }

        /* 银杏树叶样式 */
        .leaf {
            position: absolute;
            width: 25px;
            height: 25px;
            background: linear-gradient(135deg, #f9d71c, #f5b82e);
            clip-path: polygon(50% 0%, 100% 38%, 82% 100%, 18% 100%, 0% 38%);
            opacity: 0.8;
            animation: fall linear infinite;
            transform-origin: center center;
        }

        /* 树叶飘落动画 */
        @keyframes fall {
            0% {
                top: -10%;
                transform: translateX(0) rotate(0deg);
            }
            100% {
                top: 100%;
                transform: translateX(50px) rotate(360deg);
            }
        }

        /* 公司信息展示层（醒目样式） */
        .company-info {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: rgba(0, 0, 0, 0.6);
            padding: 3rem 4rem;
            border-radius: 16px;
            text-align: center;
            box-shadow: 0 0 30px rgba(255, 215, 0, 0.5);
            z-index: 10; /* 确保在树叶上层 */
        }

        /* 公司名称（最醒目） */
        .company-name {
            font-size: 3rem;
            color: #fff;
            margin-bottom: 1rem;
            text-shadow: 0 2px 10px #f9d71c;
            letter-spacing: 2px;
        }

        /* 公司简介 */
        .company-desc {
            font-size: 1.2rem;
            color: #f0f0f0;
            margin-bottom: 2rem;
            line-height: 1.6;
        }

        /* 公司联系方式 */
        .company-contact {
            font-size: 1rem;
            color: #f9d71c;
            line-height: 1.8;
        }

        /* 响应式适配 */
        @media (max-width: 768px) {
            .company-info {
                padding: 2rem 2.5rem;
            }
            .company-name {
                font-size: 2rem;
            }
            .company-desc {
                font-size: 1rem;
            }
        }
    </style>
</head>
<body>
    <!-- 背景容器 -->
    <div class="bg-container">
        <!-- 树叶飘落容器 -->
        <div class="leaves-container" id="leavesContainer"></div>

        <!-- 公司信息（醒目展示） -->
        <div class="company-info">
            <h1 class="company-name">XX科技有限公司</h1>
            <p class="company-desc">
                专注于人工智能与数字化解决方案，<br>
                以技术创新驱动企业发展，打造行业标杆品牌
            </p>
            <div class="company-contact">
                <p>联系电话：400-123-4567</p>
                <p>公司地址：北京市朝阳区科技园区88号</p>
                <p>官网：www.xxtech.com</p>
            </div>
        </div>
    </div>

    <script>
        // 动态生成银杏树叶，实现随机飘落效果
        function createLeaves() {
            const leavesContainer = document.getElementById('leavesContainer');
            const leafCount = 50; // 树叶数量，可调整

            for (let i = 0; i < leafCount; i++) {
                const leaf = document.createElement('div');
                leaf.classList.add('leaf');

                // 随机设置树叶初始位置、大小、动画延迟和时长
                const randomLeft = Math.random() * 100; // 水平位置 0-100%
                const randomSize = Math.random() * 15 + 15; // 大小 15-30px
                const randomDelay = Math.random() * 20; // 动画延迟 0-20s
                const randomDuration = Math.random() * 20 + 10; // 飘落时长 10-30s
                const randomOpacity = Math.random() * 0.5 + 0.5; // 透明度 0.5-1

                // 应用随机样式
                leaf.style.left = `${randomLeft}%`;
                leaf.style.width = `${randomSize}px`;
                leaf.style.height = `${randomSize}px`;
                leaf.style.animationDelay = `${randomDelay}s`;
                leaf.style.animationDuration = `${randomDuration}s`;
                leaf.style.opacity = randomOpacity;

                leavesContainer.appendChild(leaf);
            }
        }

        // 页面加载完成后生成树叶
        window.onload = createLeaves;
    </script>
</body>
</html>
