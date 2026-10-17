[index.html](https://github.com/user-attachments/files/33591507/index.html)
<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>大狗教</title>
    <!-- 建議加入 prevent indexing（選用）：避免搜尋引擎索引公開 Pages（不是絕對保護） -->
    <meta name="robots" content="noindex,nofollow" />

    <style>
        :root {
            --primary-color: #2c3e50;
            --secondary-color: #3498db;
            --accent-color: #e67e22;
            --bg-color: #f8f9fa;
            --text-color: #333;
        }

        * { box-sizing: border-box; margin: 0; padding: 0; }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif, "Microsoft JhengHei";
            line-height: 1.6;
            background-color: var(--bg-color);
            color: var(--text-color);
        }

        header {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: #fff;
            padding: 60px 20px;
            text-align: center;
        }

        header h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
            letter-spacing: 2px;
        }

        header p { font-size: 1.1rem; opacity: 0.9; }

        .container { max-width: 900px; margin: 30px auto; padding: 0 20px; }

        section {
            background: #fff;
            padding: 30px;
            margin-bottom: 25px;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.05);
        }

        h2 {
            color: var(--primary-color);
            border-left: 5px solid var(--secondary-color);
            padding-left: 10px;
            margin-bottom: 20px;
            font-size: 1.5rem;
        }

        p { margin-bottom: 15px; text-align: justify; }

        .highlight-box {
            background-color: #eaf2f8;
            border-left: 5px solid var(--accent-color);
            padding: 15px;
            margin: 15px 0;
            border-radius: 0 8px 8px 0;
        }

        .highlight-box ul { list-style-type: none; padding-left: 0; }

        .highlight-box li { margin-bottom: 8px; position: relative; padding-left: 20px; }

        .highlight-box li::before { content: "🏆"; position: absolute; left: 0; }

        footer { text-align: center; padding: 30px; color: #7f8c8d; font-size: 0.9rem; }

        /* --- 密碼門樣式（整合） --- */
        #gate {
            position: fixed;
            inset: 0;
            background: rgba(11,18,32,0.55);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 9999;
            backdrop-filter: blur(4px);
        }
        .gate-panel {
            background: #fff;
            padding: 22px;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.25);
            width: 360px;
            max-width: 92%;
            text-align: center;
        }
        .gate-panel h3 { margin-bottom: 8px; color: var(--primary-color); }
        .gate-panel p { font-size: 0.9rem; color: #666; margin-bottom: 12px; }
        .gate-panel input {
            width: 100%; padding: 10px; border: 1px solid #ddd; border-radius: 6px;
            box-sizing: border-box; margin-bottom: 10px;
        }
        .gate-actions { display:flex; gap:8px; justify-content:center; }
        .gate-actions button {
            padding: 8px 12px; border-radius:6px; border: none; cursor: pointer;
        }
        .btn-ok { background: var(--secondary-color); color: #fff; }
        .btn-clear { background: #eee; color: #333; }

        /* 隱藏原站直到通過驗證 */
        #site { display: block; }
    </style>
</head>
<body>

  <!-- 密碼門（放最前） -->
  <div id="gate" aria-hidden="true" style="display:none;">
    <div class="gate-panel" role="dialog" aria-label="站點驗證">
      <h3>請輸入密碼以觀看內容</h3>
      <p>此為前端保護，適合非敏感內容的簡易隱私。若需更強保護請考慮 server-side 驗證。</p>
      <input id="pwd" type="password" placeholder="請輸入密碼" autocomplete="off" />
      <div class="gate-actions">
        <button id="ok" class="btn-ok">確認</button>
        <button id="clear" class="btn-clear">清除</button>
      </div>
      <p style="font-size:12px;color:#999;margin-top:10px;">提示：關閉瀏覽器後驗證會消失；按 F12 可查看原始碼（密碼以 base64 形式存在於程式碼中）。</p>
    </div>
  </div>

  <!-- 你的網站內容 -->
  <div id="site">
    <header>
        <h1>大狗教</h1>
        <p>探索科學奧秘 • 追求創新卓越</p>
    </header>

    <div class="container">
        <!-- 關於我 -->
        <section id="about">
            <h2>關於我</h2>
            <p>我是胡衣寰</p>
        </section>

        <!-- 榮譽與核心成就 -->
        <section id="honors">
            <h2>特殊榮譽與成就</h2>
            <p>在科學研究的道路上，我積極參與競賽，並在全國大型科學賽事中獲得評審的高度肯定：</p>
            <div class="highlight-box">
                <ul>
                    <li><strong>中華民國第 65 屆全國科學展覽會</strong> - 生活與應用科學科(一) <strong>全國第三名</strong></li>
                    <li><strong>第 65 屆全國科展特別獎</strong> - <strong>D-Link 友訊智慧生活創意獎</strong></li>
                    <li><strong>得獎作品：</strong>《熱與磁的雙重試煉：探討不同鐵磁流體的導熱效果》</li>
                </ul>
            </div>
            <p>此研究聚焦於鐵磁流體在不同溫度與磁場環境下的導熱表現，期望能為未來智慧生活、高效散熱等科技領域提供創新的應用參考。</p>
        </section>

        <!-- 科研經歷與特質 -->
        <section id="experience">
            <h2>科研歷程與個人特質</h2>
            <p><strong>自主探究與團隊協作：</strong> 科展的歷程讓我深刻體會到「從做中學」的價值。從文獻探討、實驗設計、無數次的失敗修正，到最終的數據分析，我培養了嚴謹的科學態度，也鍛鍊出獨立解決問題的能力。</p>
            <p><strong>跨領域學習：</strong> 除了物理與應用科學，我也積極跨足資訊科技與動態系統動力學的學習，期許自己未來能運用多元的數位工具，進行更深度的跨領域科學實驗。</p>
        </section>

        <!-- 未來展望 -->
        <section id="future">
            <h2>未來展望</h2>
            <p>展望未來，我將繼續保持對科學的熱忱，持續精進自身的學術能力與實作技巧。我期許自己能在高等教育中進一步深造，將科學理論與智慧科技、環境永續相結合，為社會帶來具體且有益的創新貢獻。</p>
        </section>
    </div>

    <footer>
        <p>大狗教特別專制</p>
    </footer>
  </div>

  <script>
    // === 配置：把下面 PASSWORD_B64 改成你要的密碼的 base64 編碼（不是明文）
    // 我已把密碼改為 "6767"（base64 -> "Njc2Nw==")
    const PASSWORD_B64 = "Njc2Nw=="; // <-- 已設定為 base64("6767")
    const AUTH_KEY = "site_auth_v1"; // sessionStorage key（不需改動一般情況）

    function isAuthed() {
      return sessionStorage.getItem(AUTH_KEY) === "1";
    }
    function setAuthed() {
      sessionStorage.setItem(AUTH_KEY, "1");
      document.getElementById('gate').style.display = 'none';
      document.getElementById('gate').setAttribute('aria-hidden','true');
    }
    function showGate() {
      document.getElementById('gate').style.display = 'flex';
      document.getElementById('gate').setAttribute('aria-hidden','false');
    }

    (function(){
      // 頁面載入時顯示或關閉 gate
      if (isAuthed()) {
        setAuthed();
      } else {
        showGate();
      }

      // 事件綁定
      document.getElementById('ok').addEventListener('click', () => {
        const v = document.getElementById('pwd').value || "";
        try {
          const real = atob(PASSWORD_B64);
          if (v === real) {
            setAuthed();
          } else {
            alert('密碼錯誤，請再試一次');
          }
        } catch(e) {
          console.error(e);
          alert('驗證錯誤（請檢查密碼設定）');
        }
      });

      document.getElementById('clear').addEventListener('click', () => {
        document.getElementById('pwd').value = '';
      });

      document.getElementById('pwd').addEventListener('keydown', (e) => {
        if (e.key === 'Enter') document.getElementById('ok').click();
      });
    })();
  </script>

</body>
</html>
