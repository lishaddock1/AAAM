<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>XX科技有限公司 - 人工智能与数字化解决方案</title>
    <style>
        /* 全局样式重置与基础配置 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: "Microsoft Yahei", sans-serif;
        }

        body {
            padding: 20px;
            background-color: #f5f5f5;
        }

        /* CSS变量：统一管理样式属性，方便后续维护 */
        :root {
            --primary-highlight: #f9d71c;
            --bg-overlay: rgba(0, 0, 0, 0.5);
            --text-white: #ffffff;
            --text-light-gray: #f0f0f0;
            --border-radius-lg: 20px;
            --border-radius-md: 16px;
            --box-shadow: 0 0 40px rgba(249, 215, 28, 0.3);
            --spacing-xl: 60px;
            --spacing-lg: 40px;
            --spacing-md: 30px;
            --spacing-sm: 20px;
            --spacing-xs: 10px;
        }

        /* 主容器样式 */
        .company-container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
        }

        /* 背景图容器样式 */
        .bg-wrapper {
            width: 100%;
            padding: var(--spacing-xl) var(--spacing-sm);
            background: url('https://images.unsplash.com/photo-1549880338-65ddcdfd017b?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80') no-repeat center center;
            background-size: cover;
            border-radius: var(--border-radius-lg);
            box-shadow: var(--box-shadow);
            position: relative;
            overflow: hidden;
        }

        /* 内容层样式 */
        .content-wrapper {
            background: var(--bg-overlay);
            padding: var(--spacing-lg) var(--spacing-lg);
            border-radius: var(--border-radius-md);
            text-align: center;
            position: relative;
            z-index: 10;
            max-width: 800px;
            margin: 0 auto;
        }

        /* 公司标题样式 */
        .company-title {
            font-size: 4rem;
            color: var(--text-white);
            margin: 0 0 var(--spacing-sm) 0;
            text-shadow: 0 3px 15px var(--primary-highlight);
            letter-spacing: 4px;
            font-weight: 700;
        }

        /* 公司描述样式 */
        .company-desc {
            font-size: 1.3rem;
            color: var(--text-light-gray);
            line-height: 1.8;
            margin: 0 0 var(--spacing-md) 0;
        }

        /* 链接样式 */
        .info-link {
            color: var(--primary-highlight);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .info-link:hover {
            color: #fff;
            text-decoration: underline;
        }

        /* 响应式适配：针对移动端、平板等小屏幕设备 */
        @media (max-width: 768px) {
            :root {
                --spacing-xl: 30px;
                --spacing-lg: 20px;
                --spacing-md: 20px;
            }

            .company-title {
                font-size: 2.5rem;
                letter-spacing: 2px;
            }

            .company-desc {
                font-size: 1.1rem;
            }
        }

        @media (max-width: 480px) {
            .company-title {
                font-size: 1.8rem;
            }

            .content-wrapper {
                padding: var(--spacing-md) var(--spacing-xs);
            }
        }
    </style>
</head>
<body>
    <!-- 语义化标签：main标识主要内容区域 -->
    <main class="company-container">
        <!-- 背景图容器 -->
        <div class="bg-wrapper">
            <!-- 核心内容层 -->
            <div class="content-wrapper">
                <h1 class="company-title">XX科技有限公司</h1>
                <p class="company-desc">
                    专注于人工智能与数字化解决方案 <br>
                    【<a href="./data/company-info.md" class="info-link">点击查看完整公司信息</a>】
                </p>
            </div>
        </div>
    </main>
</body>
</html>