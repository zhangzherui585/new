<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>枕枝 · 公开讨论区</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,500;14..32,600&family=Nunito:wght@400;500;600;700&display=swap" rel="stylesheet">
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }

    :root {
      --bg: #f9f7f3;
      --surface: #ffffff;
      --border: #e9e3da;
      --text-primary: #2e2b26;
      --text-secondary: #6b655b;
      --accent: #8b6b4f;
      --accent-light: #f0e8e0;
      --shadow-sm: 0 4px 12px rgba(0,0,0,0.02), 0 1px 2px rgba(0,0,0,0.03);
      --shadow-md: 0 12px 28px -8px rgba(0,0,0,0.06), 0 4px 12px rgba(0,0,0,0.03);
      --radius-md: 20px;
      --radius-sm: 14px;
      --radius-full: 100px;
      --font-display: 'Nunito', sans-serif;
      --font-body: 'Inter', sans-serif;
    }

    body {
      background-color: var(--bg);
      font-family: var(--font-body);
      color: var(--text-primary);
      line-height: 1.5;
      padding: 1.5rem;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    .site-wrapper {
      max-width: 960px;
      width: 100%;
      background: var(--surface);
      border-radius: 36px;
      box-shadow: var(--shadow-md);
      border: 1px solid var(--border);
      padding: 2.5rem 2rem;
    }

    /* 顶部导航 */
    .top-nav {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 2rem;
      flex-wrap: wrap;
      gap: 1rem;
    }

    .logo {
      font-family: var(--font-display);
      font-weight: 700;
      font-size: 1.6rem;
      letter-spacing: -0.02em;
      color: var(--text-primary);
      display: flex;
      align-items: center;
      gap: 0.3rem;
    }

    .logo-dot {
      display: inline-block;
      width: 10px;
      height: 10px;
      background: var(--accent);
      border-radius: 50%;
      margin-left: 4px;
    }

    .nav-links {
      display: flex;
      gap: 2rem;
      font-weight: 500;
      color: var(--text-secondary);
    }

    .nav-links a {
      text-decoration: none;
      color: inherit;
      font-size: 0.95rem;
      transition: color 0.15s;
      border-bottom: 1.5px solid transparent;
      padding-bottom: 2px;
      cursor: pointer;
    }

    .nav-links a:hover, .nav-links a.active {
      color: var(--accent);
      border-bottom-color: var(--accent);
    }

    /* 论坛头部 */
    .forum-header {
      background: linear-gradient(135deg, #fdfcf9 0%, #f6f1ea 100%);
      border-radius: var(--radius-md);
      padding: 1.8rem 2rem;
      margin-bottom: 2rem;
      border: 1px solid var(--border);
    }

    .forum-header h1 {
      font-family: var(--font-display);
      font-weight: 700;
      font-size: 2rem;
      letter-spacing: -0.02em;
      margin-bottom: 0.5rem;
    }

    .forum-header h1 span {
      color: var(--accent);
      background: linear-gradient(145deg, var(--accent) 0%, #a88663 100%);
      -webkit-background-clip: text;
      background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .forum-header p {
      color: var(--text-secondary);
      font-size: 0.95rem;
    }

    .forum-notice {
      margin-top: 1rem;
      font-size: 0.82rem;
      color: var(--text-secondary);
      background: rgba(255,255,255,0.6);
      border: 1px solid var(--border);
      border-radius: 40px;
      padding: 0.5rem 1rem;
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
    }

    .forum-notice .dot {
      width: 7px;
      height: 7px;
      background: #7fbf7f;
      border-radius: 50%;
      flex-shrink: 0;
    }

    /* Giscus 容器 */
    .giscus-wrap {
      background: #fdfcf9;
      border: 1px solid var(--border);
      border-radius: var(--radius-md);
      padding: 1.5rem 1.6rem;
      box-shadow: var(--shadow-sm);
      margin-bottom: 2rem;
      min-height: 200px;
    }

    .giscus-wrap .giscus-title {
      font-family: var(--font-display);
      font-weight: 600;
      font-size: 1.05rem;
      margin-bottom: 1rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
      color: var(--text-primary);
    }

    .giscus-wrap .giscus-title .spark-icon {
      background: var(--accent-light);
      border-radius: 10px;
      padding: 5px 8px;
      font-size: 1.1rem;
      color: var(--accent);
    }

    .giscus {
      width: 100%;
    }

    /* 底部文案区 */
    .footer-grid {
      display: grid;
      grid-template-columns: 1fr 1fr 1fr;
      gap: 2rem;
      align-items: start;
    }

    .footer-col h4 {
      font-family: var(--font-display);
      font-weight: 600;
      font-size: 1rem;
      margin-bottom: 1rem;
      color: var(--text-primary);
      letter-spacing: -0.01em;
    }

    .footer-col p {
      color: var(--text-secondary);
      font-size: 0.9rem;
      margin-bottom: 0.6rem;
      line-height: 1.5;
    }

    .tag-group {
      display: flex;
      flex-wrap: wrap;
      gap: 0.6rem;
      margin-top: 0.5rem;
    }

    .tag {
      background: var(--bg);
      border-radius: 40px;
      padding: 0.35rem 1rem;
      font-size: 0.8rem;
      font-weight: 500;
      color: var(--text-secondary);
      border: 1px solid var(--border);
    }

    .divider {
      border: 0;
      height: 1px;
      background: linear-gradient(to right, transparent, var(--border), transparent);
      margin: 2rem 0 1.5rem 0;
    }

    .share-section {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 1rem;
      padding-top: 1rem;
    }

    .share-hint {
      font-size: 0.85rem;
      color: var(--text-secondary);
      display: flex;
      align-items: center;
      gap: 0.6rem;
    }

    .share-buttons { display: flex; gap: 0.7rem; }

    .share-btn {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 40px;
      padding: 0.5rem 1rem;
      font-size: 0.8rem;
      font-weight: 500;
      color: var(--text-secondary);
      cursor: pointer;
      transition: background 0.15s, border 0.15s, color 0.15s;
      font-family: var(--font-body);
      display: flex;
      align-items: center;
      gap: 0.4rem;
      touch-action: manipulation;
    }

    .share-btn:hover {
      background: var(--accent-light);
      border-color: var(--accent);
      color: var(--accent);
    }

    .copy-toast {
      position: fixed;
      bottom: 30px;
      left: 50%;
      transform: translateX(-50%) translateY(20px);
      background: var(--text-primary);
      color: white;
      padding: 0.7rem 1.6rem;
      border-radius: 60px;
      font-size: 0.9rem;
      font-weight: 500;
      opacity: 0;
      pointer-events: none;
      transition: opacity 0.2s, transform 0.2s;
      box-shadow: var(--shadow-md);
      z-index: 999;
    }

    .copy-toast.show {
      opacity: 1;
      transform: translateX(-50%) translateY(0);
    }

    @media (max-width: 880px) {
      .site-wrapper { padding: 1.8rem 1.4rem; border-radius: 28px; }
      .nav-links { gap: 1.2rem; }
      .forum-header h1 { font-size: 1.6rem; }
      .footer-grid { grid-template-columns: 1fr; gap: 1.6rem; }
      .top-nav { flex-direction: column; align-items: flex-start; }
    }

    @media (max-width: 480px) {
      body { padding: 0.8rem; }
      .site-wrapper { padding: 1.4rem 1rem; border-radius: 24px; }
      .forum-header { padding: 1.4rem 1.2rem; }
      .giscus-wrap { padding: 1.1rem 1rem; }
      .share-section { flex-direction: column; align-items: flex-start; }
    }
  </style>
</head>
<body>
  <div class="site-wrapper">
    <!-- 导航 -->
    <header class="top-nav">
      <div class="logo">
        <span>枕枝</span>
        <span class="logo-dot"></span>
      </div>
      <div class="nav-links">
        <a class="active" data-scroll="discussion">讨论区</a>
        <a data-scroll="footerInfo">关于</a>
        <a id="shareNav">分享</a>
      </div>
    </header>

    <main>
      <!-- 论坛头部 -->
      <div class="forum-header" id="discussion">
        <h1>枕枝 <span>公开讨论区</span></h1>
        <p>自由发表言论 · 分享灵感 · 记录日常。评论公开可见，用 GitHub 账号登录即可参与。</p>
        <div class="forum-notice">
          <span class="dot"></span>
          评论区由 Giscus 驱动，数据存储在 GitHub Discussions
        </div>
      </div>

      <!-- Giscus 评论区容器 -->
      <div class="giscus-wrap">
        <div class="giscus-title">
          <span class="spark-icon">💬</span>
          <span>讨论与留言</span>
        </div>
        <div class="giscus"></div>
      </div>

      <!-- 底部文案区 -->
      <div class="footer-grid" id="footerInfo">
        <div class="footer-col">
          <h4>📝 文案 · 细语</h4>
          <p>“把日常写成诗，让每个字都有落脚的地方。”</p>
          <p>在这里记录灵感碎片，或者用一句话描述你心中的画面。文字是图像的种子。</p>
          <div class="tag-group">
            <span class="tag">随笔</span>
            <span class="tag">短句</span>
            <span class="tag">灵感</span>
          </div>
        </div>
        <div class="footer-col">
          <h4>🧱 排版 · 呼吸感</h4>
          <p>留白、节奏、对比。模块化的卡片设计让内容自己会说话。</p>
          <p>每个区块都经过仔细调校，在手机和电脑上都有舒适的阅读体验。</p>
        </div>
        <div class="footer-col">
          <h4>⚙️ 关于本站</h4>
          <p>一个基于 GitHub Pages 托管的个人讨论区，评论区使用 Giscus 实现公开保存。</p>
          <p>无需自己维护服务器，评论数据自动同步到仓库的 Discussions。</p>
        </div>
      </div>

      <hr class="divider">

      <!-- 分享 -->
      <div class="share-section">
        <div class="share-hint"><span>🔗</span> 分享这个页面，让更多人加入讨论</div>
        <div class="share-buttons">
          <button class="share-btn" id="copyLinkBtn">📋 复制链接</button>
          <button class="share-btn" id="shareBtn">📤 系统分享</button>
        </div>
      </div>
    </main>
  </div>

  <div id="copyToast" class="copy-toast">链接已复制</div>

  <!-- ============================================================
       Giscus 评论区脚本
       使用前请替换以下 4 个值为你在 giscus.app 获取的真实配置：
       data-repo        → 你的GitHub用户名/仓库名
       data-repo-id     → 仓库ID
       data-category    → 讨论分类名称（建议 Announcements）
       data-category-id → 分类ID
  ============================================================ -->
  <script src="https://giscus.app/client.js"
          data-repo="https://github.com/zhangzherui585/new"
          data-repo-id="new"
          data-category=“Announcements"
          data-category-id="main"
          data-mapping="pathname"
          data-strict="0"
          data-reactions-enabled="1"
          data-emit-metadata="0"
          data-input-position="bottom"
          data-theme="preferred_color_scheme"
          data-lang="zh-CN"
          crossorigin="anonymous"
          async>
  </script>

  <script>
    (function() {
      'use strict';

      // 复制链接
      const copyLinkBtn = document.getElementById('copyLinkBtn');
      const shareBtn = document.getElementById('shareBtn');
      const shareNav = document.getElementById('shareNav');
      const copyToast = document.getElementById('copyToast');

      function showToast(msg) {
        copyToast.textContent = msg || '链接已复制';
        copyToast.classList.add('show');
        setTimeout(() => copyToast.classList.remove('show'), 2000);
      }

      async function copyLink() {
        const url = window.location.href;
        try {
          await navigator.clipboard.writeText(url);
          showToast('链接已复制，分享给朋友吧');
        } catch (err) {
          const ta = document.createElement('textarea');
          ta.value = url;
          document.body.appendChild(ta);
          ta.select();
          document.execCommand('copy');
          document.body.removeChild(ta);
          showToast('链接已复制');
        }
      }

      copyLinkBtn.addEventListener('click', copyLink);

      shareNav.addEventListener('click', (e) => {
        e.preventDefault();
        document.querySelector('.share-section').scrollIntoView({ behavior: 'smooth', block: 'center' });
      });

      shareBtn.addEventListener('click', async () => {
        if (navigator.share) {
          try {
            await navigator.share({
              title: '枕枝 · 公开讨论区',
              text: '一个公开可见的个人讨论区，来聊聊吧。',
              url: window.location.href,
            });
          } catch (err) {
            if (err.name !== 'AbortError') copyLink();
          }
        } else {
          copyLink();
          showToast('浏览器不支持分享，已复制链接');
        }
      });

      // 导航滚动
      document.querySelectorAll('[data-scroll]').forEach(a => {
        a.addEventListener('click', (e) => {
          e.preventDefault();
          const target = document.getElementById(a.getAttribute('data-scroll'));
          if (target) target.scrollIntoView({ behavior: 'smooth', block: 'start' });
          document.querySelectorAll('.nav-links a').forEach(x => x.classList.remove('active'));
          a.classList.add('active');
        });
      });
    })();
  </script>
</body>
</html>
