<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Abutiieeyy Mahappen— WhatsApp Bot</title>

  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;800&family=Source+Code+Pro:wght@400;600&display=swap" rel="stylesheet">

  <!-- Font Awesome for icons -->
  <script src="https://kit.fontawesome.com/7b7b7b7b7b.js" crossorigin="anonymous"></script>

  <style>
    :root{
      --bg:#f8fafb;
      --muted:#7b7f86;
      --accent:#6c5ce7;
      --card:#ffffff;
      --rounded:14px;
      --max:980px;
      --glass: rgba(255,255,255,0.6);
      --shadow: 0 6px 22px rgba(12,18,28,0.08);
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family: "Montserrat",system-ui,-apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      background:linear-gradient(180deg,#f6f9fb, #ffffff 60%);
      color:#222;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      padding:24px;
      display:flex;
      justify-content:center;
    }

    .wrap{
      width:100%;
      max-width:var(--max);
    }

    header.hero{
      background: linear-gradient(90deg, rgba(108,92,231,0.95), rgba(78,68,178,0.92));
      color:white;
      border-radius:var(--rounded);
      padding:22px;
      box-shadow:var(--shadow);
      display:flex;
      gap:18px;
      align-items:center;
      margin-bottom:20px;
    }
    .hero .brand{
      flex:1;
    }
    .brand h1{
      margin:0;
      font-size:20px;
      letter-spacing:1px;
      font-weight:800;
    }
    .brand p{
      margin:6px 0 0 0;
      opacity:0.95;
      font-size:13px;
    }

    .author-badges{
      display:flex;
      gap:8px;
      align-items:center;
    }
    .badge{
      background:rgba(255,255,255,0.12);
      padding:6px 10px;
      border-radius:8px;
      font-weight:600;
      font-size:13px;
      display:inline-flex;
      gap:8px;
      align-items:center;
    }

    main.card{
      background:var(--card);
      border-radius:14px;
      padding:18px;
      box-shadow:var(--shadow);
    }

    .row-social{
      display:flex;
      gap:10px;
      align-items:center;
      margin:8px 0 16px 0;
    }
    .social{
      width:44px;height:44px;border-radius:50%;
      display:inline-grid;place-items:center;font-size:18px;
      background:linear-gradient(180deg,#e6f7ee,#c7f0d8);
      box-shadow:0 4px 14px rgba(12,18,28,0.06);
    }
    .social.instagram{background:linear-gradient(180deg,#ffd6e0,#ffb3d0)}
    .social.facebook{background:linear-gradient(180deg,#d8e8ff,#b5d6ff)}
    .social.dev{background:linear-gradient(180deg,#fff3c9,#ffd77a)}
    .social.twitter{background:linear-gradient(180deg,#dff2ff,#bfe9ff)}

    h2.title{
      margin:6px 0 4px;
      font-size:34px;
      letter-spacing:-0.5px;
      line-height:1.02;
    }
    .sponsor{
      display:inline-block;
      margin-top:6px;
      background:#f2f2f2;
      color:#333;
      padding:6px 10px;
      border-radius:8px;
      font-weight:600;
      font-size:13px;
    }
    .lead{
      font-family: "Source Code Pro", monospace;
      color:var(--accent);
      margin:14px 0;
      letter-spacing:1px;
      font-size:18px;
    }

    .hero-image{
      width:100%;
      height:220px;
      border-radius:12px;
      background:linear-gradient(180deg,#111 0%, #666 100%);
      background-image: url('https://images.unsplash.com/photo-1515879218367-8466d910aaa4?q=80&w=1600&auto=format&fit=crop&ixlib=rb-4.0.3&s=000');
      background-size:cover;
      background-position:center;
      margin:12px 0 18px;
      overflow:hidden;
    }

    /* stats badges */
    .stats{display:flex;gap:8px;flex-wrap:wrap;margin:8px 0 18px}
    .pill{
      background:#f2f2f2;padding:8px 10px;border-radius:8px;font-weight:700;font-size:13px;color:#333;
      display:inline-flex;gap:8px;align-items:center;
    }
    .pill.green{background:#d9f6d9;color:#1b7a2a}
    .pill.blue{background:#e9f3ff;color:#1462a6}

    /* deployment grid */
    .deploy-grid{
      display:grid;
      grid-template-columns: repeat(auto-fit,minmax(180px,1fr));
      gap:12px;
      margin:14px 0 22px;
    }
    .deploy-btn{
      display:flex;align-items:center;gap:12px;padding:12px;border-radius:10px;font-weight:700;
      color:white;text-decoration:none;justify-content:center;box-shadow:0 6px 18px rgba(12,18,28,0.06)
    }
    .heroku{background:#6b1b83}
    .koyeb{background:#8fd44a;color:#072b12}
    .railway{background:#e36b4f}
    .render{background:#111}
    .netlify{background:#1578b3}
    .replit{background:#1290d8}
    .deploy-now{display:flex;justify-content:center;gap:10px;align-items:center;padding:12px;border-radius:10px;overflow:hidden}

    .deploy-now .left{background:#5c6770;color:white;padding:10px 16px;border-radius:8px 0 0 8px}
    .deploy-now .right{background:#b9dd2b;color:#10210a;padding:10px 18px;border-radius:0 8px 8px 0;font-weight:800}

    hr.sep{border:0;border-top:1px solid #e8e8e8;margin:20px 0}

    .reminder{
      border-left:4px solid #f2c94c;padding:14px;background:#fff9e6;border-radius:8px;
    }
    .notice{
      background:#f6f8ff;padding:14px;border-radius:8px;border-left:4px solid #9fb7ff;margin-top:12px;
    }

    .action-support{
      display:flex;gap:12px;align-items:center;margin-top:14px;flex-wrap:wrap;
    }
    .whatsapp-btn{
      background:#25D366;color:white;padding:10px 16px;border-radius:8px;text-decoration:none;font-weight:800;display:inline-flex;gap:10px;align-items:center;
      box-shadow:0 8px 28px rgba(37,211,102,0.12);
    }

    footer{
      margin-top:22px;padding:12px;text-align:center;color:var(--muted);font-size:14px;
    }

    /* responsive tweaks */
    @media (max-width:520px){
      h2.title{font-size:28px}
      .hero{padding:16px;flex-direction:column;align-items:flex-start;gap:10px}
      .hero .brand p{font-size:12px}
      .hero-image{height:180px}
    }

  </style>
</head>
<body>
  <div class="wrap">
    <header class="hero" role="banner" aria-label="Abutiieeyy Mahappen WhatsApp bot">
      <div class="brand">
        <h1>Abutiieeyy Mahappen WHATSAPP BOT</h1>
        <p>Powering your WhatsApp • Bots • Plugins • Deploy guides</p>
      </div>
      <div class="author-badges" aria-hidden="true">
        <span class="badge"><i class="fas fa-user"></i> CASEYWEB</span>
        <span class="badge"><i class="fas fa-code-branch"></i> v2.0</span>
      </div>
    </header>

    <main class="card" role="main">
      <div class="row-social" aria-hidden="true">
        <a class="social whatsapp" href="#" title="WhatsApp"><i class="fab fa-whatsapp"></i></a>
        <a class="social instagram" href="#" title="Instagram"><i class="fab fa-instagram"></i></a>
        <a class="social facebook" href="#" title="Facebook"><i class="fab fa-facebook-f"></i></a>
        <a class="social dev" href="#" title="DEV"><i class="fab fa-dev"></i></a>
        <a class="social twitter" href="#" title="Twitter"><i class="fab fa-twitter"></i></a>
      </div>

      <div style="display:flex;align-items:center;justify-content:space-between;gap:12px;flex-wrap:wrap">
        <div>
          <h2 class="title">Âbùtiïèy Mahappen LOF bot. <span style="font-size:20px">❤️</span></h2>
          <div class="sponsor">Sponsor <strong style="background:#ff7f50;color:white;padding:4px 8px;border-radius:6px;margin-left:8px;font-weight:800">caseyweb</strong></div>
          <div class="lead">Powering Your WhatsApp</div>
        </div>
        <div style="min-width:110px;text-align:right">
          <!-- small stats pills -->
          <div style="display:flex;flex-direction:column;gap:6px;align-items:flex-end">
            <span class="pill">followers <strong style="margin-left:6px">113</strong></span>
            <span class="pill blue">stars <strong style="margin-left:6px">94</strong></span>
            <span class="pill green">repo size <strong style="margin-left:6px">5.1 MiB</strong></span>
          </div>
        </div>
      </div>

      <div class="hero-image" role="img" aria-label="hero image"></div>

      <hr class="sep" />

      <section aria-labelledby="deployHeading">
        <h3 id="deployHeading" style="font-size:20px;margin:0 0 12px;font-weight:800;color:#111">DEPLOYMENT SECTION</h3>

        <div class="deploy-grid" role="list">
          <a class="deploy-btn heroku" role="listitem" href="#" title="Heroku deploy">
            <i class="fab fa-heroku" style="font-size:20px"></i> HEROKU DEPLOY
          </a>

          <a class="deploy-btn koyeb" role="listitem" href="#" title="Koyeb deploy">
            <i class="fas fa-server" style="font-size:18px;color:rgba(0,0,0,0.6)"></i> KOYEB DEPLOY
          </a>

          <a class="deploy-btn railway" role="listitem" href="#" title="Railway deploy">
            <i class="fas fa-train" style="font-size:18px"></i> RAILWAY DEPLOY
          </a>

          <a class="deploy-btn render" role="listitem" href="#" title="Render deploy">
            <i class="fas fa-wrench" style="font-size:18px"></i> RENDER DEPLOY
          </a>

          <a class="deploy-btn netlify" role="listitem" href="#" title="Netlify deploy">
            <i class="fas fa-cloud" style="font-size:18px"></i> NETLIFY DEPLOY
          </a>

          <a class="deploy-btn replit" role="listitem" href="#" title="Replit deploy">
            <i class="fas fa-terminal" style="font-size:18px"></i> REPLIT DEPLOY
          </a>
        </div>

        <div style="display:flex;justify-content:center;margin-top:8px">
          <div class="deploy-now" role="button" aria-pressed="false">
            <div class="left">DEPLOY</div>
            <div class="right">NOW</div>
          </div>
        </div>
      </section>

      <hr class="sep" />

      <section aria-labelledby="infoHeading">
        <h3 id="infoHeading" style="font-size:20px;margin:0 0 8px;font-weight:800">CASEYRHODES XMD Info</h3>

        <div class="stats" aria-hidden="true">
          <span class="pill">followers <strong>113</strong></span>
          <span class="pill blue">stars <strong>94</strong></span>
          <span class="pill">forks <strong>463</strong></span>
          <span class="pill green">Maintained? <strong>yes</strong></span>
        </div>

        <div class="reminder" role="note" aria-label="Warning">
          <strong>⚠️ Reminder</strong>
          <p style="margin:8px 0 0;color:#333;line-height:1.5">
            <strong>Disclaimer:</strong> This bot is not affiliated with WhatsApp Inc. Use at your own risk. Misusing the bot may result in your WhatsApp account being banned. You can only unban your account once. I am not responsible for bans or misuse. Please keep this warning in mind before proceeding.
          </p>
        </div>

        <div class="notice" role="note" aria-label="Notice">
          <strong>ℹ️ Notice</strong>
          <p style="margin:8px 0 0;color:#2b2b2b;line-height:1.5">
            Not for sale — If any plugin's code is obfuscated, you do not have permission to edit it. Please give credit if you reuse or reupload plugins/files.
          </p>
        </div>

        <div class="action-support">
          <a class="whatsapp-btn" href="#" title="Support group">
            <i class="fab fa-whatsapp"></i>
            SUPPORT GROUP
          </a>

          <a class="whatsapp-btn" style="background:linear-gradient(90deg,#3dbb3d,#25d366)" href="#" title="WhatsApp channel">
            <i class="fab fa-whatsapp"></i>
            OUR WHATSAPP CHANNEL
          </a>
        </div>
      </section>

      <footer>
        <div>This site is open source. Improve this page.</div>
      </footer>
    </main>
  </div>
</body>
</html>
