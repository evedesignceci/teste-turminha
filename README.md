<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <title>Turminha do Xexéu — Portal Oficial</title>
  
  <link rel="icon" type="image/png" href="https://res.cloudinary.com/oactqmgs/image/upload/v1786908275/TURMINHA_LOGO.png">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@500;700;800;900&display=swap" rel="stylesheet">
  
  <style>
    :root {
      --primary: #3B82F6;
      --primary-dark: #1D4ED8;
      --secondary: #F59E0B;
      --accent: #EF4444;
      --purple: #8B5CF6;
      --green: #10B981;
      --tea-blue: #0284C7;
      --tea-light: #F0F9FF;
      --bg-gradient: linear-gradient(180deg, #E0F2FE 0%, #FAF5FF 60%, #FFF1F2 100%);
      --card-bg: #FFFFFF;
      --text-main: #0F172A;
      --text-muted: #475569;
      --radius-xl: 28px;
      --radius-lg: 20px;
      --radius-md: 14px;
      --shadow-sm: 0 4px 12px rgba(15, 23, 42, 0.05);
      --shadow-md: 0 8px 24px rgba(15, 23, 42, 0.08);
      --shadow-lg: 0 14px 32px rgba(59, 130, 246, 0.16);
    }

    /* MODO SENSORIAL PROFUNDO E CALMO */
    body.sensory-mode {
      --bg-gradient: #F1F5F9 !important; 
      --primary: #475569 !important;
      --primary-dark: #334155 !important;
      --secondary: #64748B !important;
      --tea-blue: #334155 !important;
      --tea-light: #FFFFFF !important;
      background: var(--bg-gradient) !important;
      color: #1E293B !important;
    }
    body.sensory-mode * { animation: none !important; box-shadow: none !important; transition: none !important; }
    body.sensory-mode .app-container { border: 2px solid #CBD5E1; background: #FFFFFF; }
    body.sensory-mode header { background: #E2E8F0 !important; }
    body.sensory-mode .interactive-card,
    body.sensory-mode .tea-box,
    body.sensory-mode .video-card { background: #FFFFFF !important; border: 2px solid #CBD5E1 !important; }
    body.sensory-mode .top-vip-announcement,
    body.sensory-mode .floating-vip-badge { display: none !important; }

    * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Poppins', system-ui, sans-serif; -webkit-tap-highlight-color: transparent; }

    body {
      background: var(--bg-gradient);
      color: var(--text-main);
      display: flex;
      justify-content: center;
      min-height: 100vh;
      padding: 10px 10px 60px;
      transition: background 0.3s ease;
    }

    .app-container {
      width: 100%;
      max-width: 1100px;
      background: rgba(255, 255, 255, 0.98);
      backdrop-filter: blur(10px);
      border-radius: var(--radius-xl);
      box-shadow: var(--shadow-lg);
      overflow: hidden;
      display: flex;
      flex-direction: column;
      gap: 20px;
      padding-bottom: 24px;
      border: 3px solid #FFFFFF;
    }

    /* CABEÇALHO LÚDICO E RESPONSIVO */
    header {
      padding: 14px 18px;
      background: linear-gradient(135deg, #BAE6FD 0%, #E0F2FE 100%);
      display: flex;
      align-items: center;
      justify-content: space-between;
      border-radius: var(--radius-lg);
      margin: 12px 12px 0;
      box-shadow: var(--shadow-sm);
      gap: 10px;
    }
    .logo-img { max-width: 140px; height: auto; object-fit: contain; }

    .header-actions { display: flex; align-items: center; gap: 8px; }

    .action-btn-pill {
      background: #FFFFFF;
      border: 2px solid var(--primary);
      color: var(--primary-dark);
      font-weight: 800;
      font-size: 12.5px;
      padding: 8px 14px;
      border-radius: 50px;
      cursor: pointer;
      display: flex;
      align-items: center;
      gap: 6px;
      min-height: 44px;
      box-shadow: var(--shadow-sm);
      transition: transform 0.15s ease;
    }
    .action-btn-pill:active { transform: scale(0.96); }
    .action-btn-pill.muted { background: #FEE2E2; border-color: #EF4444; color: #991B1B; }

    /* MENU DE NAVEGAÇÃO PRINCIPAL */
    .page-nav {
      display: flex;
      justify-content: center;
      gap: 8px;
      background: #F0F9FF;
      padding: 6px;
      border-radius: var(--radius-lg);
      margin: 0 12px;
      border: 2px solid #BAE6FD;
      overflow-x: auto;
    }
    .nav-tab-btn {
      flex: 1;
      min-width: 80px;
      padding: 12px 8px;
      border: none;
      border-radius: var(--radius-md);
      font-weight: 800;
      font-size: 13px;
      cursor: pointer;
      background: transparent;
      color: var(--text-muted);
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 6px;
      min-height: 48px;
      white-space: nowrap;
      transition: all 0.2s ease;
    }
    .nav-tab-btn.active {
      background: var(--primary);
      color: #FFFFFF;
      box-shadow: 0 4px 14px rgba(59, 130, 246, 0.35);
    }
    .nav-tab-btn.tea-tab { background: #E0F2FE; color: var(--tea-blue); border: 2px solid #7DD3FC; }
    .nav-tab-btn.tea-tab.active { background: var(--tea-blue); color: #FFF; border-color: transparent; }
    .nav-tab-btn.vip-tab { background: #FEF3C7; color: #92400E; border: 2px solid #FCD34D; }
    .nav-tab-btn.vip-tab.active { background: linear-gradient(135deg, #F59E0B, #D97706); color: #FFF; border-color: transparent; }

    .top-vip-announcement {
      margin: 0 12px -8px;
      background: linear-gradient(135deg, #FEF3C7 0%, #FDE68A 100%);
      border: 2px dashed #F59E0B;
      border-radius: var(--radius-md);
      padding: 10px 14px;
      text-align: center;
      color: #92400E;
      font-size: 12.5px;
      font-weight: 800;
      cursor: pointer;
    }

    .page-content { display: none; flex-direction: column; gap: 20px; animation: fadeIn 0.25s ease; }
    .page-content.active-page { display: flex; }
    @keyframes fadeIn { from { opacity: 0; transform: translateY(4px); } to { opacity: 1; transform: translateY(0); } }

    /* SEÇÃO DE APRESENTAÇÃO */
    .banner-intro-grid { display: flex; flex-direction: column; gap: 16px; padding: 0 14px; }
    @media (min-width: 820px) { .banner-intro-grid { display: grid; grid-template-columns: 1fr 1.1fr; align-items: stretch; } }
    .banner-container { width: 100%; border-radius: var(--radius-lg); overflow: hidden; box-shadow: var(--shadow-sm); }
    .banner-img { width: 100%; height: 100%; min-height: 200px; display: block; object-fit: cover; }

    .intro-box {
      background: linear-gradient(135deg, #FEF3C7 0%, #FFFBEB 100%);
      border: 2.5px solid #FCD34D;
      border-radius: var(--radius-lg);
      padding: 18px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      gap: 8px;
    }
    .intro-box h2 { font-size: 18px; font-weight: 900; color: #92400E; display: flex; justify-content: space-between; align-items: center; }
    .intro-box p { font-size: 13px; color: #78350F; line-height: 1.55; font-weight: 600; }

    .btn-audio-mini {
      background: linear-gradient(135deg, #FBBF24, #F59E0B);
      border: none;
      border-radius: 50%;
      width: 38px;
      height: 38px;
      min-width: 38px;
      cursor: pointer;
      font-size: 16px;
      display: flex;
      align-items: center;
      justify-content: center;
      color: #FFF;
      box-shadow: 0 3px 8px rgba(245, 158, 11, 0.3);
    }

    /* REDES SOCIAIS */
    .social-round-section { padding: 0 14px; display: flex; justify-content: center; align-items: center; gap: 10px; flex-wrap: wrap; }
    .social-round-btn {
      width: 44px;
      height: 44px;
      border-radius: 50%;
      background: #FFF;
      border: 2px solid #E2E8F0;
      display: flex;
      align-items: center;
      justify-content: center;
      text-decoration: none;
      box-shadow: var(--shadow-sm);
      transition: transform 0.2s;
    }
    .social-round-btn:hover { transform: scale(1.08); }
    .social-round-btn img { width: 22px; height: 22px; object-fit: contain; }

    /* FAMÍLIAS & PERSONAGENS */
    .section-family-container { padding: 0 14px; display: flex; flex-direction: column; gap: 20px; }
    .family-group-title { font-size: 17px; font-weight: 900; color: var(--primary-dark); margin-bottom: 10px; display: flex; align-items: center; justify-content: space-between; }
    
    .floating-cards-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 12px; }
    @media (min-width: 768px) { .floating-cards-grid { grid-template-columns: repeat(4, 1fr); } }
    
    .floating-char-card {
      background: #FFFFFF;
      border-radius: var(--radius-lg);
      padding: 14px 10px;
      text-align: center;
      border: 3px solid #E2E8F0;
      box-shadow: var(--shadow-sm);
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 6px;
      cursor: pointer;
      transition: transform 0.2s ease, border-color 0.2s ease;
    }
    .floating-char-card:active { transform: scale(0.96); }
    .floating-char-img { width: 75px; height: 75px; object-fit: contain; border-radius: 50%; background: #F8FAFC; padding: 4px; }
    .floating-char-name { font-size: 15px; font-weight: 900; color: var(--text-main); }
    .floating-char-tag { font-size: 10px; font-weight: 800; padding: 3px 8px; border-radius: 20px; text-transform: uppercase; }
    .floating-char-desc { font-size: 11.5px; font-weight: 600; color: var(--text-muted); line-height: 1.35; display: -webkit-box; -webkit-line-clamp: 3; -webkit-box-orient: vertical; overflow: hidden; }

    .card-f1 { border-color: #F472B6; } .card-f1 .floating-char-tag { background: #FCE7F3; color: #DB2777; }
    .card-f2 { border-color: #60A5FA; } .card-f2 .floating-char-tag { background: #DBEAFE; color: #2563EB; }
    .card-avos { border-color: #FBBF24; } .card-avos .floating-char-tag { background: #FEF3C7; color: #D97706; }
    .card-especial { border-color: #A78BFA; } .card-especial .floating-char-tag { background: #EDE9FE; color: #7C3AED; }

    .char-details-box {
      margin: 0 14px;
      background: linear-gradient(135deg, #EFF6FF 0%, #FFFFFF 100%);
      border: 2.5px solid var(--primary);
      border-radius: var(--radius-lg);
      padding: 16px;
      text-align: center;
    }

    /* VÍDEOS & CARROSSEL */
    .video-section { padding: 0 14px; }
    .video-card { background: #FFFFFF; border-radius: var(--radius-lg); padding: 16px; box-shadow: var(--shadow-sm); border: 2px solid #E2E8F0; text-align: center; }
    .video-header { display: flex; align-items: center; justify-content: space-between; margin-bottom: 12px; }
    .video-header h3 { font-size: 16px; font-weight: 900; color: var(--primary-dark); }
    .video-wrapper { position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; border-radius: var(--radius-md); }
    .video-wrapper iframe { position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0; }

    /* JOGOS */
    .age-group-section { margin: 0 14px; background: #FFFFFF; border-radius: var(--radius-lg); padding: 16px; border: 2px solid #E2E8F0; box-shadow: var(--shadow-sm); }
    .age-title { font-size: 17px; font-weight: 900; color: var(--primary-dark); margin-bottom: 12px; display: flex; align-items: center; justify-content: space-between; }
    
    .conquistas-box {
      background: linear-gradient(135deg, #FEF3C7 0%, #FFFBEB 100%);
      border: 2px solid #FCD34D;
      border-radius: var(--radius-md);
      padding: 10px 14px;
      margin-bottom: 14px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      font-weight: 800;
      color: #92400E;
      font-size: 13px;
    }

    .games-subnav { display: flex; gap: 6px; background: #E0F2FE; padding: 6px; border-radius: var(--radius-md); margin-bottom: 14px; overflow-x: auto; }
    .subnav-btn {
      padding: 10px 12px;
      border: none;
      border-radius: 10px;
      font-weight: 800;
      font-size: 12px;
      cursor: pointer;
      background: #FFF;
      color: var(--primary-dark);
      min-height: 44px;
      white-space: nowrap;
    }
    .subnav-btn.active { background: var(--primary); color: #FFF; }
    .subnav-btn.vip-preview-btn { background: #FEF3C7; color: #92400E; border: 1.5px solid #FCD34D; }

    .game-section-page { display: none; } 
    .game-section-page.active-game-page { display: block; }
    .interactive-card { background: #F8FAFC; border-radius: var(--radius-md); padding: 14px; text-align: center; border: 2px solid #E2E8F0; }

    /* LOUSA MÁGICA LÚDICA */
    .brush-size-selector { display: flex; gap: 8px; justify-content: center; align-items: center; margin-bottom: 10px; }
    .btn-brush-size { background: #FFF; border: 2px solid #CBD5E1; border-radius: 10px; font-size: 12px; font-weight: 800; padding: 8px 12px; cursor: pointer; min-height: 40px; }
    .btn-brush-size.active { border-color: var(--primary); background: #E0F2FE; color: var(--primary-dark); }
    #paintCanvas { background: #FFF; border: 3px solid var(--primary); border-radius: var(--radius-lg); width: 100%; max-width: 580px; height: 280px; touch-action: none; cursor: crosshair; }
    .palette { display: flex; gap: 8px; justify-content: center; align-items: center; margin-top: 10px; flex-wrap: wrap; }
    .color-dot { width: 38px; height: 38px; border-radius: 50%; border: 3px solid #FFF; box-shadow: 0 2px 6px rgba(0,0,0,0.15); cursor: pointer; }

    .game-btn-grid { display: flex; justify-content: center; gap: 10px; flex-wrap: wrap; margin-top: 14px; }
    .btn-choice {
      background: var(--purple);
      color: #FFF;
      border: none;
      padding: 12px 20px;
      font-weight: 800;
      font-size: 16px;
      border-radius: 14px;
      cursor: pointer;
      min-width: 55px;
      min-height: 50px;
      box-shadow: 0 3px 10px rgba(139, 92, 246, 0.3);
      transition: transform 0.15s ease;
    }
    .btn-choice:active { transform: scale(0.92); }
    .btn-choice.acertou { background: #10B981 !important; transform: scale(1.08); }
    .btn-choice.errou { background: #EF4444 !important; }

    /* MEMÓRIA */
    .memory-board { display: grid; grid-template-columns: repeat(4, 1fr); gap: 8px; margin-top: 12px; max-width: 320px; margin-left: auto; margin-right: auto; }
    .memory-card { aspect-ratio: 1; background: var(--primary); border-radius: 12px; display: flex; align-items: center; justify-content: center; color: #FFF; font-weight: 900; font-size: 22px; cursor: pointer; min-height: 60px; }
    .memory-card.flipped { background: #FFF; border: 2.5px solid var(--primary); }
    .memory-card img { width: 80%; height: 80%; object-fit: contain; }

    /* ESPAÇO TEA */
    .tea-box { background: var(--tea-light); border: 2px solid #BAE6FD; border-radius: var(--radius-lg); padding: 16px; text-align: center; margin-bottom: 16px; }
    .tea-box h3 { color: var(--tea-blue); font-weight: 900; font-size: 16px; margin-bottom: 6px; }
    
    .emotion-card-grid { display: flex; gap: 10px; justify-content: center; flex-wrap: wrap; margin-top: 10px; }
    .emotion-card {
      background: #FFF;
      border: 2px solid #E2E8F0;
      border-radius: 14px;
      padding: 12px 10px;
      cursor: pointer;
      width: 90px;
      min-height: 90px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      transition: transform 0.15s ease;
    }
    .emotion-card:active { transform: scale(0.94); border-color: var(--tea-blue); }
    .emotion-card span { font-size: 32px; margin-bottom: 4px; }
    .emotion-card p { font-size: 11.5px; font-weight: 800; }

    .caa-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 8px; margin-top: 12px; }
    .caa-btn {
      background: #FFF;
      border: 2px solid #BAE6FD;
      border-radius: 14px;
      padding: 12px 6px;
      text-align: center;
      cursor: pointer;
      min-height: 75px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }
    .caa-btn:active { background: #E0F2FE; border-color: var(--tea-blue); transform: scale(0.95); }
    .caa-btn span { font-size: 26px; }
    .caa-btn p { font-size: 11px; font-weight: 800; color: var(--tea-blue); margin-top: 4px; }

    /* ÁREA VIP & PAIS */
    .vip-lock-container {
      background: linear-gradient(135deg, #FFFBEB 0%, #FEF3C7 100%);
      border: 3px solid #FCD34D;
      border-radius: var(--radius-lg);
      padding: 20px 14px;
      text-align: center;
    }
    .vip-price-tag { display: inline-block; background: #F59E0B; color: #FFF; font-weight: 900; font-size: 13.5px; padding: 6px 18px; border-radius: 30px; margin: 10px 0; }
    .vip-grid-forms { display: grid; grid-template-columns: 1fr; gap: 14px; max-width: 680px; margin: 14px auto 0; }
    @media (min-width: 640px) { .vip-grid-forms { grid-template-columns: 1fr 1fr; } }
    
    .vip-form-box { background: #FFF; padding: 14px; border-radius: var(--radius-md); border: 2px solid #FCD34D; text-align: left; }
    .vip-form-box h4 { font-size: 14px; color: #92400E; margin-bottom: 8px; font-weight: 900; }
    .vip-input { width: 100%; padding: 10px; font-size: 13px; border: 2px solid #E2E8F0; border-radius: 10px; margin-bottom: 8px; outline: none; }
    
    .btn-vip-checkout {
      background: linear-gradient(135deg, #F59E0B 0%, #D97706 100%);
      color: #FFF;
      font-weight: 800;
      font-size: 13.5px;
      padding: 12px 14px;
      border-radius: 12px;
      border: none;
      cursor: pointer;
      width: 100%;
      text-decoration: none;
      display: block;
      text-align: center;
      min-height: 46px;
    }

    /* PARENTAL GATE MODAL */
    .parent-modal {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(15, 23, 42, 0.7);
      backdrop-filter: blur(4px);
      z-index: 99999;
      justify-content: center;
      align-items: center;
      padding: 16px;
    }
    .parent-modal.active { display: flex; }
    .parent-box {
      background: #FFF;
      padding: 22px;
      border-radius: var(--radius-lg);
      text-align: center;
      max-width: 360px;
      width: 100%;
      border: 3px solid #F59E0B;
    }
    .parent-box h3 { color: #92400E; font-size: 17px; margin-bottom: 6px; font-weight: 900; }
    .parent-box p { font-size: 12.5px; color: #475569; margin-bottom: 12px; font-weight: 600; }
    .challenge-text { font-size: 20px; font-weight: 900; color: #1E293B; margin: 10px 0; }
    .challenge-input { width: 80px; padding: 8px; font-size: 18px; text-align: center; border: 2px solid #CBD5E1; border-radius: 8px; margin-bottom: 12px; font-weight: 800; }

    #visualToast {
      position: fixed;
      bottom: 14px;
      left: 50%;
      transform: translateX(-50%) translateY(100px);
      background: #0F172A;
      color: #FFF;
      padding: 10px 18px;
      border-radius: 30px;
      font-size: 12px;
      font-weight: 700;
      transition: transform 0.25s ease;
      z-index: 999999;
      pointer-events: none;
    }
    #visualToast.show { transform: translateX(-50%) translateY(0); }

    .floating-vip-badge {
      position: fixed;
      bottom: 14px;
      right: 14px;
      background: linear-gradient(135deg, #F59E0B 0%, #D97706 100%);
      color: #FFF;
      padding: 8px 14px;
      border-radius: 50px;
      font-size: 12px;
      font-weight: 800;
      box-shadow: 0 4px 14px rgba(245, 158, 11, 0.35);
      display: flex;
      align-items: center;
      gap: 6px;
      cursor: pointer;
      border: 2px solid #FDE68A;
      z-index: 999;
    }

    footer { text-align: center; padding: 14px 14px 6px; border-top: 1px solid #E2E8F0; font-size: 11.5px; color: var(--text-muted); font-weight: 600; }
  </style>
</head>
<body onclick="desbloquearAudioMobileOnce()">

  <div id="visualToast">Aviso do sistema</div>

  <!-- PARENTAL GATE (PROTEÇÃO PARA ÁREA DOS PAIS / VIP) -->
  <div id="modalParentalGate" class="parent-modal">
    <div class="parent-box">
      <h3>🔒 Espaço dos Responsáveis</h3>
      <p>Para abrir as configurações e Área VIP, resolva o desafio matemático:</p>
      <div id="desafioMatematicoTexto" class="challenge-text">3 + 4 = ?</div>
      <input type="number" id="respostaDesafio" class="challenge-input" placeholder="?">
      <div style="display: flex; gap: 8px; justify-content: center;">
        <button onclick="fecharParentalGate()" style="padding: 10px 14px; border: none; border-radius: 8px; background: #E2E8F0; font-weight: 800; cursor: pointer;">Voltar</button>
        <button onclick="verificarParentalGate()" style="padding: 10px 18px; border: none; border-radius: 8px; background: #F59E0B; color: #FFF; font-weight: 800; cursor: pointer;">Entrar ➔</button>
      </div>
    </div>
  </div>

  <div class="floating-vip-badge" onclick="abrirAreaProtegida('vip')">
    <span>⭐</span>
    <span>Área VIP (R$ 6,00)</span>
  </div>

  <div class="app-container">

    <header>
      <a href="https://www.youtube.com/@turminhaxe_xeu" target="_blank" title="YouTube da Turminha">
        <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908275/TURMINHA_LOGO.png" alt="Logo Turminha do Xexéu" class="logo-img">
      </a>
      <div class="header-actions">
        <button id="btnSensoryHeader" class="action-btn-pill" onclick="toggleSensoryMode()">
          <span>🌿</span> Modo Calmo
        </button>
        <button id="toggleAudioBtn" class="action-btn-pill" onclick="alternarAudioGlobal()">
          <span id="audioIcon">🔊</span>
          <span id="audioText">Voz</span>
        </button>
      </div>
    </header>

    <nav class="page-nav">
      <button id="btn-tab-inicio" class="nav-tab-btn active" onclick="mudarPagina('inicio')">🏠 Início</button>
      <button id="btn-tab-videos" class="nav-tab-btn" onclick="mudarPagina('videos')">🎬 Vídeos</button>
      <button id="btn-tab-jogos" class="nav-tab-btn" onclick="mudarPagina('jogos')">🎮 Jogos</button>
      <button id="btn-tab-tea" class="nav-tab-btn tea-tab" onclick="mudarPagina('tea')">🧩 Espaço TEA</button>
      <button id="btn-tab-vip" class="nav-tab-btn vip-tab" onclick="abrirAreaProtegida('vip')">⭐ Área VIP</button>
    </nav>

    <div class="top-vip-announcement" onclick="abrirAreaProtegida('vip')">
      <span>⭐ Desbloqueie todo o Drive Pedagógico e Ferramentas TEA por R$ 6,00/mês! 💖</span>
    </div>

    <!-- PÁGINA 1: INÍCIO -->
    <main id="pagina-inicio" class="page-content active-page">
      <section class="banner-intro-grid">
        <div class="banner-container">
          <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786906934/Banner_para_youtube_streamer_de_jogos_rosa_feminino_e_delicado.png" alt="Capa da Turminha do Xexéu" class="banner-img">
        </div>
        <div class="intro-box">
          <h2>
            <span>✨ Educando com Amor</span>
            <button class="btn-audio-mini" onclick="lerTexto('Mais do que um nome divertido, a Turminha do Xexéu é o nosso jeito de honrar as raízes e a história da nossa família.')" title="Ouvir">🔊</button>
          </h2>
          <p>Mais do que um nome divertido, a <strong>Turminha do Xexéu</strong> é o nosso jeito de honrar as raízes e a história da nossa família.</p>
          <p>O nome <strong>Xexéu</strong> homenageia <em>Mariano Xexéu</em> e seu filho <em>Pedro Mariano</em> (o <strong>Vovô Beto</strong>). A <strong>Vovó Hilda</strong> é inspirada na doce <em>Astrogilda Grispym</em>.</p>
        </div>
      </section>

      <section class="social-round-section">
        <a href="https://www.youtube.com/@turminhaxe_xeu" target="_blank" class="social-round-btn" title="YouTube"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908275/YT.png" alt="YouTube"></a>
        <a href="https://www.instagram.com/turminhaxe_xeu" target="_blank" class="social-round-btn" title="Instagram"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908273/INDTAGRAM.png" alt="Instagram"></a>
        <a href="https://www.tiktok.com/@turminhaxe_xeu" target="_blank" class="social-round-btn" title="TikTok"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908275/TIKTOK.png" alt="TikTok"></a>
        <a href="https://open.spotify.com/intl-pt/artist/6ykKQ3uP6Wl2REylKJAdJ6" target="_blank" class="social-round-btn" title="Spotify"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908274/SPOTIFY.png" alt="Spotify"></a>
      </section>

      <section class="section-family-container">
        <div>
          <h3 class="family-group-title">
            <span>✨ Mascotes Oficiais</span>
            <button class="btn-audio-mini" onclick="lerTexto('Conheça os mascotes oficiais da Turminha!')">🔊</button>
          </h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-especial" onclick="tocarVozETexto('Xexéu')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786902347/xexeu.png" class="floating-char-img" alt="Xexéu">
              <span class="floating-char-name">Xexéu</span>
              <span class="floating-char-tag">Mascote Oficial</span>
              <p class="floating-char-desc">Pássaro azul de boina amarela. Guardião alegre da nossa história!</p>
            </div>
            <div class="floating-char-card card-especial" onclick="tocarVozETexto('Capilé')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786902348/capile.png" class="floating-char-img" alt="Capilé">
              <span class="floating-char-name">Capilé</span>
              <span class="floating-char-tag">O Companheiro</span>
              <p class="floating-char-desc">Cachorrinho fofo de coleira azul e pingente de osso dourado.</p>
            </div>
          </div>
        </div>

        <div>
          <h3 class="family-group-title">
            <span>💖 Casa da Maya e do Theo</span>
            <button class="btn-audio-mini" onclick="lerTexto('A Casa da Maya e do Theo.')">🔊</button>
          </h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-f1" onclick="tocarVozETexto('Maya')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786907604/16.png" class="floating-char-img" alt="Maya">
              <span class="floating-char-name">Maya</span>
              <span class="floating-char-tag">Mãe & Guia</span>
              <p class="floating-char-desc">Organizada, amorosa e porto seguro das filhas.</p>
            </div>
            <div class="floating-char-card card-f1" onclick="tocarVozETexto('Theo')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786907605/17.png" class="floating-char-img" alt="Theo">
              <span class="floating-char-name">Theo</span>
              <span class="floating-char-tag">Pai Protetor</span>
              <p class="floating-char-desc">Calmo, paciente e sempre pronto para acolher.</p>
            </div>
            <div class="floating-char-card card-f1" onclick="tocarVozETexto('Nina')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786903228/Sem_nome_512_x_512_px_1.png" class="floating-char-img" alt="Nina">
              <span class="floating-char-name">Nina</span>
              <span class="floating-char-tag">Super Esperta</span>
              <p class="floating-char-desc">Cabelos cacheados e muita curiosidade para aprender.</p>
            </div>
            <div class="floating-char-card card-f1" onclick="tocarVozETexto('Iza')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786902350/iza.png" class="floating-char-img" alt="Iza">
              <span class="floating-char-name">Iza</span>
              <span class="floating-char-tag">A Vaidosa</span>
              <p class="floating-char-desc">Vestidinho rosa, doce e charmosa por onde passa.</p>
            </div>
          </div>
        </div>

        <div>
          <h3 class="family-group-title">
            <span>⚡ Casa do Sam e da Lia</span>
            <button class="btn-audio-mini" onclick="lerTexto('A Casa do Sam e da Lia.')">🔊</button>
          </h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-f2" onclick="tocarVozETexto('Sam')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786907601/14.png" class="floating-char-img" alt="Sam">
              <span class="floating-char-name">Sam</span>
              <span class="floating-char-tag">Pai Inventor</span>
              <p class="floating-char-desc">Adora inventar brinquedos com os filhos.</p>
            </div>
            <div class="floating-char-card card-f2" onclick="tocarVozETexto('Lia')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786907602/15.png" class="floating-char-img" alt="Lia">
              <span class="floating-char-name">Lia</span>
              <span class="floating-char-tag">Mãe Alegria</span>
              <p class="floating-char-desc">Estilosa, alegre e cheia de energia positiva.</p>
            </div>
            <div class="floating-char-card card-f2" onclick="tocarVozETexto('Joca')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786902350/joca.png" class="floating-char-img" alt="Joca">
              <span class="floating-char-name">Joca</span>
              <span class="floating-char-tag">O Divertido</span>
              <p class="floating-char-desc">Menino de camiseta verde, engraçado e leal.</p>
            </div>
            <div class="floating-char-card card-f2" onclick="tocarVozETexto('Leo')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786902347/leo.png" class="floating-char-img" alt="Leo">
              <span class="floating-char-name">Leo</span>
              <span class="floating-char-tag">Explorador Focado</span>
              <p class="floating-char-desc">Atento aos detalhes e grande explorador com o coração puro.</p>
            </div>
          </div>
        </div>

        <div>
          <h3 class="family-group-title">
            <span>👵👴 Os Avós</span>
            <button class="btn-audio-mini" onclick="lerTexto('Os queridos Vovô Beto e Vovó Hilda.')">🔊</button>
          </h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-avos" onclick="tocarVozETexto('Beto')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786902348/vovo_beto.png" class="floating-char-img" alt="Vovô Beto">
              <span class="floating-char-name">Vovô Beto</span>
              <span class="floating-char-tag">Vovô Coruja</span>
              <p class="floating-char-desc">Óculos quadrados, risada solta e muita paciência.</p>
            </div>
            <div class="floating-char-card card-avos" onclick="tocarVozETexto('Hilda')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786902347/vovo_hilda.png" class="floating-char-img" alt="Vovó Hilda">
              <span class="floating-char-name">Vovó Hilda</span>
              <span class="floating-char-tag">Vovó Acolhedora</span>
              <p class="floating-char-desc">Óculos redondos e os abraços mais doces do mundo.</p>
            </div>
          </div>
        </div>
      </section>

      <section class="char-details-box" id="detalhes-personagem">
        <h3 id="detalhe-nome" style="color: var(--primary-dark); font-weight: 900; font-size: 15px;">Toque em um personagem acima para ouvir sua história!</h3>
        <p id="detalhe-texto" style="font-weight: 600; color: var(--text-muted); margin-top: 4px; font-size: 12.5px;">A voz da Turminha vai apresentar cada amiguinho para você!</p>
      </section>
    </main>

    <!-- PÁGINA 2: VÍDEOS -->
    <main id="pagina-videos" class="page-content">
      <section class="video-section">
        <div class="video-card">
          <div class="video-header">
            <h3>🎬 Episódios Oficiais da Turminha</h3>
            <button class="btn-audio-mini" onclick="lerTexto('Assista aos episódios da Turminha do Xexéu!')">🔊</button>
          </div>
          <div class="video-wrapper">
            <iframe src="https://www.youtube-nocookie.com/embed/videosseries?list=PLh42qmbnReoE_pM4lig3DpJaNGWqoT9uJ" allowfullscreen></iframe>
          </div>
        </div>
      </section>
    </main>

    <!-- PÁGINA 3: JOGOS -->
    <main id="pagina-jogos" class="page-content">
      <div class="age-group-section">
        <h3 class="age-title">
          <span>🎮 Jogos da Turminha</span>
          <button class="btn-audio-mini" onclick="lerTexto('Vamos brincar com os jogos da Turminha!')">🔊</button>
        </h3>
        
        <div class="conquistas-box">
          <span>🏆 Pontos: <strong id="placar-pontos">0</strong></span>
          <span id="medalha-status">⭐ Amigo da Turminha</span>
        </div>

        <nav class="games-subnav">
          <button id="subtab-lousa" class="subnav-btn active" onclick="mudarSubJogo('lousa')">🎨 Lousa</button>
          <button id="subtab-contar" class="subnav-btn" onclick="mudarSubJogo('contar')">🔢 Contar</button>
          <button id="subtab-letras" class="subnav-btn" onclick="mudarSubJogo('letras')">🔤 Letras</button>
          <button id="subtab-memoria" class="subnav-btn" onclick="mudarSubJogo('memoria')">🧠 Memória</button>
          <button id="subtab-quiz" class="subnav-btn" onclick="mudarSubJogo('quiz')">❓ Quiz</button>
        </nav>

        <!-- LOUSA MÁGICA -->
        <div id="game-lousa" class="game-section-page active-game-page interactive-card">
          <h4 style="font-weight: 800; margin-bottom: 8px; font-size: 15px;">🎨 Desenhe e Pinte</h4>
          <div class="brush-size-selector">
            <button class="btn-brush-size active" onclick="definirTamanhoPincel(4, this)">Fino ✏️</button>
            <button class="btn-brush-size" onclick="definirTamanhoPincel(8, this)">Médio 🖌️</button>
            <button class="btn-brush-size" onclick="definirTamanhoPincel(16, this)">Grosso 🖍️</button>
          </div>
          <canvas id="paintCanvas"></canvas>
          <div class="palette">
            <div class="color-dot" style="background: #3B82F6;" onclick="mudarCor('#3B82F6')"></div>
            <div class="color-dot" style="background: #EF4444;" onclick="mudarCor('#EF4444')"></div>
            <div class="color-dot" style="background: #10B981;" onclick="mudarCor('#10B981')"></div>
            <div class="color-dot" style="background: #F59E0B;" onclick="mudarCor('#F59E0B')"></div>
            <div class="color-dot" style="background: #8B5CF6;" onclick="mudarCor('#8B5CF6')"></div>
            <button onclick="limparCanvas()" style="padding: 8px 12px; font-weight: 800; border-radius: 10px; border: none; background: #FEE2E2; color: #DC2626; cursor: pointer; font-size: 12px; min-height: 40px;">Limpar 🗑️</button>
            <button onclick="salvarFotoDesenho()" style="padding: 8px 12px; font-weight: 800; border-radius: 10px; border: none; background: #D1FAE5; color: #065F46; cursor: pointer; font-size: 12px; min-height: 40px;">Salvar 📸</button>
          </div>
        </div>

        <!-- CONTAR -->
        <div id="game-contar" class="game-section-page interactive-card">
          <h4 style="font-weight: 800; font-size: 16px; margin-bottom: 4px;">🔢 Quantos Amigos Têm Aqui?</h4>
          <div id="countDisplay" style="display: flex; justify-content: center; align-items: center; gap: 8px; margin: 16px 0; min-height: 70px; flex-wrap: wrap;"></div>
          <div id="countOptions" class="game-btn-grid"></div>
        </div>

        <!-- LETRAS -->
        <div id="game-letras" class="game-section-page interactive-card">
          <h4 style="font-weight: 800; font-size: 16px; margin-bottom: 4px;">🔤 Primeira Letra do Nome</h4>
          <p style="font-size: 13px; font-weight: 700; margin-top: 4px;">Nome: <strong id="nome-letra-personagem" style="color: var(--purple);">Xexéu</strong></p>
          <img id="img-letra-personagem" src="" alt="Personagem" style="width: 85px; height: 85px; object-fit: contain; margin: 10px 0;">
          <div id="opcoes-letras" class="game-btn-grid"></div>
        </div>

        <!-- MEMÓRIA -->
        <div id="game-memoria" class="game-section-page interactive-card">
          <h4 style="font-weight: 800; font-size: 16px; margin-bottom: 4px;">🧠 Jogo da Memória</h4>
          <p style="font-size: 12px; color: var(--text-muted);">Ache os pares dos personagens!</p>
          <div id="memoryBoard" class="memory-board"></div>
        </div>

        <!-- QUIZ -->
        <div id="game-quiz" class="game-section-page interactive-card">
          <h4 style="font-weight: 800; font-size: 16px; margin-bottom: 6px;">❓ Quem é este Personagem?</h4>
          <img id="quiz-img" src="" alt="Quiz" style="width: 80px; height: 80px; object-fit: contain; margin: 8px 0;">
          <div id="quiz-options" class="game-btn-grid"></div>
        </div>
      </div>
    </main>

    <!-- PÁGINA 4: ESPAÇO TEA -->
    <main id="pagina-tea" class="page-content">
      <div class="age-group-section">
        <div class="tea-box">
          <h3>🧩 Espaço Aconchegante e TEA</h3>
          <p style="font-size: 12px; color: #475569; font-weight: 600;">Ambiente tranquilo para expressar sentimentos e apoiar a comunicação.</p>
        </div>

        <div class="interactive-card" style="border-color: #BAE6FD; margin-bottom: 16px;">
          <h4 style="color: var(--tea-blue); font-weight: 800; font-size: 15px; margin-bottom: 10px;">Como você está se sentindo agora?</h4>
          <div class="emotion-card-grid">
            <div class="emotion-card" onclick="responderMinhaEmocao('Feliz')">
              <span>😄</span>
              <p style="color: #16A34A;">Feliz</p>
            </div>
            <div class="emotion-card" onclick="responderMinhaEmocao('Calmo')">
              <span>😌</span>
              <p style="color: var(--tea-blue);">Calmo</p>
            </div>
            <div class="emotion-card" onclick="responderMinhaEmocao('Triste')">
              <span>😢</span>
              <p style="color: #475569;">Triste</p>
            </div>
            <div class="emotion-card" onclick="responderMinhaEmocao('Bravo')">
              <span>😤</span>
              <p style="color: #DC2626;">Bravo</p>
            </div>
          </div>
        </div>

        <div class="interactive-card" style="border-color: #BAE6FD;">
          <h4 style="color: var(--tea-blue); font-weight: 800; font-size: 15px; margin-bottom: 8px;">Toque no Cartão para Falar (CAA):</h4>
          <div class="caa-grid">
            <div class="caa-btn" onclick="lerTexto('Eu quero água, por favor.')"><span>💧</span><p>Água</p></div>
            <div class="caa-btn" onclick="lerTexto('Estou com fome.')"><span>🍎</span><p>Comer</p></div>
            <div class="caa-btn" onclick="lerTexto('Preciso ir ao banheiro.')"><span>🚽</span><p>Banheiro</p></div>
            <div class="caa-btn" onclick="lerTexto('Quero brincar.')"><span>🧸</span><p>Brincar</p></div>
            <div class="caa-btn" onclick="lerTexto('Quero descansar.')"><span>💤</span><p>Descansar</p></div>
            <div class="caa-btn" onclick="lerTexto('Preciso de um abraço.')"><span>🤗</span><p>Abraço</p></div>
          </div>
        </div>
      </div>
    </main>

    <!-- PÁGINA 5: ÁREA VIP (PAIS & ASSINANTES) -->
    <main id="pagina-vip" class="page-content">
      <div class="age-group-section">
        <div class="vip-lock-container">
          <h3>⭐ Clube VIP da Turminha do Xexéu</h3>
          <div class="vip-price-tag">Assinatura: R$ 6,00 / mês</div>
          <p style="font-size: 12.5px; color: #78350F; font-weight: 600; line-height: 1.5; margin-bottom: 12px;">
            Apoie a produção independente da Turminha e desbloqueie o Drive Completo de Atividades para Impressão, Temporizador Expandido e Pranchas Editáveis de Rotina e Comunicação!
          </p>

          <div class="vip-grid-forms">
            <div class="vip-form-box">
              <h4>✨ Quero Assinar o VIP</h4>
              <input type="email" id="cad-email" class="vip-input" placeholder="Seu e-mail">
              <input type="password" id="cad-senha" class="vip-input" placeholder="Crie uma senha de acesso">
              <a href="https://pay.kiwify.com.br/avOqrEg" target="_blank" class="btn-vip-checkout" onclick="salvarECadastrar()">Assinar por R$ 6,00 💳</a>
            </div>

            <div class="vip-form-box" style="border-color: #CBD5E1;">
              <h4 style="color: #1E293B;">🔑 Já sou Assinante</h4>
              <input type="email" id="log-email" class="vip-input" placeholder="E-mail cadastrado">
              <input type="password" id="log-senha" class="vip-input" placeholder="Sua senha">
              <button onclick="fazerLogin()" style="width:100%; padding: 11px; background: #3B82F6; color: #FFF; border: none; border-radius: 10px; font-weight: 800; cursor: pointer; min-height: 46px;">Entrar no Painel</button>
            </div>
          </div>
        </div>
      </div>
    </main>

    <footer>
      <span>© Turminha do Xexéu — Todos os direitos reservados</span>
    </footer>

  </div>

  <script>
    let audioAtivo = true;
    let audioUnlocked = false;
    let pontosConquista = parseInt(localStorage.getItem('turminha_pontos') || '0');
    let desafioResultadoEsperado = 0;
    let destinoAposGate = 'vip';

    const SENHA_MESTRA = "65628467";

    const PERSONAGENS = [
      { nome: 'Xexéu', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786902347/xexeu.png', letra: 'X', desc: 'O pássaro azul de boina amarela! O guardião alegre da história.' },
      { nome: 'Capilé', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786902348/capile.png', letra: 'C', desc: 'O cachorrinho fofo com coleira azul e pingente de osso dourado!' },
      { nome: 'Maya', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786907604/16.png', letra: 'M', desc: 'A mãe dedicada da Iza e da Nina, amorosa e atenciosa.' },
      { nome: 'Theo', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786907605/17.png', letra: 'T', desc: 'O pai paciente e calmo da Iza e da Nina.' },
      { nome: 'Nina', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786903228/Sem_nome_512_x_512_px_1.png', letra: 'N', desc: 'A menina super esperta de cabelos cacheados!' },
      { nome: 'Iza', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786902350/iza.png', letra: 'I', desc: 'A vaidosa da Turminha, de vestido rosa e coração doce.' },
      { nome: 'Sam', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786907601/14.png', letra: 'S', desc: 'O pai inventor do Joca e do Leo, adora brincadeiras!' },
      { nome: 'Lia', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786907602/15.png', letra: 'L', desc: 'A mãe cheia de energia e alegria do Joca e do Leo.' },
      { nome: 'Joca', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786902350/joca.png', letra: 'J', desc: 'O garoto engraçado de camiseta verde!' },
      { nome: 'Leo', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786902347/leo.png', letra: 'L', desc: 'O explorador detalhista e focado nas descobertas.' },
      { nome: 'Beto', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786902348/vovo_beto.png', letra: 'B', desc: 'O Vovô Beto, de óculos quadrados e risada boa!' },
      { nome: 'Hilda', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786902347/vovo_hilda.png', letra: 'H', desc: 'A Vovó Hilda, de óculos redondos e abraços acolhedores.' }
    ];

    function lerTexto(texto) {
      exibirToast(texto);
      if (!audioAtivo || !('speechSynthesis' in window)) return;
      try {
        window.speechSynthesis.cancel();
        const u = new SpeechSynthesisUtterance(texto);
        u.lang = 'pt-BR';
        u.rate = 1.0;
        u.pitch = 1.05;
        window.speechSynthesis.speak(u);
      } catch (e) {}
    }

    function desbloquearAudioMobileOnce() {
      if (!audioUnlocked && 'speechSynthesis' in window) {
        window.speechSynthesis.speak(new SpeechSynthesisUtterance(""));
        audioUnlocked = true;
      }
    }

    function tocarVozETexto(nome) {
      const p = PERSONAGENS.find(x => x.nome === nome);
      if (!p) return;
      document.getElementById('detalhe-nome').innerText = p.nome;
      document.getElementById('detalhe-texto').innerText = p.desc;
      lerTexto(p.desc);
    }

    function alternarAudioGlobal() {
      audioAtivo = !audioAtivo;
      const btn = document.getElementById('toggleAudioBtn');
      if (audioAtivo) {
        btn.classList.remove('muted');
        document.getElementById('audioIcon').innerText = '🔊';
        lerTexto("Voz ligada!");
      } else {
        if ('speechSynthesis' in window) window.speechSynthesis.cancel();
        btn.classList.add('muted');
        document.getElementById('audioIcon').innerText = '🔇';
        exibirToast("Voz desligada!");
      }
    }

    function toggleSensoryMode() {
      const ativado = document.body.classList.toggle('sensory-mode');
      const btn = document.getElementById('btnSensoryHeader');
      btn.innerHTML = ativado ? '🌿 Normal' : '🌿 Modo Calmo';
      lerTexto(ativado ? "Modo Calmo ativado" : "Modo normal ativado");
    }

    function exibirToast(t) {
      const toast = document.getElementById('visualToast');
      if (!toast) return;
      toast.innerText = t;
      toast.classList.add('show');
      setTimeout(() => toast.classList.remove('show'), 2200);
    }

    /* PARENTAL GATE */
    function abrirAreaProtegida(destino) {
      destinoAposGate = destino;
      const n1 = Math.floor(Math.random() * 5) + 2;
      const n2 = Math.floor(Math.random() * 4) + 1;
      desafioResultadoEsperado = n1 + n2;
      document.getElementById('desafioMatematicoTexto').innerText = `${n1} + ${n2} = ?`;
      document.getElementById('respostaDesafio').value = '';
      document.getElementById('modalParentalGate').classList.add('active');
    }

    function fecharParentalGate() {
      document.getElementById('modalParentalGate').classList.remove('active');
    }

    function verificarParentalGate() {
      const resp = parseInt(document.getElementById('respostaDesafio').value);
      if (resp === desafioResultadoEsperado) {
        fecharParentalGate();
        mudarPagina(destinoAposGate);
        lerTexto("Acesso liberado aos responsáveis.");
      } else {
        alert("Resposta incorreta! Tente novamente.");
        abrirAreaProtegida(destinoAposGate);
      }
    }

    function mudarPagina(p) {
      ['inicio', 'videos', 'jogos', 'tea', 'vip'].forEach(id => {
        const el = document.getElementById('pagina-' + id);
        const tab = document.getElementById('btn-tab-' + id);
        if (el) el.classList.remove('active-page');
        if (tab) tab.classList.remove('active');
      });
      const target = document.getElementById('pagina-' + p);
      const targetTab = document.getElementById('btn-tab-' + p);
      if (target) target.classList.add('active-page');
      if (targetTab) targetTab.classList.add('active');
      
      if (p === 'jogos') setTimeout(redimensionarCanvas, 50);
    }

    function mudarSubJogo(sub) {
      ['lousa', 'contar', 'letras', 'memoria', 'quiz'].forEach(s => {
        const el = document.getElementById('game-' + s);
        const tab = document.getElementById('subtab-' + s);
        if (el) el.classList.remove('active-game-page');
        if (tab) tab.classList.remove('active');
      });
      const target = document.getElementById('game-' + sub);
      const tabTarget = document.getElementById('subtab-' + sub);
      if (target) target.classList.add('active-game-page');
      if (tabTarget) tabTarget.classList.add('active');
      if (sub === 'lousa') setTimeout(redimensionarCanvas, 50);
    }

    function responderMinhaEmocao(e) {
      if (e === 'Feliz') lerTexto("Que coisa maravilhosa estar feliz!");
      else if (e === 'Calmo') lerTexto("Que momento bom e tranquilo.");
      else if (e === 'Triste') lerTexto("Tudo bem ficar triste. A Turminha te dá um abraço quentinho.");
      else if (e === 'Bravo') lerTexto("Vamos respirar bem fundo juntos e acalmar o coração.");
    }

    /* CANVAS / LOUSA */
    const canvas = document.getElementById('paintCanvas');
    const ctx = canvas ? canvas.getContext('2d') : null;
    let desenhando = false, corAtual = '#3B82F6', tamanhoPincel = 4;

    function redimensionarCanvas() {
      if (!canvas || !canvas.parentElement) return;
      canvas.width = canvas.parentElement.clientWidth - 28;
      canvas.height = window.innerWidth > 600 ? 320 : 250;
    }

    function definirTamanhoPincel(tam, btn) {
      tamanhoPincel = tam;
      document.querySelectorAll('.btn-brush-size').forEach(b => b.classList.remove('active'));
      if (btn) btn.classList.add('active');
    }

    function mudarCor(c) { corAtual = c; }
    function limparCanvas() { if (ctx) ctx.clearRect(0, 0, canvas.width, canvas.height); }

    function salvarFotoDesenho() {
      const link = document.createElement('a');
      link.download = 'meu-desenho-turminha.png';
      link.href = canvas.toDataURL();
      link.click();
      lerTexto("Desenho guardado com sucesso!");
    }

    function getPos(e) {
      const rect = canvas.getBoundingClientRect();
      const cx = e.touches ? e.touches[0].clientX : e.clientX;
      const cy = e.touches ? e.touches[0].clientY : e.clientY;
      return { x: cx - rect.left, y: cy - rect.top };
    }

    if (canvas) {
      const iniciar = (e) => { desenhando = true; const p = getPos(e); ctx.beginPath(); ctx.moveTo(p.x, p.y); ctx.strokeStyle = corAtual; ctx.lineWidth = tamanhoPincel; ctx.lineCap = 'round'; };
      const mover = (e) => { if (!desenhando) return; const p = getPos(e); ctx.lineTo(p.x, p.y); ctx.stroke(); if(e.preventDefault) e.preventDefault(); };
      const parar = () => { desenhando = false; };
      
      canvas.addEventListener('mousedown', iniciar);
      canvas.addEventListener('mousemove', mover);
      canvas.addEventListener('mouseup', parar);
      canvas.addEventListener('touchstart', iniciar, { passive: false });
      canvas.addEventListener('touchmove', mover, { passive: false });
      canvas.addEventListener('touchend', parar);
    }

    /* JOGO: CONTAR */
    let qContar = 0;
    function carregarJogoContar() {
      qContar = Math.floor(Math.random() * 4) + 1;
      const char = PERSONAGENS[Math.floor(Math.random() * PERSONAGENS.length)];
      const display = document.getElementById('countDisplay');
      if (!display) return;
      display.innerHTML = '';
      for (let i = 0; i < qContar; i++) {
        const img = document.createElement('img');
        img.src = char.img;
        img.style.cssText = 'width:48px; height:48px; object-fit:contain;';
        display.appendChild(img);
      }
      const opts = document.getElementById('countOptions');
      opts.innerHTML = '';
      for (let n = 1; n <= 4; n++) {
        const btn = document.createElement('button');
        btn.className = 'btn-choice';
        btn.innerText = n;
        btn.onclick = () => {
          if (n === qContar) {
            btn.classList.add('acertou');
            lerTexto("Parabéns! Você acertou!");
            adicionarPontos(5);
            setTimeout(() => { btn.classList.remove('acertou'); carregarJogoContar(); }, 700);
          } else {
            btn.classList.add('errou');
            lerTexto("Tente de novo!");
            setTimeout(() => btn.classList.remove('errou'), 400);
          }
        };
        opts.appendChild(btn);
      }
    }

    /* JOGO: LETRAS */
    let pLetraAtual = null;
    function carregarJogoLetra() {
      pLetraAtual = PERSONAGENS[Math.floor(Math.random() * PERSONAGENS.length)];
      document.getElementById('nome-letra-personagem').innerText = pLetraAtual.nome;
      document.getElementById('img-letra-personagem').src = pLetraAtual.img;
      const container = document.getElementById('opcoes-letras');
      container.innerHTML = '';
      const alfabeto = ['A', 'B', 'C', 'D', 'E', 'F', 'I', 'J', 'L', 'M', 'N', 'P', 'S', 'T', 'X'];
      let opcoes = [pLetraAtual.letra];
      while (opcoes.length < 3) {
        let l = alfabeto[Math.floor(Math.random() * alfabeto.length)];
        if (!opcoes.includes(l)) opcoes.push(l);
      }
      opcoes.sort(() => Math.random() - 0.5).forEach(l => {
        const btn = document.createElement('button');
        btn.className = 'btn-choice';
        btn.innerText = l;
        btn.onclick = () => {
          if (l === pLetraAtual.letra) {
            btn.classList.add('acertou');
            lerTexto("Muito bem!");
            adicionarPontos(5);
            setTimeout(() => { btn.classList.remove('acertou'); carregarJogoLetra(); }, 700);
          } else {
            btn.classList.add('errou');
            lerTexto("Tente outra vez!");
            setTimeout(() => btn.classList.remove('errou'), 400);
          }
        };
        container.appendChild(btn);
      });
    }

    /* JOGO: MEMÓRIA */
    let cMem = [], pCarta = null, travaMem = false, acertosMem = 0;
    function iniciarMemoria() {
      acertosMem = 0;
      const sorteados = [...PERSONAGENS].sort(() => Math.random() - 0.5).slice(0, 4);
      const imgs = sorteados.map(p => p.img);
      cMem = [...imgs, ...imgs].sort(() => Math.random() - 0.5);
      const board = document.getElementById('memoryBoard');
      if (!board) return;
      board.innerHTML = '';
      cMem.forEach(src => {
        const card = document.createElement('div');
        card.className = 'memory-card';
        card.dataset.img = src;
        card.innerText = '❓';
        card.onclick = () => {
          if (travaMem || card.classList.contains('flipped')) return;
          card.classList.add('flipped');
          card.innerHTML = `<img src="${src}" alt="Carta">`;
          if (!pCarta) pCarta = card;
          else {
            if (pCarta.dataset.img === src) {
              acertosMem++;
              lerTexto("Achou o par!");
              pCarta = null;
              adicionarPontos(3);
              if (acertosMem === 4) {
                adicionarPontos(10);
                setTimeout(iniciarMemoria, 1500);
              }
            } else {
              travaMem = true;
              setTimeout(() => {
                pCarta.classList.remove('flipped');
                pCarta.innerText = '❓';
                card.classList.remove('flipped');
                card.innerText = '❓';
                pCarta = null;
                travaMem = false;
              }, 800);
            }
          }
        };
        board.appendChild(card);
      });
    }

    /* JOGO: QUIZ */
    function carregarQuiz() {
      const pAtual = PERSONAGENS[Math.floor(Math.random() * PERSONAGENS.length)];
      document.getElementById('quiz-img').src = pAtual.img;
      const container = document.getElementById('quiz-options');
      container.innerHTML = '';
      let opcoes = [pAtual.nome];
      while (opcoes.length < 3) {
        let o = PERSONAGENS[Math.floor(Math.random() * PERSONAGENS.length)].nome;
        if (!opcoes.includes(o)) opcoes.push(o);
      }
      opcoes.sort(() => Math.random() - 0.5).forEach(o => {
        const btn = document.createElement('button');
        btn.className = 'btn-choice';
        btn.style.fontSize = '14px';
        btn.innerText = o;
        btn.onclick = () => {
          if (o === pAtual.nome) {
            btn.classList.add('acertou');
            lerTexto("Isso mesmo!");
            adicionarPontos(5);
            setTimeout(() => { btn.classList.remove('acertou'); carregarQuiz(); }, 700);
          } else {
            btn.classList.add('errou');
            lerTexto("Tente novamente!");
            setTimeout(() => btn.classList.remove('errou'), 400);
          }
        };
        container.appendChild(btn);
      });
    }

    function adicionarPontos(n) {
      pontosConquista += n;
      localStorage.setItem('turminha_pontos', pontosConquista);
      document.getElementById('placar-pontos').innerText = pontosConquista;
      const med = document.getElementById('medalha-status');
      if (pontosConquista >= 50) med.innerText = "🌟 Super Fã Mestre";
      else if (pontosConquista >= 20) med.innerText = "⭐ Explorador Experiente";
    }

    function salvarECadastrar() {
      const email = document.getElementById('cad-email').value.trim();
      const senha = document.getElementById('cad-senha').value.trim();
      if (!email || !senha) alert("Preencha o e-mail e crie a senha!");
    }

    function fazerLogin() {
      const senha = document.getElementById('log-senha').value.trim();
      if (senha === SENHA_MESTRA) {
        alert("Acesso Mestre Liberado!");
        lerTexto("Bem-vindo de volta!");
      } else {
        alert("Senha incorreta ou assinatura pendente.");
      }
    }

    window.onload = () => {
      document.getElementById('placar-pontos').innerText = pontosConquista;
      carregarJogoContar();
      carregarJogoLetra();
      iniciarMemoria();
      carregarQuiz();
    };
    window.onresize = redimensionarCanvas;
  </script>
</body>
</html>
