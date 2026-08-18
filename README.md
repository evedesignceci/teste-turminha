<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Turminha do Xexéu — Portal Oficial</title>
  
  <link rel="icon" type="image/png" href="https://res.cloudinary.com/oactqmgs/image/upload/v1786908275/TURMINHA_LOGO.png">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700;800;900&display=swap" rel="stylesheet">
  
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
      --radius-xl: 32px; 
      --radius-lg: 20px; 
      --radius-md: 14px;
      --shadow-sm: 0 6px 16px rgba(15, 23, 42, 0.06); 
      --shadow-md: 0 10px 28px rgba(15, 23, 42, 0.1);
    }

    body.teen-mode {
      --bg-gradient: linear-gradient(180deg, #0F172A 0%, #1E293B 100%) !important;
      --primary: #60A5FA !important; --primary-dark: #3B82F6 !important;
      --card-bg: #1E293B !important; --text-main: #F8FAFC !important; --text-muted: #94A3B8 !important;
    }
    body.teen-mode .app-container { background: rgba(30, 41, 59, 0.98); border-color: #334155; }
    body.teen-mode header { background: linear-gradient(135deg, #1E293B 0%, #334155 100%) !important; }
    body.teen-mode .interactive-card, body.teen-mode .age-group-section, body.teen-mode .video-card { background: #1E293B !important; border-color: #334155 !important; color: #F8FAFC; }

    body.sensory-mode {
      --bg-gradient: #F1F5F9 !important; --primary: #475569 !important; --primary-dark: #334155 !important;
      --secondary: #64748B !important; --tea-blue: #334155 !important; --tea-light: #FFFFFF !important;
      background: var(--bg-gradient) !important; color: #1E293B !important;
    }
    body.sensory-mode * { animation: none !important; box-shadow: none !important; transition: none !important; }
    body.sensory-mode .interactive-card, body.sensory-mode .tea-box, body.sensory-mode .video-card { background: #FFFFFF !important; border: 2px solid #CBD5E1 !important; }

    * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Poppins', system-ui, sans-serif; -webkit-tap-highlight-color: transparent; }
    body { background: var(--bg-gradient); color: var(--text-main); min-height: 100vh; overflow-x: hidden; }

    @keyframes float { 0% { transform: translateY(0px); } 50% { transform: translateY(-4px); } 100% { transform: translateY(0px); } }
    @keyframes pulse { 0% { transform: scale(1); } 50% { transform: scale(1.02); } 100% { transform: scale(1); } }
    @keyframes fadeIn { from { opacity: 0; transform: translateY(6px); } to { opacity: 1; transform: translateY(0); } }

    .float-anim { animation: float 4s ease-in-out infinite; }
    .pulse-anim { animation: pulse 2.5s infinite; }
    .hover-float { transition: transform 0.2s ease; }
    .hover-float:hover { transform: translateY(-3px); }

    .app-container { width: 100%; min-height: 100vh; display: flex; flex-direction: column; gap: 24px; padding: 0 16px 60px; }
    .content-wrapper { width: 100%; max-width: 1500px; margin-left: auto; margin-right: auto; }

    header { background: linear-gradient(135deg, #BAE6FD 0%, #E0F2FE 100%); display: flex; align-items: center; justify-content: space-between; border-radius: var(--radius-lg); padding: 18px 32px; margin-top: 16px; box-shadow: var(--shadow-sm); gap: 16px; border: 3px solid #FFFFFF; }
    .logo-img { max-width: 190px; height: auto; object-fit: contain; }
    .header-actions { display: flex; align-items: center; gap: 12px; flex-wrap: wrap; }
    
    .action-btn-pill { background: #FFFFFF; border: 2.5px solid var(--primary); color: var(--primary-dark); font-weight: 800; font-size: 14px; padding: 10px 20px; border-radius: 50px; cursor: pointer; display: flex; align-items: center; gap: 8px; box-shadow: 0 4px 12px rgba(59, 130, 246, 0.15); transition: all 0.2s ease; }
    .action-btn-pill:hover { background: var(--primary); color: #FFF; transform: translateY(-2px); }

    .browser-notice-box { background: linear-gradient(135deg, #EFF6FF 0%, #DBEAFE 100%); border: 2.5px solid #3B82F6; border-radius: var(--radius-md); padding: 14px 20px; text-align: center; color: #1E40AF; font-size: 14px; font-weight: 800; box-shadow: var(--shadow-sm); display: flex; align-items: center; justify-content: center; gap: 10px; margin-bottom: 8px; }

    .page-nav { display: flex; gap: 12px; background: #F0F9FF; padding: 12px; border-radius: var(--radius-lg); border: 2px solid #BAE6FD; justify-content: center; flex-wrap: wrap; box-shadow: var(--shadow-sm); }
    .nav-tab-btn { flex: 1; min-width: 130px; max-width: 190px; padding: 12px 16px; border: none; border-radius: 12px; font-weight: 800; font-size: 14.5px; cursor: pointer; background: #FFFFFF; color: var(--text-muted); display: flex; align-items: center; justify-content: center; gap: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.04); transition: all 0.25s ease; }
    .nav-tab-btn:hover { background: #E0F2FE; color: var(--primary); transform: translateY(-2px); }
    .nav-tab-btn.active { background: var(--primary); color: #FFFFFF; box-shadow: 0 6px 16px rgba(59, 130, 246, 0.4); transform: translateY(-3px); }
    .nav-tab-btn.tea-tab.active { background: var(--tea-blue); color: #FFF; }
    .nav-tab-btn.vip-tab.active { background: linear-gradient(135deg, #F59E0B, #D97706); color: #FFF; }

    .page-content { display: none; flex-direction: column; gap: 28px; animation: fadeIn 0.3s ease; }
    .page-content.active-page { display: flex; }

    .banner-container { width: 100%; border-radius: var(--radius-lg); overflow: hidden; box-shadow: var(--shadow-sm); border: 3px solid #FFF; }
    .banner-img { width: 100%; height: 100%; min-height: 320px; max-height: 480px; display: block; object-fit: cover; }
    
    .intro-box { background: linear-gradient(135deg, #FEF3C7 0%, #FFFBEB 100%); border: 3px solid #FCD34D; border-radius: var(--radius-lg); padding: 36px; display: flex; flex-direction: column; justify-content: center; gap: 18px; box-shadow: var(--shadow-md); }
    .intro-box h2 { font-size: 26px; font-weight: 900; color: #92400E; display: flex; justify-content: space-between; align-items: center; gap: 12px; }
    .intro-box p { font-size: 16.5px; color: #78350F; line-height: 1.8; font-weight: 600; }
    
    .btn-audio-mini { background: linear-gradient(135deg, #FBBF24, #F59E0B); border: none; border-radius: 50%; width: 46px; height: 46px; min-width: 46px; cursor: pointer; font-size: 19px; display: flex; align-items: center; justify-content: center; color: #FFF; box-shadow: 0 4px 12px rgba(245, 158, 11, 0.4); transition: all 0.2s; }
    .btn-audio-mini:hover { transform: scale(1.1) rotate(5deg); }

    .age-group-section { background: #FFFFFF; border-radius: var(--radius-lg); padding: 36px; border: 2px solid #E2E8F0; box-shadow: var(--shadow-sm); }
    .age-title { font-size: 28px; font-weight: 900; color: var(--primary-dark); margin-bottom: 24px; display: flex; align-items: center; justify-content: space-between; }
    .interactive-card { background: #F8FAFC; border-radius: var(--radius-md); padding: 32px; text-align: center; border: 2px solid #E2E8F0; width: 100%; box-shadow: 0 2px 8px rgba(0,0,0,0.02); }

    .floating-cards-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); gap: 24px; }
    .floating-char-card { background: #FFFFFF; border-radius: var(--radius-lg); padding: 26px 20px; text-align: center; border: 3px solid #E2E8F0; box-shadow: var(--shadow-sm); display: flex; flex-direction: column; align-items: center; gap: 12px; cursor: pointer; transition: all 0.3s ease; }
    .floating-char-card:hover { transform: translateY(-6px); border-color: var(--primary); box-shadow: var(--shadow-md); }
    .floating-char-img { width: 120px; height: 120px; object-fit: contain; border-radius: 50%; background: #F0F9FF; padding: 6px; }
    .floating-char-name { font-size: 21px; font-weight: 900; color: var(--text-main); }
    .floating-char-tag { font-size: 13px; font-weight: 800; padding: 6px 16px; border-radius: 20px; text-transform: uppercase; }

    /* REDES SOCIAIS (TODOS OS 8 ÍCONES PEDIDOS) */
    .social-round-section { display: flex; justify-content: center; align-items: center; gap: 16px; flex-wrap: wrap; background: #FFF; padding: 22px; border-radius: var(--radius-lg); box-shadow: var(--shadow-sm); border: 2px solid #E2E8F0; }
    .social-round-btn { width: 58px; height: 58px; border-radius: 50%; background: #F8FAFC; border: 2.5px solid #CBD5E1; display: flex; align-items: center; justify-content: center; text-decoration: none; box-shadow: var(--shadow-sm); transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1); }
    .social-round-btn:hover { transform: translateY(-6px) scale(1.1); border-color: var(--primary); background: #FFF; box-shadow: 0 10px 20px rgba(59, 130, 246, 0.25); }
    .social-round-btn img { width: 32px; height: 32px; object-fit: contain; }

    .media-section-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 32px; }
    @media (max-width: 900px) { .media-section-grid { grid-template-columns: 1fr; } }
    .video-card { background: #FFFFFF; border-radius: var(--radius-lg); padding: 32px; box-shadow: var(--shadow-sm); border: 2px solid #E2E8F0; text-align: center; }
    .video-wrapper { position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; border-radius: var(--radius-md); }
    .video-wrapper iframe { position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0; }
    .spotify-wrapper { width: 100%; height: 352px; border-radius: 14px; overflow: hidden; border: 2px solid #1DB954; }

    .media-card-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 20px; margin-top: 24px; }
    .media-item-box { background: #FFF; border: 2.5px solid #CBD5E1; border-radius: var(--radius-md); padding: 24px 18px; display: flex; flex-direction: column; align-items: center; gap: 10px; cursor: pointer; position: relative; transition: all 0.2s; box-shadow: 0 2px 6px rgba(0,0,0,0.03); }
    .media-item-box:hover { transform: translateY(-4px); border-color: var(--primary); box-shadow: 0 6px 14px rgba(59,130,246,0.15); }
    .media-item-box.locked { background: #FFFBEB; border-color: #FCD34D; }
    .media-badge-vip { position: absolute; top: 8px; right: 8px; background: #F59E0B; color: #FFF; font-size: 11px; font-weight: 800; padding: 4px 8px; border-radius: 8px; }

    #paintCanvas { background: #FFF; border: 4px solid var(--primary); border-radius: var(--radius-lg); width: 100%; height: 520px; touch-action: none; cursor: crosshair; }
    
    /* LOUSA MÁGICA BOTÕES COM TEXTO LEGÍVEL E CORES NITIDAS */
    .btn-color-draw { background: #FFFFFF; border: 2.5px solid #94A3B8; color: #0F172A; padding: 12px 20px; border-radius: 12px; font-weight: 800; font-size: 14.5px; cursor: pointer; display: flex; align-items: center; gap: 8px; transition: all 0.2s; box-shadow: 0 2px 6px rgba(0,0,0,0.05); }
    .btn-color-draw:hover { background: #F1F5F9; border-color: var(--primary); }
    .btn-color-draw.selected { border-color: var(--primary); background: #3B82F6; color: #FFFFFF; transform: scale(1.05); box-shadow: 0 4px 12px rgba(59,130,246,0.3); }
    .btn-color-draw img { width: 30px; height: 30px; object-fit: contain; background: #FFF; border-radius: 50%; padding: 2px; }

    .game-btn-grid { display: flex; justify-content: center; gap: 14px; flex-wrap: wrap; margin-top: 24px; }
    .btn-choice { background: var(--purple); color: #FFF; border: none; padding: 18px 32px; font-weight: 900; font-size: 20px; border-radius: 14px; cursor: pointer; min-width: 80px; box-shadow: 0 4px 14px rgba(139, 92, 246, 0.3); transition: transform 0.15s ease; }
    .btn-choice:active { transform: scale(0.92); }
    .btn-choice.acertou { background: #10B981 !important; transform: scale(1.1); }
    .btn-choice.errou { background: #EF4444 !important; transform: scale(0.95) rotate(-3deg); }

    .memory-board { display: grid; grid-template-columns: repeat(4, 1fr); gap: 16px; margin-top: 20px; max-width: 560px; margin-left: auto; margin-right: auto; }
    .memory-card { aspect-ratio: 1; background: var(--primary); border-radius: 16px; display: flex; align-items: center; justify-content: center; color: #FFF; font-weight: 900; font-size: 32px; cursor: pointer; transition: transform 0.2s; box-shadow: 0 4px 12px rgba(59,130,246,0.2); }
    .memory-card:active { transform: scale(0.95); }
    .memory-card.flipped { background: #FFF; border: 3px solid var(--primary); }

    .timer-bar-bg { width: 100%; height: 24px; background: #E2E8F0; border-radius: 12px; overflow: hidden; margin: 14px 0; border: 2px solid #CBD5E1; }
    .timer-bar-fill { width: 100%; height: 100%; background: #10B981; transition: width 1s linear, background-color 0.5s ease; }

    .modal-overlay { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(15, 23, 42, 0.8); backdrop-filter: blur(6px); z-index: 99999; justify-content: center; align-items: center; padding: 20px; }
    .modal-overlay.active { display: flex; animation: fadeIn 0.3s; }
    .modal-box { background: #FFF; border-radius: var(--radius-lg); padding: 40px; max-width: 560px; width: 100%; text-align: center; border: 4px solid var(--primary); position: relative; box-shadow: 0 20px 40px rgba(0,0,0,0.3); }
    .modal-close { position: absolute; top: 16px; right: 16px; background: #F1F5F9; border: none; width: 38px; height: 38px; border-radius: 50%; font-weight: bold; font-size: 16px; cursor: pointer; }
    
    .vip-input { width: 100%; padding: 14px 18px; font-size: 15px; border: 2.5px solid #CBD5E1; border-radius: 12px; margin-bottom: 14px; outline: none; font-family: 'Poppins'; }
    .vip-input:focus { border-color: var(--primary); }

    #visualToast { position: fixed; bottom: 80px; left: 50%; transform: translateX(-50%) translateY(100px); background: #0F172A; color: #FFF; padding: 14px 28px; border-radius: 30px; font-size: 15px; font-weight: 700; transition: transform 0.3s; z-index: 999999; pointer-events: none; opacity: 0; box-shadow: 0 8px 24px rgba(0,0,0,0.25); }
    #visualToast.show { transform: translateX(-50%) translateY(0); opacity: 1; }
    
    .floating-vip-badge { position: fixed; bottom: 28px; right: 28px; background: linear-gradient(135deg, #F59E0B 0%, #D97706 100%); color: #FFF; padding: 16px 28px; border-radius: 50px; font-size: 16px; font-weight: 900; box-shadow: 0 8px 24px rgba(245, 158, 11, 0.4); display: flex; align-items: center; gap: 10px; cursor: pointer; border: 2px solid #FDE68A; z-index: 999; }
    
    footer { text-align: center; padding: 40px 20px; font-size: 14px; color: var(--text-muted); font-weight: 600; margin-top: auto; display: flex; flex-direction: column; gap: 8px; }
    footer a { color: var(--primary); cursor: pointer; text-decoration: underline; }
  </style>
</head>
<body onclick="desbloquearAudioMobileOnce()">

  <div id="visualToast">Aviso</div>

  <!-- MODAL: ONBOARDING -->
  <div id="modalOnboarding" class="modal-overlay">
    <div class="modal-box" style="max-width: 560px; text-align: left; border-color: #3B82F6;">
      <h3 style="color: var(--primary-dark); font-size: 26px; margin-bottom: 12px; font-weight: 900; text-align:center; display:flex; align-items:center; justify-content:center; gap:10px;">
        👋 Bem-vindo(a) ao Portal!
        <button class="btn-audio-mini" style="width:38px;height:38px;font-size:14px;" onclick="lerTexto('Bem-vindo ao Portal da Turminha do Xexéu. Vamos configurar sua experiência.')">🔊</button>
      </h3>
      <p style="font-size: 14.5px; color: #475569; margin-bottom: 22px; font-weight: 600; text-align:center;">Configure seu acesso para iniciar a navegação no notebook.</p>

      <label style="font-size: 14.5px; font-weight: 800; color: var(--primary-dark); display: block; margin-bottom: 6px;">Seu Nome ou Apelido de Exibição:</label>
      <input type="text" id="onb-nome" class="vip-input" placeholder="Digite seu nome..." value="Evelyn">

      <label style="font-size: 14.5px; font-weight: 800; color: var(--primary-dark); display: block; margin-bottom: 6px; margin-top:14px;">Estilo de Experiência do Portal:</label>
      <select id="onb-modo" class="vip-input" style="background:#FFF;">
        <option value="familia">🧸 Padrão / Família & Crianças</option>
        <option value="adolescente">🎧 Adolescente / Criativo (Visual Clean/Dark)</option>
      </select>

      <label style="font-size: 14.5px; font-weight: 800; color: var(--primary-dark); display: block; margin-bottom: 6px; margin-top:14px;">
        Criar Senha Parental / Segurança (PIN):
      </label>
      <input type="password" id="onb-senha" class="vip-input" placeholder="Crie uma senha numérica ou texto">

      <button onclick="salvarConfiguracaoInicial()" style="background: #10B981; color: #FFF; border: none; padding: 16px; border-radius: 12px; font-size: 16px; font-weight: 900; cursor: pointer; width: 100%; box-shadow: 0 4px 12px rgba(16,185,129,0.3); margin-top:14px;">
        Acessar Portal 🚀
      </button>
    </div>
  </div>

  <!-- MODAL: FICHA DO PERSONAGEM -->
  <div id="modalFichaPersonagem" class="modal-overlay">
    <div class="modal-box">
      <button class="modal-close" onclick="fecharFichaPersonagem()">✕</button>
      <img id="ficha-img" src="" alt="Personagem" class="pulse-anim" style="width: 140px; height: 140px; object-fit: contain; margin-bottom: 16px;">
      <h3 id="ficha-nome" style="color: var(--primary-dark); font-weight: 900; font-size: 30px;"></h3>
      <p id="ficha-apelido" style="color: var(--purple); font-weight: 800; font-size: 16px; margin-bottom: 20px;"></p>
      <button id="btnFichaOuvir" class="btn-choice hover-float" style="padding: 16px 30px; font-size: 18px; margin-bottom: 20px; background: #F59E0B;">🔊 Ouvir Apresentação</button>
      <div style="text-align: left; background: #F8FAFC; padding: 22px; border-radius: 14px; border: 2px solid #E2E8F0; font-size: 15.5px; display: flex; flex-direction: column; gap: 12px;">
        <p><strong>🌟 Quem sou eu?</strong> <span id="ficha-quem"></span></p>
        <p><strong>💖 O que eu gosto?</strong> <span id="ficha-gosto"></span></p>
        <p><strong>💬 Minha frase:</strong> <em style="color:#475569;">"<span id="ficha-frase"></span>"</em></p>
      </div>
    </div>
  </div>

  <!-- MODAL: PARENTAL GATE -->
  <div id="modalParentalGate" class="modal-overlay">
    <div class="modal-box" style="border-color:#F59E0B; max-width:460px;">
      <h3 style="color: #92400E; font-size: 26px; margin-bottom: 10px; font-weight: 900;">🔒 Área Restrita</h3>
      <p style="font-size: 15px; color: #475569; margin-bottom: 18px; font-weight: 600;">Digite sua <strong>Senha Parental (PIN)</strong>:</p>
      <input type="password" id="respostaDesafio" class="vip-input" style="text-align:center; font-size:24px; letter-spacing:4px;" placeholder="****">
      <div style="display: flex; gap: 14px; justify-content: center; margin-bottom: 16px;">
        <button onclick="fecharParentalGate()" style="padding: 14px 24px; border: none; border-radius: 10px; background: #E2E8F0; font-weight: 800; cursor: pointer; font-size: 15px;">Voltar</button>
        <button onclick="verificarParentalGate()" style="padding: 14px 28px; border: none; border-radius: 10px; background: #F59E0B; color: #FFF; font-weight: 900; cursor: pointer; font-size: 15px;">Entrar ➔</button>
      </div>
      <a onclick="esqueciMinhaSenha()" style="font-size: 13.5px; color: var(--primary); cursor: pointer; text-decoration: underline;">Esqueci minha senha (Usar Senha Mestra)</a>
    </div>
  </div>

  <!-- MODAL: BLOQUEIO TEMPO -->
  <div id="modalBloqueioTempo" class="modal-overlay">
    <div class="modal-box" style="border-color:#EF4444; max-width:460px;">
      <h3 style="color: #991B1B; font-size: 26px; margin-bottom: 10px; font-weight: 900;">⏰ O Tempo de Uso Acabou!</h3>
      <p style="font-size: 15px; color: #475569; margin-bottom: 18px; font-weight: 600;">Para desbloquear o portal, insira a senha parental:</p>
      <input type="password" id="senhaDesbloqueioTempo" class="vip-input" style="text-align:center; font-size:24px; letter-spacing:4px;" placeholder="****">
      <button onclick="tentarDesbloquearTelaTempo()" style="background: #EF4444; color: #FFF; border: none; padding: 14px; border-radius: 12px; font-weight: 900; cursor: pointer; width: 100%; margin-bottom: 14px; font-size: 16px;">Desbloquear 🔓</button>
      <a onclick="esqueciMinhaSenhaTempo()" style="font-size: 13.5px; color: var(--primary); cursor: pointer; text-decoration: underline;">Esqueci minha senha</a>
    </div>
  </div>

  <div class="floating-vip-badge float-anim" onclick="abrirAreaProtegida('vip')">
    <span style="font-size:20px;">⭐</span><span>Seja VIP (R$ 6,00)</span>
  </div>

  <div class="app-container">

    <!-- CABEÇALHO -->
    <header class="content-wrapper">
      <a href="https://www.youtube.com/@turminhaxe_xeu" target="_blank">
        <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908275/TURMINHA_LOGO.png" class="logo-img hover-float" alt="Logo">
      </a>
      <div class="header-actions">
        <button id="btnSensoryHeader" class="action-btn-pill" onclick="toggleSensoryMode()"><span>🌿</span> Modo Calmo</button>
        <button id="toggleAudioBtn" class="action-btn-pill" onclick="alternarAudioGlobal()"><span id="audioIcon">🔊</span> <span id="audioText">Voz</span></button>
        <button class="action-btn-pill" onclick="abrirAreaProtegida('config')"><span>⚙️</span></button>
        <button class="action-btn-pill" onclick="abrirAreaProtegida('perfil')"><span>👤</span></button>
      </div>
    </header>

    <!-- DICA DE ÁUDIO NO NOTEBOOK / NAVEGADOR -->
    <div class="browser-notice-box content-wrapper">
      <span>💡 Dica: Se o som estiver mudo ou travado, clique em qualquer botão de voz (🔊) ou abra diretamente no Google Chrome / Safari!</span>
    </div>

    <!-- NAVEGAÇÃO AMPLA -->
    <nav class="page-nav content-wrapper">
      <button id="btn-tab-inicio" class="nav-tab-btn active" onclick="mudarPagina('inicio')">🏠 Início</button>
      <button id="btn-tab-videos" class="nav-tab-btn" onclick="mudarPagina('videos')">🎬 Vídeos e Músicas</button>
      <button id="btn-tab-jogos" class="nav-tab-btn" onclick="mudarPagina('jogos')">🎮 Jogos</button>
      <button id="btn-tab-tea" class="nav-tab-btn tea-tab" onclick="mudarPagina('tea')">🧩 Espaço TEA</button>
      <button id="btn-tab-livros" class="nav-tab-btn" onclick="mudarPagina('livros')">📚 Livros</button>
      <button id="btn-tab-rotina" class="nav-tab-btn" onclick="mudarPagina('rotina')">📅 Rotina</button>
      <button id="btn-tab-conquistas" class="nav-tab-btn" onclick="mudarPagina('conquistas')">🏆 Conquistas</button>
      <button id="btn-tab-vip" class="nav-tab-btn vip-tab" onclick="abrirAreaProtegida('vip')">⭐ Área VIP</button>
    </nav>

    <!-- PÁGINA 1: INÍCIO -->
    <main id="pagina-inicio" class="page-content active-page content-wrapper">
      <section style="display: grid; grid-template-columns: 1fr 1fr; gap: 28px; align-items: stretch;">
        <div class="banner-container"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994339/BANNER_SITE_TURMINHA_DO_XEXEU.png" class="banner-img"></div>
        
        <div class="interactive-card" style="border-color: #BAE6FD; background: #F0F9FF; text-align: left; padding: 28px; display:flex; flex-direction:column; justify-content:center;">
          <h4 style="color: var(--tea-blue); font-weight: 900; font-size: 19px; margin-bottom: 8px; display:flex; justify-content:space-between; align-items:center;">
            <span>⏳ Temporizador de Uso</span>
            <button class="btn-audio-mini" style="width:36px;height:36px;font-size:14px;" onclick="lerTexto('Defina um limite de tempo para uso do portal. Grátis até 2 minutos, VIP até 30 minutos.')">🔊</button>
          </h4>
          <p style="font-size: 14px; color: #475569; font-weight: 600; margin-bottom: 14px;">Grátis: até 2 min | VIP: até 30 min.</p>
          <div id="botoesTemporizadorGeral" style="display:flex; gap:10px; flex-wrap:wrap; margin-bottom:14px;"></div>
          <div class="timer-bar-bg"><div id="barra-temporizador" class="timer-bar-fill" style="width: 100%;"></div></div>
          <p id="texto-temporizador" style="font-weight: 900; color: #475569; font-size: 19px; margin:6px 0 0 0; text-align:center;">0:00</p>
        </div>
      </section>

      <section class="intro-box hover-float">
        <h2>
          <span>✨ Educando com Alegria e Amor</span>
          <button class="btn-audio-mini" onclick="lerTexto('Olá, Evelyn! Mais do que um nome divertido, a Turminha do Xexéu é o nosso jeito de honrar as raízes e a história da nossa família. O nome Xexéu é uma homenagem que atravessa gerações. Ele honra a memória de Mariano Xexéu e celebra a vida de seu filho, Pedro Mariano, grande inspiração para o nosso querido Vovô Beto. A Vovó Hilda é inspirada na inesquecível Astrogilda Grispym, representando o amor que não conhece o tempo.')">🔊</button>
        </h2>
        <p>Olá, <strong class="nome-usuario-dinamico">Evelyn</strong>! Mais do que um nome divertido, a <strong>Turminha do Xexéu</strong> é o nosso jeito de honrar as raízes e a história da nossa família.</p>
        <p>O nome <strong>Xexéu</strong> é uma homenagem que atravessa gerações. Ele honra a memória de <em>Mariano Xexéu</em> e celebra a vida de seu filho, <em>Pedro Mariano</em>, grande inspiração para o nosso querido <strong>Vovô Beto</strong>.</p>
        <p>A <strong>Vovó Hilda</strong> é inspirada na inesquecível <em>Astrogilda Grispym</em>, representando o amor que não conhece o tempo.</p>
      </section>

      <!-- REDES SOCIAIS OFICIAIS (TODOS OS 8 LINKS E ÍCONES) -->
      <section class="social-round-section">
        <a href="https://www.youtube.com/@turminhaxe_xeu" target="_blank" class="social-round-btn" title="YouTube"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908275/YT.png" alt="YouTube"></a>
        <a href="https://music.youtube.com/channel/UC8KOg4IH-h0YNrpKlfIl2Vw" target="_blank" class="social-round-btn" title="YouTube Music"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908275/YT_MUSIC.png" alt="YT Music"></a>
        <a href="https://www.instagram.com/turminhaxe_xeu/" target="_blank" class="social-round-btn" title="Instagram"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908273/INDTAGRAM.png" alt="Instagram"></a>
        <a href="https://www.tiktok.com/@turminhaxe_xeu" target="_blank" class="social-round-btn" title="TikTok"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908275/TIKTOK.png" alt="TikTok"></a>
        <a href="https://open.spotify.com/intl-pt/artist/6ykKQ3uP6Wl2REylKJAdJ6?si=QqrYhcP2REaiUA9LFtjT4g" target="_blank" class="social-round-btn" title="Spotify"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908274/SPOTIFY.png" alt="Spotify"></a>
        <a href="https://www.facebook.com/profile.php?id=61585431586796" target="_blank" class="social-round-btn" title="Facebook"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908273/FACEBOOK.png" alt="Facebook"></a>
        <a href="https://www.threads.net/@turminhaxe_xeu" target="_blank" class="social-round-btn" title="Threads"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908274/THRENDS.png" alt="Threads"></a>
        <a href="https://br.pinterest.com/turminhaxe_xeu" target="_blank" class="social-round-btn" title="Pinterest"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908274/PINTEREST.png" alt="Pinterest"></a>
      </section>

      <section class="section-family-container" style="display:flex; flex-direction:column; gap:32px;">
        <div>
          <h3 class="family-group-title" style="font-size:22px; font-weight:900; color:var(--primary-dark); margin-bottom:14px; display:flex; justify-content:space-between; align-items:center;">
            <span>✨ Mascotes Oficiais</span>
            <button class="btn-audio-mini" style="width:40px;height:40px;font-size:15px;" onclick="lerTexto('Toque nos personagens para ver a ficha completa.')">🔊</button>
          </h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-especial" onclick="abrirFichaPersonagem('Xexéu')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_XEXEU.png" class="floating-char-img"><span class="floating-char-name">Xexéu</span><span class="floating-char-tag">Mascote Oficial</span></div>
            <div class="floating-char-card card-especial" onclick="abrirFichaPersonagem('Capilé')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994882/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_CAPILE.png" class="floating-char-img"><span class="floating-char-name">Capilé</span><span class="floating-char-tag">O Companheiro</span></div>
          </div>
        </div>

        <div>
          <h3 class="family-group-title" style="font-size:22px; font-weight:900; color:var(--primary-dark); margin-bottom:14px; display:flex; justify-content:space-between; align-items:center;">
            <span>💖 Casa da Maya e do Theo</span>
            <button class="btn-audio-mini" style="width:40px;height:40px;font-size:15px;" onclick="lerTexto('Casa da Maya e do Theo.')">🔊</button>
          </h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-f1" onclick="abrirFichaPersonagem('Maya')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994884/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_MAYA.png" class="floating-char-img"><span class="floating-char-name">Maya</span></div>
            <div class="floating-char-card card-f1" onclick="abrirFichaPersonagem('Theo')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_THEO.png" class="floating-char-img"><span class="floating-char-name">Theo</span></div>
            <div class="floating-char-card card-f1" onclick="abrirFichaPersonagem('Nina')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_NINA.png" class="floating-char-img"><span class="floating-char-name">Nina</span></div>
            <div class="floating-char-card card-f1" onclick="abrirFichaPersonagem('Iza')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_IZA.png" class="floating-char-img"><span class="floating-char-name">Iza</span></div>
          </div>
        </div>

        <div>
          <h3 class="family-group-title" style="font-size:22px; font-weight:900; color:var(--primary-dark); margin-bottom:14px; display:flex; justify-content:space-between; align-items:center;">
            <span>⚡ Casa do Sam e da Lia</span>
            <button class="btn-audio-mini" style="width:40px;height:40px;font-size:15px;" onclick="lerTexto('Casa do Sam e da Lia.')">🔊</button>
          </h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-f2" onclick="abrirFichaPersonagem('Sam')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_SAM.png" class="floating-char-img"><span class="floating-char-name">Sam</span></div>
            <div class="floating-char-card card-f2" onclick="abrirFichaPersonagem('Lia')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994884/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_LIA.png" class="floating-char-img"><span class="floating-char-name">Lia</span></div>
            <div class="floating-char-card card-f2" onclick="abrirFichaPersonagem('Joca')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_JOCA.png" class="floating-char-img"><span class="floating-char-name">Joca</span></div>
            <div class="floating-char-card card-f2" onclick="abrirFichaPersonagem('Leo')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_LEO.png" class="floating-char-img"><span class="floating-char-name">Leo</span></div>
          </div>
        </div>

        <div>
          <h3 class="family-group-title" style="font-size:22px; font-weight:900; color:var(--primary-dark); margin-bottom:14px; display:flex; justify-content:space-between; align-items:center;">
            <span>👵👴 Os Avós</span>
            <button class="btn-audio-mini" style="width:40px;height:40px;font-size:15px;" onclick="lerTexto('Os queridos Avós.')">🔊</button>
          </h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-avos" onclick="abrirFichaPersonagem('Beto')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_VOVO_BETO.png" class="floating-char-img"><span class="floating-char-name">Vovô Beto</span></div>
            <div class="floating-char-card card-avos" onclick="abrirFichaPersonagem('Hilda')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_VOVO_HILDA.png" class="floating-char-img"><span class="floating-char-name">Vovó Hilda</span></div>
          </div>
        </div>
      </section>

      <!-- SUPORTE INÍCIO -->
      <section class="interactive-card" style="background:#F0F9FF; border:3px solid #BAE6FD; text-align:left; margin-top:32px; padding:32px;">
        <h3 style="color:var(--tea-blue); font-size:24px; font-weight:900; margin-bottom:10px; display:flex; justify-content:space-between; align-items:center;">
          📬 Dúvidas ou Sugestões?
          <button class="btn-audio-mini" onclick="lerTexto('Precisa de ajuda ou quer enviar uma sugestão? Escreva para nós!')">🔊</button>
        </h3>
        <p style="font-size:15px; font-weight:600; color:#475569; margin-bottom:18px;">Sua mensagem vai direto para nossa equipe (turminhaxexeu@gmail.com).</p>
        <input type="email" id="suporteEmailInicio" class="vip-input" placeholder="Seu e-mail de contato">
        <textarea id="suporteMensagemInicio" class="vip-input" placeholder="Escreva aqui..." style="resize:vertical; min-height:120px;"></textarea>
        <button onclick="enviarSuporteReclamacao('Inicio')" id="btnEnviarSuporteInicio" style="background:var(--tea-blue); color:#FFF; border:none; padding:16px 24px; border-radius:12px; font-size:16px; font-weight:900; cursor:pointer; width:100%;">Enviar Mensagem ✉️</button>
      </section>
    </main>

    <!-- PÁGINA 2: VÍDEOS E MÚSICAS (COM SONS FUNCIONANDO AO CLIQUE) -->
    <main id="pagina-videos" class="page-content content-wrapper">
      <div class="media-section-grid">
        <div class="video-card hover-float">
          <h3 style="font-size:22px; font-weight:900; color:var(--primary-dark); margin-bottom:18px; display:flex; justify-content:space-between; align-items:center;">
            📺 Episódios YouTube
            <button class="btn-audio-mini" onclick="lerTexto('Assista aos episódios no YouTube!')">🔊</button>
          </h3>
          <div class="video-wrapper"><iframe src="https://www.youtube-nocookie.com/embed/videosseries?list=PLh42qmbnReoE_pM4lig3DpJaNGWqoT9uJ" allowfullscreen></iframe></div>
        </div>
        <div class="video-card hover-float" style="border-color:#1DB954;">
          <h3 style="font-size:22px; font-weight:900; color:#1DB954; margin-bottom:18px; display:flex; justify-content:space-between; align-items:center;">
            🎧 Rádio da Turminha
            <button class="btn-audio-mini" style="background:#1DB954;" onclick="lerTexto('Ouça as músicas no Spotify!')">🔊</button>
          </h3>
          <div class="spotify-wrapper"><iframe src="https://open.spotify.com/embed/artist/6ykKQ3uP6Wl2REylKJAdJ6?utm_source=generator&theme=0" width="100%" height="352" frameBorder="0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy"></iframe></div>
        </div>
      </div>

      <div class="interactive-card">
        <h4 style="font-size:24px; font-weight:900; color:var(--tea-blue); margin-bottom:14px; display:flex; justify-content:space-between; align-items:center;">
          🌙 Sons e Acalento (Grátis & VIP)
          <button class="btn-audio-mini" onclick="lerTexto('Sons suaves para relaxar, focar ou dormir. Basta clicar para escutar.')">🔊</button>
        </h4>
        <div class="media-card-grid">
          <div class="media-item-box" onclick="tocarSomReal('https://actions.google.com/sounds/v1/weather/light_rain.ogg')"><span style="font-size:42px;">🌧️</span><strong style="font-size:16px;">Chuva Suave</strong><span style="font-size:13px; color:#16A34A; font-weight:900;">GRÁTIS (Tocar)</span></div>
          <div class="media-item-box" onclick="tocarSomReal('https://actions.google.com/sounds/v1/animals/birds_arent_real.ogg')"><span style="font-size:42px;">🐦</span><strong style="font-size:16px;">Passarinhos</strong><span style="font-size:13px; color:#16A34A; font-weight:900;">GRÁTIS (Tocar)</span></div>
          <div class="media-item-box locked" onclick="abrirAreaProtegida('vip')"><span class="media-badge-vip">👑 VIP</span><span style="font-size:42px;">🌊</span><strong style="font-size:16px;">Ondas do Mar</strong></div>
          <div class="media-item-box locked" onclick="abrirAreaProtegida('vip')"><span class="media-badge-vip">👑 VIP</span><span style="font-size:42px;">🔥</span><strong style="font-size:16px;">Fogueira</strong></div>
        </div>
      </div>
    </main>

    <!-- PÁGINA 3: JOGOS INFINITOS E FLUIDOS -->
    <main id="pagina-jogos" class="page-content content-wrapper">
      <div class="age-group-section">
        <h3 class="age-title">
          <span>🎮 Central de Jogos</span>
          <button class="btn-audio-mini" onclick="lerTexto('Central de jogos educativos e interativos!')">🔊</button>
        </h3>
        
        <nav class="games-subnav" style="display:flex; gap:12px; background:#E0F2FE; padding:14px; border-radius:14px; margin-bottom:24px; overflow-x:auto;">
          <button id="subtab-lousa" class="subnav-btn active" onclick="mudarSubJogo('lousa')" style="padding:12px 18px; border:none; border-radius:10px; font-weight:800; cursor:pointer; background:var(--primary); color:#FFF; font-size:15px;">🎨 Lousa Mágica</button>
          <button id="subtab-contar" class="subnav-btn" onclick="mudarSubJogo('contar')" style="padding:12px 18px; border:none; border-radius:10px; font-weight:800; cursor:pointer; background:#FFF; color:var(--primary-dark); font-size:15px;">🔢 Contar</button>
          <button id="subtab-letras" class="subnav-btn" onclick="mudarSubJogo('letras')" style="padding:12px 18px; border:none; border-radius:10px; font-weight:800; cursor:pointer; background:#FFF; color:var(--primary-dark); font-size:15px;">🔤 Letras</button>
          <button id="subtab-memoria" class="subnav-btn" onclick="mudarSubJogo('memoria')" style="padding:12px 18px; border:none; border-radius:10px; font-weight:800; cursor:pointer; background:#FFF; color:var(--primary-dark); font-size:15px;">🧠 Memória</button>
          <button id="subtab-quiz" class="subnav-btn" onclick="mudarSubJogo('quiz')" style="padding:12px 18px; border:none; border-radius:10px; font-weight:800; cursor:pointer; background:#FFF; color:var(--primary-dark); font-size:15px;">❓ Quiz</button>
        </nav>

        <!-- LOUSA MÁGICA -->
        <div id="game-lousa" class="game-section-page active-game-page interactive-card">
          <h4 style="font-weight: 900; margin-bottom: 16px; font-size: 22px;">🎨 Lousa Mágica & Colorir</h4>
          <div id="coloringSelectGrid" style="display:flex; justify-content:center; gap:12px; flex-wrap:wrap; margin-bottom:18px;"></div>
          <canvas id="paintCanvas"></canvas>
          <div class="palette" style="display:flex; gap:14px; justify-content:center; align-items:center; margin-top:20px; flex-wrap:wrap;">
            <div class="color-dot" style="width:44px;height:44px;border-radius:50%;background:#3B82F6;cursor:pointer;" onclick="mudarCor('#3B82F6')"></div>
            <div class="color-dot" style="width:44px;height:44px;border-radius:50%;background:#EF4444;cursor:pointer;" onclick="mudarCor('#EF4444')"></div>
            <div class="color-dot" style="width:44px;height:44px;border-radius:50%;background:#10B981;cursor:pointer;" onclick="mudarCor('#10B981')"></div>
            <div class="color-dot" style="width:44px;height:44px;border-radius:50%;background:#F59E0B;cursor:pointer;" onclick="mudarCor('#F59E0B')"></div>
            <div class="color-dot" style="width:44px;height:44px;border-radius:50%;background:#8B5CF6;cursor:pointer;" onclick="mudarCor('#8B5CF6')"></div>
            <div class="color-dot" style="width:44px;height:44px;border-radius:50%;background:#000000;cursor:pointer;" onclick="mudarCor('#000000')"></div>
            <button class="action-btn-pill" style="background:#FEE2E2; border-color:#EF4444; color:#991B1B;" onclick="limparCanvas()">Limpar 🗑️</button>
            <button class="action-btn-pill" style="background:#D1FAE5; border-color:#10B981; color:#065F46;" onclick="salvarFotoDesenho()">Salvar 📸</button>
          </div>
        </div>

        <!-- CONTAR -->
        <div id="game-contar" class="game-section-page interactive-card">
          <h4 style="font-weight:900; font-size:24px; margin-bottom:12px;">🔢 Vamos Contar?</h4>
          <p style="color:var(--text-muted); font-size:15px; margin-bottom:16px;">Quantos amiguinhos aparecem abaixo?</p>
          <div id="countDisplay" style="display:flex; justify-content:center; align-items:center; gap:16px; margin:24px 0; min-height:100px; flex-wrap:wrap;"></div>
          <div id="countOptions" class="game-btn-grid"></div>
        </div>

        <!-- LETRAS -->
        <div id="game-letras" class="game-section-page interactive-card">
          <h4 style="font-weight:900; font-size:24px; margin-bottom:12px;">🔤 Qual é a Primeira Letra?</h4>
          <p style="font-size:16px; font-weight:700;">Nome: <strong id="nome-letra-personagem" style="color:var(--purple); font-size:22px;">Xexéu</strong></p>
          <img id="img-letra-personagem" src="" style="width:140px; height:140px; object-fit:contain; margin:18px 0;">
          <div id="opcoes-letras" class="game-btn-grid"></div>
        </div>

        <!-- MEMÓRIA -->
        <div id="game-memoria" class="game-section-page interactive-card">
          <h4 style="font-weight:900; font-size:24px; margin-bottom:12px;">🧠 Jogo da Memória</h4>
          <p style="color:var(--text-muted); font-size:15px; margin-bottom:16px;">Encontre os pares dos amigos da Turminha!</p>
          <div id="memoryBoard" class="memory-board"></div>
        </div>

        <!-- QUIZ -->
        <div id="game-quiz" class="game-section-page interactive-card">
          <h4 style="font-weight:900; font-size:24px; margin-bottom:12px;">❓ Desafios da Turminha</h4>
          <p style="color:var(--text-muted); font-size:15px; margin-bottom:16px;">Quem é o personagem da foto abaixo?</p>
          <img id="quiz-img" src="" style="width:140px; height:140px; object-fit:contain; margin:18px 0;">
          <div id="quiz-options" class="game-btn-grid"></div>
        </div>
      </div>
    </main>

    <!-- PÁGINA 4: ESPAÇO TEA -->
    <main id="pagina-tea" class="page-content content-wrapper">
      <div class="age-group-section">
        <div class="tea-box hover-float" style="padding:28px;">
          <div style="display:flex; align-items:center; justify-content:space-between; margin-bottom:12px;">
            <div style="display:flex; align-items:center; gap:16px;">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_LEO.png" style="width:70px; height:70px; object-fit:contain;">
              <h3 style="margin:0; font-size:24px;">🧩 Espaço TEA com o Leo</h3>
            </div>
            <button class="btn-audio-mini" onclick="lerTexto('Espaço TEA com o Leo. Vamos fazer tudo com calma, no seu próprio tempo.')">🔊</button>
          </div>
          <p style="font-size: 15px; color: #475569; font-weight: 600;">"Oi! Eu sou o Leo. Vamos fazer tudo com calma e no nosso próprio tempo?"</p>
        </div>

        <div class="interactive-card" style="border-color: #BAE6FD; margin-top: 24px;">
          <h4 style="color: var(--tea-blue); font-weight: 900; font-size: 18px; margin-bottom: 12px;">🗣️ Cartões de Fala (CAA)</h4>
          <div class="caa-grid" style="display:grid; grid-template-columns:repeat(auto-fit, minmax(140px,1fr)); gap:14px;">
            <div class="caa-btn hover-float" style="background:#FFF; border:2.5px solid #BAE6FD; border-radius:14px; padding:18px 10px; text-align:center; cursor:pointer;" onclick="lerTexto('Eu quero água, por favor.')"><span style="font-size:36px;">💧</span><p style="font-weight:800; color:var(--tea-blue); margin-top:6px; font-size:14px;">Água</p></div>
            <div class="caa-btn hover-float" style="background:#FFF; border:2.5px solid #BAE6FD; border-radius:14px; padding:18px 10px; text-align:center; cursor:pointer;" onclick="lerTexto('Estou com fome.')"><span style="font-size:36px;">🍎</span><p style="font-weight:800; color:var(--tea-blue); margin-top:6px; font-size:14px;">Comer</p></div>
            <div class="caa-btn hover-float" style="background:#FFF; border:2.5px solid #BAE6FD; border-radius:14px; padding:18px 10px; text-align:center; cursor:pointer;" onclick="lerTexto('Preciso ir ao banheiro.')"><span style="font-size:36px;">🚽</span><p style="font-weight:800; color:var(--tea-blue); margin-top:6px; font-size:14px;">Banheiro</p></div>
          </div>
        </div>
      </div>
    </main>

    <!-- PÁGINA 5: LIVROS -->
    <main id="pagina-livros" class="page-content content-wrapper">
      <div class="age-group-section">
        <h3 class="age-title">
          <span>📚 Biblioteca da Turminha</span>
          <button class="btn-audio-mini" onclick="lerTexto('As histórias mágicas estão sendo preparadas!')">🔊</button>
        </h3>
        <p style="font-size:15px; font-weight:600; color:#475569; text-align:center;">As histórias mágicas da Turminha estão sendo escritas e ilustradas com muito amor!</p>
      </div>
    </main>

    <!-- PÁGINA 6: ROTINA -->
    <main id="pagina-rotina" class="page-content content-wrapper">
      <div class="age-group-section">
        <h3 class="age-title">
          <span>📅 Rotina & Cuidados</span>
          <button class="btn-audio-mini" onclick="lerTexto('Crie a sua rotina diária. No modo grátis você pode adicionar até 3 tarefas.')">🔊</button>
        </h3>
        <div class="interactive-card" style="text-align:left; padding:28px;">
          <h4 style="font-size:18px; font-weight:900; margin-bottom:12px;">Adicionar Tarefa na Rotina:</h4>
          <div class="rotina-add-box" style="display:flex; gap:10px; margin-bottom:20px; flex-wrap:wrap;">
            <input type="text" id="rotina-nova-texto" class="vip-input" style="flex:1; margin-bottom:0;" placeholder="Ex: Hora do banho 🛁">
            <button class="action-btn-pill" style="background:var(--primary); color:#FFF;" onclick="adicionarRotinaPersonalizada()">Adicionar</button>
          </div>
          <div id="lista-rotinas-dinamica"></div>
        </div>
      </div>
    </main>

    <!-- PÁGINA 7: CONQUISTAS (CERTIFICADO SUPER BONITO PARA POSTAR) -->
    <main id="pagina-conquistas" class="page-content content-wrapper">
      <div class="age-group-section">
        <h3 class="age-title">
          <span>🏆 Minhas Conquistas</span>
          <button class="btn-audio-mini" onclick="lerTexto('Minhas conquistas e certificado de Super Fã!')">🔊</button>
        </h3>
        <div class="conquistas-box" style="background: linear-gradient(135deg, #FEF3C7 0%, #FFFBEB 100%); border: 2px solid #FCD34D; border-radius: 12px; padding: 16px 24px; margin-bottom: 20px; display: flex; justify-content: space-between; font-weight: 800; color: #92400E; font-size: 15px;">
          <span>⭐ Pontos: <strong id="placar-pontos">0</strong></span>
          <span id="medalha-status">Iniciante</span>
        </div>

        <div class="interactive-card hover-float" style="border: 4px double #F59E0B; background: linear-gradient(135deg, #FFFBEB 0%, #FEF3C7 100%); padding:40px;">
          <span style="font-size:50px;">🌟</span>
          <h4 style="color:#92400E; font-size:28px; font-weight:900; margin:10px 0;">Certificado Oficial de Super Fã</h4>
          <p style="font-size:14px; color:#78350F; font-weight:700; margin-bottom:20px;">Poste nas redes sociais e marque a Turminha! Queremos ver nosso super fã!</p>
          <input type="text" id="nome-certificado-input" placeholder="Digite seu nome completo" class="vip-input" style="border-color:#FCD34D; max-width:420px; margin:0 auto 16px; display:block; text-align:center; font-size:18px; font-weight:800;">
          <button onclick="gerarCertificadoGeral()" class="action-btn-pill" style="background:#D97706; color:#FFF; border:none; margin:0 auto; padding:14px 32px; font-size:16px;">Gerar Certificado ⭐</button>
          
          <div id="boxCertificadoResultado" style="display:none; margin-top:28px; padding:32px; background:#FFF; border-radius:16px; border:4px double #F59E0B; box-shadow: 0 10px 30px rgba(245,158,11,0.2);">
            <span style="font-size:36px;">🏆</span>
            <p style="font-size:13px; font-weight:800; color:#D97706; text-transform:uppercase; letter-spacing:2px;">Certificado de Reconhecimento</p>
            <h3 style="color:#1D4ED8; font-size:36px; text-transform:uppercase; margin:12px 0;" id="txtNomeCertificado"></h3>
            <p style="font-weight:800; color:#B45309; font-size:17px;">É oficialmente Super Fã da Turminha do Xexéu! 🌟</p>
            <p style="font-size:12px; color:#64748B; margin-top:14px;">📸 Tire um print ou salve e poste marcando @turminhaxe_xeu</p>
          </div>
        </div>
      </div>
    </main>

    <!-- PÁGINA 8: ÁREA VIP -->
    <main id="pagina-vip" class="page-content content-wrapper">
      <div class="age-group-section">
        <div class="vip-lock-container" id="painelVipConteudo" style="background: linear-gradient(135deg, #FFFBEB 0%, #FEF3C7 100%); border: 3px solid #FCD34D; border-radius: var(--radius-lg); padding: 36px; text-align: center;">
          <h3 style="font-size:30px; color:#92400E; font-weight:900; display:flex; justify-content:center; align-items:center; gap:12px;">
            ⭐ Clube VIP da Turminha
            <button class="btn-audio-mini" onclick="lerTexto('Assine o Clube VIP e desbloqueie todas as ferramentas exclusivas!')">🔊</button>
          </h3>
          <div class="vip-price-tag" style="display:inline-block; background:#F59E0B; color:#FFF; font-weight:900; font-size:17px; padding:10px 28px; border-radius:30px; margin:16px 0;">Apenas R$ 6,00 / mês</div>
          
          <div style="display:flex; gap:16px; justify-content:center; flex-wrap:wrap; margin: 20px 0;">
            <a href="https://drive.google.com/drive/folders/1gi1SjbtPXWuFBxhfMEuRpK2z4BFPXIBP?usp=drive_link" target="_blank" class="action-btn-pill" style="background:#2563EB; color:#FFF; border:none; padding:14px 24px; font-size:15px;">📁 Acessar Drive Oficial da Turminha</a>
            <a href="https://drive.google.com/drive/folders/1JO8RfeGen-CeN6eWiw60OENT5E50R6yu?usp=drive_link" target="_blank" class="action-btn-pill" style="background:#0284C7; color:#FFF; border:none; padding:14px 24px; font-size:15px;" title="Drive Azul TEA">🧩 Drive Azul TEA (🚧 Em Construção)</a>
          </div>

          <div style="background:#FFF; padding:28px; border-radius:18px; border:2px dashed #F59E0B; text-align:left; font-size:15.5px; margin:24px auto; color:#78350F; max-width: 950px;">
            <strong style="display:block; font-size:20px; margin-bottom:16px;">💖 O que o Clube VIP desbloqueia para os Pais e para as Crianças?</strong>
            <ul style="margin-left:24px; line-height:2.0; font-weight:600; display:flex; flex-direction:column; gap:8px;">
              <li>📁 <strong>Drive Completo de Atividades Pedagógicas:</strong> Material exclusivo para imprimir em alta qualidade.</li>
              <li>🧩 <strong>Área Especial Pais & TEA (VIP):</strong> Pranchas de rotina visual e histórias sociais adaptadas.</li>
              <li>💬 <strong>Prancha de Comunicação Editável (CAA):</strong> Adicione quantos cards e botões personalizados você quiser!</li>
              <li>⏳ <strong>Temporizador Expandido (Até 30 min):</strong> Opções de 5, 10, 15 e 30 minutos com bloqueio de segurança.</li>
              <li>🔊 <strong>Configuração de Voz Global:</strong> Escolha o tipo exato de voz e a velocidade de leitura para todo o portal.</li>
              <li>🎧 <strong>Caixa do Acalento Completa:</strong> Sons relaxantes para regulação sensorial.</li>
              <li>🌟 <strong>Rotina de Super Força:</strong> Acompanhamento lúdico de vitaminas e medicamentos direto no app.</li>
              <li>🌟 <strong>Diploma de Super Fã Personalizável:</strong> Gere certificados exclusivos com o nome da criança.</li>
              <li>🎬 <strong>Episódios Inéditos e Prévias VIP:</strong> Conteúdos liberados em primeira mão.</li>
              <li>🎮 <strong>Minijogos Exclusivos VIP:</strong> Desafios de histórias, cores e memória avançada.</li>
            </ul>
          </div>

          <div class="vip-grid-forms" style="display:grid; grid-template-columns:repeat(auto-fit, minmax(320px,1fr)); gap:24px; max-width:950px; margin:24px auto 0;">
            <div class="vip-form-box" style="background:#FFF; padding:28px; border-radius:16px; border:2px solid #FCD34D; text-align:left;">
              <h4 style="font-size:19px; color:#92400E; margin-bottom:12px; font-weight:900;">✨ Desbloquear Acesso VIP</h4>
              <input type="email" id="cad-email" class="vip-input" placeholder="Seu E-mail">
              <input type="password" id="cad-senha" class="vip-input" placeholder="Crie uma Senha">
              <a href="javascript:void(0)" class="btn-vip-checkout" id="btnCheckoutVip" onclick="salvarECadastrar()" style="background:linear-gradient(135deg, #F59E0B, #D97706); color:#FFF; font-weight:800; padding:16px; border-radius:12px; text-decoration:none; display:block; text-align:center; font-size:16px;">Quero Ser VIP por R$ 6,00 💳</a>
            </div>

            <div class="vip-form-box" style="background:#FFF; padding:28px; border-radius:16px; border:2px solid #CBD5E1; text-align:left;">
              <h4 style="font-size:19px; color:#1E293B; margin-bottom:12px; font-weight:900;">🔑 Já sou Assinante</h4>
              <input type="email" id="log-email" class="vip-input" placeholder="E-mail Cadastrado">
              <input type="password" id="log-senha" class="vip-input" placeholder="Sua Senha">
              <button onclick="fazerLogin()" id="btnLoginVip" class="action-btn-pill" style="width:100%; justify-content:center; background:#3B82F6; color:#FFF; border:none; min-height:52px; font-size:16px;">Entrar no Clube VIP</button>
            </div>
          </div>
        </div>

        <div class="interactive-card" style="background:#F0F9FF; border:3px solid #BAE6FD; text-align:left; margin-top:32px; padding:32px;">
          <h3 style="color:var(--tea-blue); font-size:22px; font-weight:900; margin-bottom:10px;">📬 Precisa de Ajuda ou quer enviar uma Sugestão?</h3>
          <p style="font-size:15px; font-weight:600; color:#475569; margin-bottom:18px;">Escreva para nós! Sua mensagem será enviada diretamente para <strong>turminhaxexeu@gmail.com</strong>.</p>
          <input type="email" id="suporteEmailVip" class="vip-input" placeholder="Seu e-mail de contato">
          <textarea id="suporteMensagemVip" class="vip-input" placeholder="Escreva aqui..." style="resize:vertical; min-height:120px;"></textarea>
          <button onclick="enviarSuporteReclamacao('Vip')" id="btnEnviarSuporteVip" style="background:var(--tea-blue); color:#FFF; border:none; padding:16px 24px; border-radius:12px; font-size:16px; font-weight:900; cursor:pointer; width:100%;">Enviar Mensagem ✉️</button>
        </div>
      </div>
    </main>

    <!-- CONFIG & PERFIL -->
    <main id="pagina-config" class="page-content content-wrapper">
      <div class="age-group-section">
        <h3 class="age-title">⚙️ Configurações</h3>
        <button class="action-btn-pill" onclick="abrirAreaProtegida('vip')">🔒 Alterar Senha Parental</button>
      </div>
    </main>

    <main id="pagina-perfil" class="page-content content-wrapper">
      <div class="age-group-section">
        <h3 class="age-title">👤 Perfil</h3>
        <p style="font-size:17px; font-weight:700;">Olá, <strong class="nome-usuario-dinamico">Evelyn</strong>!</p>
        <div id="avatarEscolhaGrid" style="display:flex; gap:14px; margin-top:20px; flex-wrap:wrap;"></div>
      </div>
    </main>

    <footer class="content-wrapper">
      <span>© Turminha do Xexéu — eve Design — Todos os direitos reservados.</span>
    </footer>
  </div>

  <script>
    const URL_SCRIPT = "https://script.google.com/macros/s/AKfycbxtV9X0CNAFK69n7JGLBKyPaXCFERg4L4Y-jFw96xj18vueORUGlRtBXOJeJtBboQki/exec";
    const SENHA_MESTRA = "65628467";

    let audioAtivo = true;
    let audioUnlocked = false;
    let pontosConquista = parseInt(localStorage.getItem('turminha_pontos') || '0');
    let isUserVip = localStorage.getItem('turminha_vip_status') === 'ativo';
    
    let rotinasSalvas = JSON.parse(localStorage.getItem('turminha_rotina')) || [
      { id: 1, texto: "☀️ Escovar os dentes ao acordar", feito: false },
      { id: 2, texto: "🍎 Hora do lanche saudável", feito: false }
    ];
    
    let destinoAposGate = 'vip';
    let somAcalentoAtual = null;
    let timerInterval = null;

    const PERSONAGENS = [
      { nome: 'Xexéu', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_XEXEU.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994876/DESENHOS_DA_LOUSA_XEXEU.png', letra: 'X', tag: 'Mascote Oficial', quem: 'Pássaro azul de boina amarela.', gosto: 'Cantar, voar e contar histórias.', frase: 'Educando com alegria!' },
      { nome: 'Capilé', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994882/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_CAPILE.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994874/DESENHOS_DA_LOUSA_CAPILE.png', letra: 'C', tag: 'O Companheiro', quem: 'Cachorrinho fiel de orelhas grandes.', gosto: 'Correr e brincar pelo jardim.', frase: 'Sempre pronto para a brincadeira!' },
      { nome: 'Maya', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994884/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_MAYA.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994875/DESENHOS_DA_LOUSA_MAYA.png', letra: 'M', tag: 'Mãe & Guia', quem: 'Mãe dedicada e porto seguro da família.', gosto: 'Ler histórias e passeios em família.', frase: 'O amor transforma tudo.' },
      { nome: 'Theo', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_THEO.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994877/DESENHOS_DA_LOUSA_THEO.png', letra: 'T', tag: 'Pai Protetor', quem: 'Pai paciente e sempre atencioso.', gosto: 'Ensinar coisas novas e dar abraços.', frase: 'Com calma aprendemos melhor.' },
      { nome: 'Nina', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_NINA.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994876/DESENHOS_DA_LOUSA_NINA.png', letra: 'N', tag: 'Super Esperta', quem: 'Menina de cabelos cacheados.', gosto: 'Descobrir segredos da natureza.', frase: 'Aprender é super divertido!' },
      { nome: 'Iza', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_IZA.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994873/DESENHOS_DA_LOUSA_IZA.png', letra: 'I', tag: 'A Vaidosa', quem: 'Menina charmosa de vestido rosa.', gosto: 'Cantar e usar laços bonitos.', frase: 'Ser gentil é lindo!' },
      { nome: 'Sam', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_SAM.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994876/DESENHOS_DA_LOUSA_SAM.png', letra: 'S', tag: 'Pai Inventor', quem: 'Paizão ruivo apaixonado por criar.', gosto: 'Montar máquinas e brinquedos.', frase: 'Toda ideia é uma invenção!' },
      { nome: 'Lia', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994884/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_LIA.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994875/DESENHOS_DA_LOUSA_LIA.png', letra: 'L', tag: 'Mãe Alegria', quem: 'Mãe cheia de energia positiva.', gosto: 'Dançar e cozinhar.', frase: 'A alegria é nosso superpoder!' },
      { nome: 'Joca', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_JOCA.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994874/DESENHOS_DA_LOUSA_JOCA.png', letra: 'J', tag: 'O Divertido', quem: 'Menino engraçado de camiseta verde.', gosto: 'Fazer piadas e correr.', frase: 'O importante é se divertir!' },
      { nome: 'Leo', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_LEO.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994875/DESENHOS_DA_LOUSA_LEO.png', letra: 'L', tag: 'Explorador Focado', quem: 'Observador detalhista e guia TEA.', gosto: 'Organizar blocos e rotinas.', frase: 'Tudo no nosso próprio tempo.' },
      { nome: 'Beto', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_VOVO_BETO.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994876/DESENHOS_DA_LOUSA_VOVO_BETO.png', letra: 'B', tag: 'Vovô Coruja', quem: 'Vovô de risada boa e óculos.', gosto: 'Passear ao ar livre.', frase: 'A família é a maior riqueza.' },
      { nome: 'Hilda', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_VOVO_HILDA.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994877/DESENHOS_DA_LOUSA_VOVO_HILDA.png', letra: 'H', tag: 'Vovó Acolhedora', quem: 'Vovó de abraços doces.', gosto: 'Fazer bolos.', frase: 'O amor não envelhece.' }
    ];

    function verificarOnboarding() {
      if (localStorage.getItem('turminha_configurado') !== 'true') {
        document.getElementById('modalOnboarding').classList.add('active');
      } else {
        aplicarPreferenciasUsuario();
      }
    }

    function salvarConfiguracaoInicial() {
      const nome = document.getElementById('onb-nome').value.trim() || 'Evelyn';
      const senha = document.getElementById('onb-senha').value.trim();
      const modo = document.getElementById('onb-modo').value;
      
      if(!senha) { alert("Crie uma senha parental de segurança!"); return; }
      
      localStorage.setItem('turminha_nome', nome);
      localStorage.setItem('turminha_senha_parental', senha);
      localStorage.setItem('turminha_modo', modo);
      localStorage.setItem('turminha_configurado', 'true');
      
      document.getElementById('modalOnboarding').classList.remove('active');
      aplicarPreferenciasUsuario();
      lerTexto(`Tudo pronto! Bem-vindo(a), ${nome}!`);
    }

    function aplicarPreferenciasUsuario() {
      const nome = localStorage.getItem('turminha_nome') || 'Evelyn';
      const modo = localStorage.getItem('turminha_modo') || 'familia';
      
      document.querySelectorAll('.nome-usuario-dinamico').forEach(el => el.innerText = nome);
      if (modo === 'adolescente') { document.body.classList.add('teen-mode'); } 
      else { document.body.classList.remove('teen-mode'); }
      atualizarInterfaceVip();
    }

    function atualizarInterfaceVip() {
      const painel = document.getElementById('painelVipConteudo');
      if (!painel) return;
      if (isUserVip) {
        painel.innerHTML = `
          <h3 style="font-size:30px; color:#065F46; font-weight:900; margin-bottom:12px;">🎉 Acesso VIP Confirmado!</h3>
          <p style="font-size:16px; color:#047857; font-weight:700; margin-bottom:20px;">Você tem acesso completo a todo o portal.</p>
          <div style="display:flex; gap:14px; justify-content:center; flex-wrap:wrap;">
            <a href="https://drive.google.com/drive/folders/1gi1SjbtPXWuFBxhfMEuRpK2z4BFPXIBP?usp=drive_link" target="_blank" class="action-btn-pill" style="background:#2563EB; color:#FFF; border:none; padding:14px 24px;">📁 Drive Oficial</a>
            <a href="https://drive.google.com/drive/folders/1JO8RfeGen-CeN6eWiw60OENT5E50R6yu?usp=drive_link" target="_blank" class="action-btn-pill" style="background:#0284C7; color:#FFF; border:none; padding:14px 24px;">🧩 Drive TEA (🚧 Em Construção)</a>
            <button onclick="sairVip()" class="action-btn-pill" style="background:#EF4444; color:#FFF; border:none; padding:14px 24px;">🔒 Sair do VIP</button>
          </div>
        `;
      }
    }

    function sairVip() {
      if(confirm("Deseja sair do modo VIP?")) {
        localStorage.removeItem('turminha_vip_status');
        isUserVip = false;
        window.location.reload();
      }
    }

    function lerTexto(texto) {
      exibirToast(texto);
      if (!audioAtivo || !('speechSynthesis' in window)) return;
      try { window.speechSynthesis.cancel(); const u = new SpeechSynthesisUtterance(texto); u.lang = 'pt-BR'; u.rate = 1.0; u.pitch = 1.05; window.speechSynthesis.speak(u); } catch (e) {}
    }

    function desbloquearAudioMobileOnce() {
      if (!audioUnlocked && 'speechSynthesis' in window) { window.speechSynthesis.speak(new SpeechSynthesisUtterance("")); audioUnlocked = true; }
    }

    function alternarAudioGlobal() {
      audioAtivo = !audioAtivo;
      const btn = document.getElementById('toggleAudioBtn');
      if (audioAtivo) { btn.classList.remove('muted'); document.getElementById('audioIcon').innerText = '🔊'; lerTexto("Voz ligada!"); } 
      else { if ('speechSynthesis' in window) window.speechSynthesis.cancel(); btn.classList.add('muted'); document.getElementById('audioIcon').innerText = '🔇'; exibirToast("Voz desligada!"); }
    }

    function toggleSensoryMode() {
      const ativado = document.body.classList.toggle('sensory-mode');
      document.getElementById('btnSensoryHeader').innerHTML = ativado ? '🌿 Normal' : '🌿 Modo Calmo';
      if (somAcalentoAtual) { somAcalentoAtual.pause(); somAcalentoAtual = null; }
      lerTexto(ativado ? "Modo Calmo ativado" : "Modo normal ativado");
    }

    function exibirToast(t) {
      const toast = document.getElementById('visualToast');
      if (!toast) return;
      toast.innerText = t; toast.classList.add('show');
      setTimeout(() => toast.classList.remove('show'), 2800);
    }

    function tocarSomReal(url) {
      if (somAcalentoAtual) { somAcalentoAtual.pause(); if (somAcalentoAtual.src === url) { somAcalentoAtual = null; lerTexto("Som pausado"); return; } }
      somAcalentoAtual = new Audio(url); somAcalentoAtual.loop = true; somAcalentoAtual.play().catch(() => {}); lerTexto("Tocando som relaxante.");
    }

    function abrirFichaPersonagem(nome) {
      const p = PERSONAGENS.find(x => x.nome === nome) || PERSONAGENS[0];
      document.getElementById('ficha-img').src = p.img;
      document.getElementById('ficha-nome').innerText = p.nome;
      document.getElementById('ficha-apelido').innerText = `"${p.tag}"`;
      document.getElementById('ficha-quem').innerText = p.quem;
      document.getElementById('ficha-gosto').innerText = p.gosto;
      document.getElementById('ficha-frase').innerText = p.frase;
      document.getElementById('btnFichaOuvir').onclick = () => lerTexto(`Oi! Eu sou ${p.nome}, ${p.tag}. ${p.quem} ${p.frase}`);
      document.getElementById('modalFichaPersonagem').classList.add('active');
      lerTexto(`Conheça ${p.nome}!`);
    }

    function fecharFichaPersonagem() { document.getElementById('modalFichaPersonagem').classList.remove('active'); }

    function enviarSuporteReclamacao(local) {
      const email = document.getElementById('suporteEmail' + local).value.trim();
      const mensagem = document.getElementById('suporteMensagem' + local).value.trim();
      const btn = document.getElementById('btnEnviarSuporte' + local);
      if (!email || !mensagem) { alert("Preencha o e-mail e a mensagem!"); return; }
      if(btn) { btn.innerText = "Enviando... ⏳"; btn.disabled = true; }

      fetch(URL_SCRIPT, {
        method: "POST", mode: "no-cors", headers: { "Content-Type": "application/json" },
        body: JSON.stringify({ tipo: "SUPORTE", email: email, mensagem: mensagem })
      }).then(() => {
        lerTexto("Sua mensagem foi enviada!");
        document.getElementById('suporteEmail' + local).value = ''; document.getElementById('suporteMensagem' + local).value = '';
        if(btn) { btn.innerText = "Mensagem Enviada! ✅"; btn.style.background = "#10B981"; setTimeout(() => { btn.innerText = "Enviar Mensagem ✉️"; btn.style.background = "var(--tea-blue)"; btn.disabled = false; }, 3000); }
      }).catch(() => { alert("Erro ao enviar."); if(btn) btn.disabled = false; });
    }

    function salvarECadastrar() {
      const email = document.getElementById('cad-email').value.trim();
      const senha = document.getElementById('cad-senha').value.trim();
      if (!email || !senha) { alert("Preencha e-mail e senha!"); return; }
      fetch(URL_SCRIPT, {
        method: "POST", mode: "no-cors", headers: { "Content-Type": "application/json" },
        body: JSON.stringify({ tipo: "NOVO_CLIENTE", email: email, senha: senha })
      }).then(() => {
        lerTexto("Redirecionando para pagamento..."); window.open("https://pay.kiwify.com.br/avOqrEg", "_blank");
      });
    }

    function fazerLogin() {
      const email = document.getElementById('log-email').value.trim();
      const senha = document.getElementById('log-senha').value.trim();
      if (senha === SENHA_MESTRA) { isUserVip = true; localStorage.setItem('turminha_vip_status', 'ativo'); alert("Acesso Mestre Liberado!"); window.location.reload(); return; }
      if (!email || !senha) { alert("Preencha e-mail e senha."); return; }
      
      const btn = document.getElementById('btnLoginVip');
      if(btn) btn.innerText = "Verificando na Planilha... ⏳";

      fetch(`${URL_SCRIPT}?email=${encodeURIComponent(email)}&senha=${encodeURIComponent(senha)}`)
        .then(res => res.json())
        .then(data => {
          if(data.liberado) { 
            isUserVip = true; 
            localStorage.setItem('turminha_vip_status', 'ativo'); 
            alert("✅ Acesso VIP Confirmado!"); 
            window.location.reload(); 
          } else { 
            alert("❌ Senha incorreta ou assinatura pendente na planilha."); 
            if(btn) btn.innerText = "Entrar no Clube VIP";
          }
        }).catch(() => {
          alert("❌ Erro ao verificar conexão."); 
          if(btn) btn.innerText = "Entrar no Clube VIP";
        });
    }

    function renderizarRotinas() {
      const container = document.getElementById('lista-rotinas-dinamica'); if (!container) return; container.innerHTML = '';
      rotinasSalvas.forEach((r, idx) => {
        const div = document.createElement('div');
        div.style.cssText = "display:flex; justify-content:space-between; align-items:center; background:#FFF; border:2px solid #E2E8F0; padding:12px 16px; border-radius:12px; margin-bottom:10px; font-weight:700;";
        div.innerHTML = `
          <span>${r.texto}</span>
          <div style="display:flex; gap:8px;">
            <button onclick="toggleRotinaStatus(${idx})" style="background:#10B981; color:#FFF; border:none; padding:8px 12px; border-radius:8px; font-weight:900; cursor:pointer;">${r.feito ? 'Desfazer' : '✓ Feito'}</button>
            <button onclick="removerRotina(${idx})" style="background:#EF4444; color:#FFF; border:none; padding:8px 12px; border-radius:8px; font-weight:900; cursor:pointer;">X</button>
          </div>
        `;
        container.appendChild(div);
      });
    }

    function adicionarRotinaPersonalizada() {
      const texto = document.getElementById('rotina-nova-texto').value.trim();
      if (!texto) { alert("Escreva a tarefa!"); return; }
      if (!isUserVip && rotinasSalvas.length >= 3) { alert("No modo Grátis você pode ter até 3 rotinas. Assine o VIP para ilimitadas!"); abrirAreaProtegida('vip'); return; }
      rotinasSalvas.push({ id: Date.now(), texto: texto, feito: false });
      localStorage.setItem('turminha_rotina', JSON.stringify(rotinasSalvas));
      document.getElementById('rotina-nova-texto').value = ''; renderizarRotinas(); lerTexto("Rotina adicionada!");
    }

    function toggleRotinaStatus(index) { rotinasSalvas[index].feito = !rotinasSalvas[index].feito; if(rotinasSalvas[index].feito) adicionarPontos(5); localStorage.setItem('turminha_rotina', JSON.stringify(rotinasSalvas)); renderizarRotinas(); }
    function removerRotina(index) { rotinasSalvas.splice(index, 1); localStorage.setItem('turminha_rotina', JSON.stringify(rotinasSalvas)); renderizarRotinas(); }

    function atualizarBotoesTemporizadorGeral() {
      const container = document.getElementById('botoesTemporizadorGeral');
      if (!container) return;
      if (isUserVip) {
        container.innerHTML = `
          <button class="action-btn-pill" style="min-height:36px; font-size:13px;" onclick="iniciarTemporizador(1)">1 Min</button>
          <button class="action-btn-pill" style="min-height:36px; font-size:13px;" onclick="iniciarTemporizador(5)">5 Min</button>
          <button class="action-btn-pill" style="min-height:36px; font-size:13px;" onclick="iniciarTemporizador(10)">10 Min</button>
          <button class="action-btn-pill" style="min-height:36px; font-size:13px;" onclick="iniciarTemporizador(15)">15 Min</button>
          <button class="action-btn-pill" style="min-height:36px; font-size:13px;" onclick="iniciarTemporizador(30)">30 Min</button>
        `;
      } else {
        container.innerHTML = `
          <button class="action-btn-pill" style="min-height:36px; font-size:13px;" onclick="iniciarTemporizador(1)">1 Min</button>
          <button class="action-btn-pill" style="min-height:36px; font-size:13px;" onclick="iniciarTemporizador(2)">2 Min (Máx Grátis)</button>
        `;
      }
    }

    function iniciarTemporizador(minutos) {
      if (!isUserVip && minutos > 2) {
        alert("🔒 No modo Grátis, o temporizador vai até 2 minutos. Torne-se VIP para liberar até 30 minutos!");
        abrirAreaProtegida('vip');
        return;
      }
      clearInterval(timerInterval);
      let tempoRestante = minutos * 60;
      const totalTempo = tempoRestante;
      const barra = document.getElementById('barra-temporizador');
      const txt = document.getElementById('texto-temporizador');
      
      if(barra) { barra.style.width = '100%'; barra.style.backgroundColor = '#10B981'; }
      if(txt) txt.innerText = `${minutos}:00`;
      lerTexto(`Temporizador iniciado para ${minutos} minutos.`);

      timerInterval = setInterval(() => {
        tempoRestante--;
        const m = Math.floor(tempoRestante / 60);
        const s = tempoRestante % 60;
        if(txt) txt.innerText = `${m}:${s < 10 ? '0' : ''}${s}`;
        
        const pct = (tempoRestante / totalTempo) * 100;
        if(barra) barra.style.width = `${pct}%`;
        if (pct < 30 && barra) barra.style.backgroundColor = '#F59E0B'; 
        if (pct < 10 && barra) barra.style.backgroundColor = '#EF4444'; 
        
        if (tempoRestante <= 0) {
          clearInterval(timerInterval);
          lerTexto("O tempo de uso acabou! Insira a senha parental.");
          if(txt) txt.innerText = "Tempo Esgotado!";
          document.getElementById('modalBloqueioTempo').classList.add('active');
        }
      }, 1000);
    }

    function tentarDesbloquearTelaTempo() {
      const digitada = document.getElementById('senhaDesbloqueioTempo').value.trim();
      const senhaSalva = localStorage.getItem('turminha_senha_parental');
      if (digitada === senhaSalva || digitada === SENHA_MESTRA) {
        document.getElementById('modalBloqueioTempo').classList.remove('active');
        document.getElementById('senhaDesbloqueioTempo').value = '';
        lerTexto("Desbloqueado com sucesso!");
      } else { alert("❌ Senha incorreta!"); }
    }

    function esqueciMinhaSenha() {
      if(confirm("Deseja usar a Senha Mestra de emergência?")) {
        fecharParentalGate(); mudarPagina(destinoAposGate); lerTexto("Acesso liberado.");
      }
    }
    function esqueciMinhaSenhaTempo() {
      if(confirm("Deseja usar a Senha Mestra de emergência?")) {
        document.getElementById('modalBloqueioTempo').classList.remove('active');
        lerTexto("Tela destravada.");
      }
    }

    function abrirAreaProtegida(destino) {
      destinoAposGate = destino;
      document.getElementById('respostaDesafio').value = '';
      document.getElementById('modalParentalGate').classList.add('active');
      lerTexto("Digite sua senha parental.");
    }
    function fecharParentalGate() { document.getElementById('modalParentalGate').classList.remove('active'); }
    function verificarParentalGate() {
      const resp = document.getElementById('respostaDesafio').value.trim();
      const senhaSalva = localStorage.getItem('turminha_senha_parental');
      if (resp === senhaSalva || resp === SENHA_MESTRA) {
        fecharParentalGate(); mudarPagina(destinoAposGate); lerTexto("Acesso liberado.");
      } else { alert("Senha incorreta!"); lerTexto("Senha incorreta."); }
    }

    function mudarPagina(p) {
      const abas = ['inicio', 'videos', 'jogos', 'tea', 'livros', 'rotina', 'conquistas', 'vip', 'config', 'perfil'];
      abas.forEach(id => {
        const el = document.getElementById('pagina-' + id); const tab = document.getElementById('btn-tab-' + id);
        if (el) el.classList.remove('active-page'); if (tab) tab.classList.remove('active');
      });
      const target = document.getElementById('pagina-' + p); const targetTab = document.getElementById('btn-tab-' + p);
      if (target) target.classList.add('active-page'); if (targetTab) targetTab.classList.add('active');
      
      if (p === 'inicio') atualizarBotoesTemporizadorGeral();
      if (p === 'jogos') { renderizarLousaBtns(); setTimeout(redimensionarCanvas, 50); }
      if (p === 'perfil') criarSeletorAvatar();
      if (p === 'rotina') renderizarRotinas();
      if (p === 'vip') atualizarInterfaceVip();
      window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    function mudarSubJogo(sub) {
      ['lousa', 'contar', 'letras', 'memoria', 'quiz'].forEach(s => {
        const el = document.getElementById('game-' + s);
        const btn = document.getElementById('subtab-' + s);
        if(el) el.classList.remove('active-game-page');
        if(btn) btn.style.background = '#FFF';
      });
      const target = document.getElementById('game-' + sub);
      const activeBtn = document.getElementById('subtab-' + sub);
      if(target) target.classList.add('active-game-page');
      if(activeBtn) activeBtn.style.background = 'var(--primary)';
      if(sub === 'lousa') setTimeout(redimensionarCanvas, 50);
      if(sub === 'contar') carregarJogoContar();
      if(sub === 'letras') carregarJogoLetra();
      if(sub === 'memoria') iniciarMemoria();
      if(sub === 'quiz') carregarQuiz();
    }

    /* LOUSA */
    const canvas = document.getElementById('paintCanvas'); const ctx = canvas ? canvas.getContext('2d') : null;
    let desenhando = false, corAtual = '#3B82F6', tamanhoPincel = 6, imgContornoAtual = null;

    function renderizarLousaBtns() {
      const grid = document.getElementById('coloringSelectGrid'); if (!grid) return; grid.innerHTML = '';
      
      // Botão Desenho Livre
      const btnLivre = document.createElement('button'); 
      btnLivre.className = 'btn-color-draw selected'; 
      btnLivre.innerHTML = '✏️ Desenho Livre';
      btnLivre.onclick = () => { 
        imgContornoAtual = null; 
        limparCanvas(); 
        document.querySelectorAll('.btn-color-draw').forEach(b => b.classList.remove('selected')); 
        btnLivre.classList.add('selected'); 
      };
      grid.appendChild(btnLivre);

      const limit = isUserVip ? PERSONAGENS.length : 3;
      for(let i = 0; i < limit; i++) {
        const item = PERSONAGENS[i]; 
        const btn = document.createElement('button'); 
        btn.className = 'btn-color-draw'; 
        btn.innerHTML = `<img src="${item.img}"> ${item.nome}`;
        btn.onclick = () => carregarContornoPintar(item.lousa, btn); 
        grid.appendChild(btn);
      }
      if(!isUserVip) {
        const btnVip = document.createElement('button'); 
        btnVip.className = 'btn-color-draw'; 
        btnVip.style.cssText = "border-color:#F59E0B; background:#FFFBEB; color:#92400E;";
        btnVip.innerHTML = '🔒 +9 Desenhos (VIP)'; 
        btnVip.onclick = () => abrirAreaProtegida('vip'); 
        grid.appendChild(btnVip);
      }
    }

    function redimensionarCanvas() {
      if (!canvas || !canvas.parentElement) return;
      canvas.width = canvas.parentElement.clientWidth - 48; canvas.height = 450;
      if (imgContornoAtual) desenharContorno(imgContornoAtual);
    }
    function mudarCor(c) { corAtual = c; }
    function limparCanvas() { if (ctx) ctx.clearRect(0, 0, canvas.width, canvas.height); if (imgContornoAtual) desenharContorno(imgContornoAtual); }
    
    function carregarContornoPintar(url, btn) {
      document.querySelectorAll('.btn-color-draw').forEach(b => b.classList.remove('selected')); 
      if (btn) btn.classList.add('selected');
      limparCanvas(); 
      const img = new Image(); 
      img.crossOrigin = "Anonymous"; 
      img.src = url;
      img.onload = () => { 
        imgContornoAtual = img; 
        desenharContorno(img); 
      };
    }

    function desenharContorno(img) {
      const ratio = Math.min(canvas.width / img.width, canvas.height / img.height) * 0.85;
      const w = img.width * ratio; const h = img.height * ratio; const x = (canvas.width - w) / 2; const y = (canvas.height - h) / 2;
      ctx.globalAlpha = 0.35; ctx.drawImage(img, x, y, w, h); ctx.globalAlpha = 1.0;
    }
    
    function salvarFotoDesenho() { 
      const link = document.createElement('a'); 
      link.download = 'desenho.png'; 
      link.href = canvas.toDataURL(); 
      link.click(); 
      lerTexto("Salvo!"); 
    }

    if (canvas) {
      const getPos = (e) => { const r = canvas.getBoundingClientRect(); const cx = e.touches ? e.touches[0].clientX : e.clientX; const cy = e.touches ? e.touches[0].clientY : e.clientY; return { x: cx - r.left, y: cy - r.top }; };
      const iniciar = (e) => { desenhando = true; const p = getPos(e); ctx.beginPath(); ctx.moveTo(p.x, p.y); ctx.strokeStyle = corAtual; ctx.lineWidth = tamanhoPincel; ctx.lineCap = 'round'; };
      const mover = (e) => { if (!desenhando) return; const p = getPos(e); ctx.lineTo(p.x, p.y); ctx.stroke(); if(e.preventDefault) e.preventDefault(); };
      const parar = () => { desenhando = false; };
      canvas.addEventListener('mousedown', iniciar); canvas.addEventListener('mousemove', mover); canvas.addEventListener('mouseup', parar);
      canvas.addEventListener('touchstart', iniciar, { passive: false }); canvas.addEventListener('touchmove', mover, { passive: false }); canvas.addEventListener('touchend', parar);
    }

    /* MINIGAMES */
    let qContar = 0;
    function carregarJogoContar() {
      qContar = Math.floor(Math.random() * 4) + 1; const char = PERSONAGENS[Math.floor(Math.random() * PERSONAGENS.length)];
      const display = document.getElementById('countDisplay'); if(!display) return; display.innerHTML = '';
      for (let i = 0; i < qContar; i++) { const img = document.createElement('img'); img.src = char.img; img.style.cssText = 'width:70px; height:70px; object-fit:contain;'; display.appendChild(img); }
      const opts = document.getElementById('countOptions'); opts.innerHTML = '';
      for (let n = 1; n <= 4; n++) {
        const btn = document.createElement('button'); btn.className = 'btn-choice'; btn.innerText = n;
        btn.onclick = () => { if (n === qContar) { btn.classList.add('acertou'); lerTexto("Acertou!"); adicionarPontos(5); setTimeout(() => { btn.classList.remove('acertou'); carregarJogoContar(); }, 800); } else { btn.classList.add('errou'); lerTexto("Tente de novo!"); setTimeout(() => btn.classList.remove('errou'), 500); } };
        opts.appendChild(btn);
      }
    }

    function carregarJogoLetra() {
      const p = PERSONAGENS[Math.floor(Math.random() * PERSONAGENS.length)];
      document.getElementById('nome-letra-personagem').innerText = p.nome; document.getElementById('img-letra-personagem').src = p.img;
      const container = document.getElementById('opcoes-letras'); container.innerHTML = '';
      ['A', 'B', 'C', 'D', 'E', 'F', 'I', 'J', 'L', 'M', 'N', 'P', 'S', 'T', 'X'].sort(() => Math.random() - 0.5).slice(0, 3).concat(p.letra).sort(() => Math.random() - 0.5).forEach(l => {
        const btn = document.createElement('button'); btn.className = 'btn-choice'; btn.innerText = l;
        btn.onclick = () => { if (l === p.letra) { btn.classList.add('acertou'); lerTexto("Muito bem!"); adicionarPontos(5); setTimeout(() => { btn.classList.remove('acertou'); carregarJogoLetra(); }, 800); } else { btn.classList.add('errou'); lerTexto("Tente outra vez!"); setTimeout(() => btn.classList.remove('errou'), 500); } };
        container.appendChild(btn);
      });
    }

    function iniciarMemoria() {
      const sorteados = [...PERSONAGENS].sort(() => Math.random() - 0.5).slice(0, 4);
      let cMem = [...sorteados.map(p=>p.img), ...sorteados.map(p=>p.img)].sort(() => Math.random() - 0.5);
      const board = document.getElementById('memoryBoard'); if(!board) return; board.innerHTML = '';
      let pCarta = null, travaMem = false, acertosMem = 0;
      cMem.forEach(src => {
        const card = document.createElement('div'); card.className = 'memory-card'; card.dataset.img = src; card.innerText = '❓';
        card.onclick = () => {
          if (travaMem || card.classList.contains('flipped')) return;
          card.classList.add('flipped'); card.innerHTML = `<img src="${src}" style="width:80%; height:80%; object-fit:contain;">`;
          if (!pCarta) pCarta = card;
          else {
            if (pCarta.dataset.img === src) { acertosMem++; lerTexto("Achou o par!"); pCarta = null; adicionarPontos(3); if (acertosMem === 4) setTimeout(iniciarMemoria, 1500); } 
            else { travaMem = true; setTimeout(() => { pCarta.classList.remove('flipped'); pCarta.innerText = '❓'; card.classList.remove('flipped'); card.innerText = '❓'; pCarta = null; travaMem = false; }, 800); }
          }
        }; board.appendChild(card);
      });
    }

    function carregarQuiz() {
      const p = PERSONAGENS[Math.floor(Math.random() * PERSONAGENS.length)];
      document.getElementById('quiz-img').src = p.img; const container = document.getElementById('quiz-options'); container.innerHTML = '';
      [p.nome, PERSONAGENS[Math.floor(Math.random()*PERSONAGENS.length)].nome].sort(() => Math.random() - 0.5).forEach(o => {
        const btn = document.createElement('button'); btn.className = 'btn-choice'; btn.innerText = o;
        btn.onclick = () => { if (o === p.nome) { btn.classList.add('acertou'); lerTexto("Isso mesmo!"); adicionarPontos(5); setTimeout(() => { btn.classList.remove('acertou'); carregarQuiz(); }, 800); } else { btn.classList.add('errou'); lerTexto("Tente de novo!"); setTimeout(() => btn.classList.remove('errou'), 500); } };
        container.appendChild(btn);
      });
    }

    function adicionarPontos(n) {
      pontosConquista += n; localStorage.setItem('turminha_pontos', pontosConquista);
      const placa = document.getElementById('placar-pontos'); if (placa) placa.innerText = pontosConquista;
      const tit = pontosConquista >= 50 ? "🌟 Super Fã Mestre" : pontosConquista >= 20 ? "⭐ Explorador" : "⭐ Iniciante";
      const med = document.getElementById('medalha-status'); if (med) med.innerText = tit;
    }

    function criarSeletorAvatar() {
      const grid = document.getElementById('avatarEscolhaGrid'); if (!grid || grid.children.length > 0) return;
      const avatarAtual = localStorage.getItem('turminha_avatar') || PERSONAGENS[0].img;
      PERSONAGENS.forEach(p => {
        const img = document.createElement('img'); img.src = p.img;
        img.style.cssText = `width:70px; height:70px; border-radius:50%; border:3px solid ${p.img === avatarAtual ? '#F59E0B' : '#CBD5E1'}; cursor:pointer; background:#FFF; padding:4px; transition:transform 0.2s;`;
        img.onclick = () => { document.querySelectorAll('#avatarEscolhaGrid img').forEach(b => b.style.borderColor = '#CBD5E1'); img.style.borderColor = '#F59E0B'; localStorage.setItem('turminha_avatar', p.img); lerTexto(`${p.nome} escolhido!`); };
        grid.appendChild(img);
      });
    }

    function gerarCertificadoGeral() {
      const nome = document.getElementById('nome-certificado-input').value.trim();
      if (!nome) { alert("Digite o nome!"); return; }
      document.getElementById('txtNomeCertificado').innerText = nome;
      document.getElementById('boxCertificadoResultado').style.display = 'block';
      lerTexto(`Parabéns, ${nome}! Certificado Gerado.`);
    }

    window.onload = () => {
      verificarOnboarding();
      adicionarPontos(0); 
      carregarJogoContar(); carregarJogoLetra(); iniciarMemoria(); carregarQuiz();
      renderizarRotinas();
      atualizarBotoesTemporizadorGeral();
      window.addEventListener('resize', redimensionarCanvas); setTimeout(redimensionarCanvas, 200);
    };
  </script>
</body>
</html>
