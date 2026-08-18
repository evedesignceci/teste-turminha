<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
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

    body.sensory-mode {
      --bg-gradient: #F1F5F9 !important; --primary: #475569 !important; --primary-dark: #334155 !important;
      --secondary: #64748B !important; --tea-blue: #334155 !important; --tea-light: #FFFFFF !important;
      background: var(--bg-gradient) !important; color: #1E293B !important;
    }
    body.sensory-mode * { animation: none !important; box-shadow: none !important; transition: none !important; }
    body.sensory-mode .interactive-card, body.sensory-mode .tea-box, body.sensory-mode .video-card { background: #FFFFFF !important; border: 2px solid #CBD5E1 !important; }
    body.sensory-mode .floating-vip-badge, body.sensory-mode .cookie-banner { display: none !important; }

    * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Poppins', system-ui, sans-serif; -webkit-tap-highlight-color: transparent; }
    body { background: var(--bg-gradient); color: var(--text-main); min-height: 100vh; transition: background 0.3s ease; overflow-x: hidden; }

    @keyframes float { 0% { transform: translateY(0px); } 50% { transform: translateY(-6px); } 100% { transform: translateY(0px); } }
    @keyframes pulse { 0% { transform: scale(1); } 50% { transform: scale(1.03); } 100% { transform: scale(1); } }
    @keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }

    .float-anim { animation: float 4s ease-in-out infinite; }
    .pulse-anim { animation: pulse 2.5s infinite; }
    .hover-float { transition: transform 0.25s cubic-bezier(0.4, 0, 0.2, 1); }
    .hover-float:hover { transform: translateY(-4px); }

    .app-container { width: 100%; min-height: 100vh; display: flex; flex-direction: column; gap: 20px; padding-bottom: 40px; }
    .content-wrapper { width: 100%; max-width: 1300px; margin-left: auto; margin-right: auto; }
    @media (max-width: 1340px) { .content-wrapper { width: calc(100% - 24px); } }

    /* CABEÇALHO LÚDICO & BOTÕES APRIMORADOS */
    header { background: linear-gradient(135deg, #BAE6FD 0%, #E0F2FE 100%); display: flex; align-items: center; justify-content: space-between; border-radius: var(--radius-lg); padding: 16px 24px; margin-top: 16px; box-shadow: var(--shadow-sm); gap: 12px; flex-wrap: wrap; border: 2px solid #FFFFFF; }
    .logo-img { max-width: 160px; height: auto; object-fit: contain; }
    .header-actions { display: flex; align-items: center; gap: 10px; flex-wrap: wrap; }
    
    .action-btn-pill { background: #FFFFFF; border: 2.5px solid var(--primary); color: var(--primary-dark); font-weight: 800; font-size: 13.5px; padding: 10px 18px; border-radius: 50px; cursor: pointer; display: flex; align-items: center; gap: 6px; box-shadow: 0 4px 12px rgba(59, 130, 246, 0.15); transition: all 0.2s ease; }
    .action-btn-pill:hover { background: var(--primary); color: #FFF; transform: translateY(-2px); box-shadow: 0 6px 16px rgba(59, 130, 246, 0.3); }
    .action-btn-pill.muted { background: #FEE2E2; border-color: #EF4444; color: #991B1B; }

    .page-nav { display: flex; gap: 10px; background: #F0F9FF; padding: 10px; border-radius: var(--radius-lg); border: 2px solid #BAE6FD; overflow-x: auto; scrollbar-width: thin; flex-wrap: nowrap; box-shadow: var(--shadow-sm); }
    @media (min-width: 1024px) { .page-nav { flex-wrap: wrap; justify-content: center; } }
    .nav-tab-btn { flex: 0 0 auto; padding: 12px 20px; border: none; border-radius: 12px; font-weight: 800; font-size: 14px; cursor: pointer; background: #FFFFFF; color: var(--text-muted); display: flex; align-items: center; justify-content: center; gap: 6px; box-shadow: 0 2px 8px rgba(0,0,0,0.04); transition: all 0.25s ease; }
    .nav-tab-btn:hover { background: #E0F2FE; color: var(--primary); transform: translateY(-2px); }
    .nav-tab-btn.active { background: var(--primary); color: #FFFFFF; box-shadow: 0 6px 16px rgba(59, 130, 246, 0.4); transform: translateY(-3px); }
    .nav-tab-btn.tea-tab.active { background: var(--tea-blue); color: #FFF; }
    .nav-tab-btn.vip-tab.active { background: linear-gradient(135deg, #F59E0B, #D97706); color: #FFF; }

    .page-content { display: none; flex-direction: column; gap: 24px; animation: fadeIn 0.3s ease; }
    .page-content.active-page { display: flex; }

    /* ESTILOS COMUNS DE CARTÕES E BLOCOS */
    .banner-container { width: 100%; border-radius: var(--radius-lg); overflow: hidden; box-shadow: var(--shadow-sm); border: 3px solid #FFF; }
    .banner-img { width: 100%; height: 100%; min-height: 240px; display: block; object-fit: cover; }
    .intro-box { background: linear-gradient(135deg, #FEF3C7 0%, #FFFBEB 100%); border: 3px solid #FCD34D; border-radius: var(--radius-lg); padding: 24px; display: flex; flex-direction: column; justify-content: center; gap: 12px; box-shadow: var(--shadow-sm); }
    
    .btn-audio-mini { background: linear-gradient(135deg, #FBBF24, #F59E0B); border: none; border-radius: 50%; width: 42px; height: 42px; min-width: 42px; cursor: pointer; font-size: 16px; display: flex; align-items: center; justify-content: center; color: #FFF; box-shadow: 0 4px 12px rgba(245, 158, 11, 0.4); transition: all 0.2s; }
    .btn-audio-mini:hover { transform: scale(1.1) rotate(5deg); }

    .age-group-section { background: #FFFFFF; border-radius: var(--radius-lg); padding: 24px; border: 2px solid #E2E8F0; box-shadow: var(--shadow-sm); }
    .age-title { font-size: 22px; font-weight: 900; color: var(--primary-dark); margin-bottom: 16px; display: flex; align-items: center; justify-content: space-between; }
    .interactive-card { background: #F8FAFC; border-radius: var(--radius-md); padding: 20px; text-align: center; border: 2px solid #E2E8F0; width: 100%; box-shadow: 0 2px 8px rgba(0,0,0,0.02); }

    /* PERSONAGENS E GRID */
    .floating-cards-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); gap: 16px; }
    .floating-char-card { background: #FFFFFF; border-radius: var(--radius-lg); padding: 16px 12px; text-align: center; border: 3px solid #E2E8F0; box-shadow: var(--shadow-sm); display: flex; flex-direction: column; align-items: center; gap: 8px; cursor: pointer; transition: all 0.3s ease; }
    .floating-char-card:hover { transform: translateY(-6px); border-color: var(--primary); box-shadow: var(--shadow-md); }
    .floating-char-img { width: 90px; height: 90px; object-fit: contain; border-radius: 50%; background: #F0F9FF; padding: 6px; }
    .floating-char-name { font-size: 16px; font-weight: 900; color: var(--text-main); }
    .floating-char-tag { font-size: 11px; font-weight: 800; padding: 4px 10px; border-radius: 20px; text-transform: uppercase; }

    /* VÍDEOS E MÍDIA */
    .media-section-grid { display: grid; grid-template-columns: 1fr; gap: 24px; }
    @media (min-width: 900px) { .media-section-grid { grid-template-columns: 1fr 1fr; } }
    .video-card { background: #FFFFFF; border-radius: var(--radius-lg); padding: 20px; box-shadow: var(--shadow-sm); border: 2px solid #E2E8F0; text-align: center; }
    .video-wrapper { position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; border-radius: var(--radius-md); }
    .video-wrapper iframe { position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0; }
    .spotify-wrapper { width: 100%; height: 352px; border-radius: 14px; overflow: hidden; border: 2px solid #1DB954; }

    .media-card-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr)); gap: 16px; margin-top: 14px; }
    .media-item-box { background: #FFF; border: 2.5px solid #CBD5E1; border-radius: var(--radius-md); padding: 16px 12px; display: flex; flex-direction: column; align-items: center; gap: 8px; cursor: pointer; position: relative; transition: all 0.2s; box-shadow: 0 2px 6px rgba(0,0,0,0.03); }
    .media-item-box:hover { transform: translateY(-4px); border-color: var(--primary); box-shadow: 0 6px 14px rgba(59,130,246,0.15); }
    .media-item-box.locked { background: #FFFBEB; border-color: #FCD34D; }
    .media-badge-vip { position: absolute; top: 8px; right: 8px; background: #F59E0B; color: #FFF; font-size: 10px; font-weight: 800; padding: 4px 8px; border-radius: 8px; }

    /* LOUSA MÁGICA */
    #paintCanvas { background: #FFF; border: 4px solid var(--primary); border-radius: var(--radius-lg); width: 100%; height: 350px; touch-action: none; cursor: crosshair; }
    @media (min-width: 1024px) { #paintCanvas { height: 480px; } }
    .btn-color-draw { background: #FFF; border: 2.5px solid #CBD5E1; padding: 10px 14px; border-radius: 12px; font-weight: 800; font-size: 13px; cursor: pointer; display: flex; align-items: center; gap: 6px; transition: all 0.2s; }
    .btn-color-draw.selected { border-color: var(--primary); background: #E0F2FE; transform: scale(1.05); box-shadow: 0 4px 10px rgba(59,130,246,0.2); }
    .btn-color-draw img { width: 26px; height: 26px; object-fit: contain; }

    .game-btn-grid { display: flex; justify-content: center; gap: 12px; flex-wrap: wrap; margin-top: 16px; }
    .btn-choice { background: var(--purple); color: #FFF; border: none; padding: 16px 24px; font-weight: 900; font-size: 18px; border-radius: 14px; cursor: pointer; min-width: 64px; box-shadow: 0 4px 14px rgba(139, 92, 246, 0.3); transition: transform 0.15s ease; }
    .btn-choice:active { transform: scale(0.92); }
    .btn-choice.acertou { background: #10B981 !important; transform: scale(1.1); }
    .btn-choice.errou { background: #EF4444 !important; transform: scale(0.95) rotate(-3deg); }

    /* MODAIS */
    .modal-overlay { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(15, 23, 42, 0.8); backdrop-filter: blur(6px); z-index: 99999; justify-content: center; align-items: center; padding: 20px; }
    .modal-overlay.active { display: flex; animation: fadeIn 0.3s; }
    .modal-box { background: #FFF; border-radius: var(--radius-lg); padding: 28px; max-width: 460px; width: 100%; text-align: center; border: 4px solid var(--primary); position: relative; box-shadow: 0 20px 40px rgba(0,0,0,0.3); }
    .modal-close { position: absolute; top: 16px; right: 16px; background: #F1F5F9; border: none; width: 36px; height: 36px; border-radius: 50%; font-weight: bold; font-size: 16px; cursor: pointer; }
    
    .vip-input { width: 100%; padding: 12px 16px; font-size: 14px; border: 2.5px solid #CBD5E1; border-radius: 12px; margin-bottom: 12px; outline: none; font-family: 'Poppins'; }
    .vip-input:focus { border-color: var(--primary); }

    #visualToast { position: fixed; bottom: 80px; left: 50%; transform: translateX(-50%) translateY(100px); background: #0F172A; color: #FFF; padding: 12px 24px; border-radius: 30px; font-size: 14px; font-weight: 700; transition: transform 0.3s; z-index: 999999; pointer-events: none; opacity: 0; }
    #visualToast.show { transform: translateX(-50%) translateY(0); opacity: 1; }
    
    .floating-vip-badge { position: fixed; bottom: 24px; right: 24px; background: linear-gradient(135deg, #F59E0B 0%, #D97706 100%); color: #FFF; padding: 14px 24px; border-radius: 50px; font-size: 15px; font-weight: 900; box-shadow: 0 8px 24px rgba(245, 158, 11, 0.4); display: flex; align-items: center; gap: 8px; cursor: pointer; border: 2px solid #FDE68A; z-index: 999; }
    
    footer { text-align: center; padding: 30px 20px; font-size: 13px; color: var(--text-muted); font-weight: 600; margin-top: auto; display: flex; flex-direction: column; gap: 8px; }
    footer a { color: var(--primary); cursor: pointer; text-decoration: underline; }
  </style>
</head>
<body onclick="desbloquearAudioMobileOnce()">

  <div id="visualToast">Aviso</div>

  <!-- MODAL: ONBOARDING (FICHA DE PREENCHIMENTO INICIAL) -->
  <div id="modalOnboarding" class="modal-overlay">
    <div class="modal-box" style="max-width: 500px; text-align: left; border-color: #3B82F6;">
      <h3 style="color: var(--primary-dark); font-size: 24px; margin-bottom: 8px; font-weight: 900; text-align:center; display:flex; align-items:center; justify-content:center; gap:10px;">
        👋 Bem-vindo à Turminha!
        <button class="btn-audio-mini" style="width:36px;height:36px;font-size:14px;" onclick="lerTexto('Bem-vindo à Turminha do Xexéu! Vamos configurar o portal para o seu pequeno.')">🔊</button>
      </h3>
      <p style="font-size: 14px; color: #475569; margin-bottom: 20px; font-weight: 600; text-align:center;">Configure o portal para iniciar a diversão com segurança.</p>

      <label style="font-size: 14px; font-weight: 800; color: var(--primary-dark); display: block; margin-bottom: 6px;">Qual o nome da criança?</label>
      <input type="text" id="onb-nome" class="vip-input" placeholder="Ex: Lucas">

      <label style="font-size: 14px; font-weight: 800; color: var(--primary-dark); display: block; margin-bottom: 6px; margin-top:12px;">
        Crie uma Senha Parental (PIN numérico ou texto):
        <span style="font-size:11.5px; color:#EF4444; font-weight:600; display:block;">Para proteger Configurações e Área VIP de toques infantis.</span>
      </label>
      <input type="password" id="onb-senha" class="vip-input" placeholder="Ex: 1234">

      <div style="background:#F0F9FF; border:2.5px solid #BAE6FD; padding:12px 16px; border-radius:12px; margin: 16px 0; font-size:13px; color:#0369A1; font-weight:700; line-height: 1.6;">
        <strong style="display:block; margin-bottom:6px; color:#0284C7; font-size:14px;">🎁 Como funciona o portal:</strong>
        • <strong>Grátis:</strong> Acesso aos 3 primeiros desenhos da lousa, 3 rotinas e minijogos básicos.<br>
        • <strong>VIP (R$ 6,00/mês):</strong> Lousa Completa com 12 personagens, Rotinas Ilimitadas, Drive Pedagógico completo e Espaço TEA avançado!
      </div>

      <button onclick="salvarConfiguracaoInicial()" style="background: #10B981; color: #FFF; border: none; padding: 14px; border-radius: 12px; font-size: 16px; font-weight: 900; cursor: pointer; width: 100%; transition: transform 0.2s; box-shadow: 0 4px 12px rgba(16,185,129,0.3);">
        Salvar e Entrar! 🚀
      </button>
    </div>
  </div>

  <!-- MODAL: FICHA DO PERSONAGEM -->
  <div id="modalFichaPersonagem" class="modal-overlay">
    <div class="modal-box">
      <button class="modal-close" onclick="fecharFichaPersonagem()">✕</button>
      <img id="ficha-img" src="" alt="Personagem" class="pulse-anim" style="width: 110px; height: 110px; object-fit: contain; margin-bottom: 12px;">
      <h3 id="ficha-nome" style="color: var(--primary-dark); font-weight: 900; font-size: 24px;"></h3>
      <p id="ficha-apelido" style="color: var(--purple); font-weight: 800; font-size: 15px; margin-bottom: 16px;"></p>
      <button id="btnFichaOuvir" class="btn-choice hover-float" style="padding: 12px 20px; font-size: 15px; margin-bottom: 16px; background: #F59E0B;">🔊 Ouvir Apresentação</button>
      <div style="text-align: left; background: #F8FAFC; padding: 16px; border-radius: 12px; border: 2px solid #E2E8F0; font-size: 14px; display: flex; flex-direction: column; gap: 10px;">
        <p><strong>🌟 Quem sou eu?</strong> <span id="ficha-quem"></span></p>
        <p><strong>💖 O que eu gosto?</strong> <span id="ficha-gosto"></span></p>
        <p><strong>💬 Minha frase:</strong> <em style="color:#475569;">"<span id="ficha-frase"></span>"</em></p>
      </div>
    </div>
  </div>

  <!-- MODAL: PARENTAL GATE (PEDE A SENHA CRIADA NO ONBOARDING) -->
  <div id="modalParentalGate" class="modal-overlay">
    <div class="modal-box" style="border-color:#F59E0B; max-width:400px;">
      <h3 style="color: #92400E; font-size: 22px; margin-bottom: 8px; font-weight: 900;">🔒 Acesso dos Responsáveis</h3>
      <p style="font-size: 14px; color: #475569; margin-bottom: 16px; font-weight: 600;">Digite sua <strong>Senha Parental (PIN)</strong>:</p>
      <input type="password" id="respostaDesafio" class="vip-input" style="text-align:center; font-size:22px; letter-spacing:4px;" placeholder="****">
      <div style="display: flex; gap: 12px; justify-content: center;">
        <button onclick="fecharParentalGate()" style="padding: 12px 20px; border: none; border-radius: 10px; background: #E2E8F0; font-weight: 800; cursor: pointer; font-size: 14px;">Voltar</button>
        <button onclick="verificarParentalGate()" style="padding: 12px 24px; border: none; border-radius: 10px; background: #F59E0B; color: #FFF; font-weight: 900; cursor: pointer; font-size: 14px;">Entrar ➔</button>
      </div>
    </div>
  </div>

  <div class="floating-vip-badge float-anim" onclick="abrirAreaProtegida('vip')">
    <span style="font-size:18px;">⭐</span><span>Seja VIP (R$ 6,00)</span>
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

    <!-- NAVEGAÇÃO -->
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
      <section class="banner-intro-grid">
        <div class="banner-container"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994339/BANNER_SITE_TURMINHA_DO_XEXEU.png" class="banner-img"></div>
        <div class="intro-box hover-float">
          <h2><span>✨ Educando com Alegria e Amor</span><button class="btn-audio-mini" onclick="lerTexto('Mais do que um nome divertido, a Turminha do Xexéu é o nosso jeito de honrar as raízes e a história da nossa família.')">🔊</button></h2>
          <p>Mais do que um nome divertido, a <strong>Turminha do Xexéu</strong> é o nosso jeito de honrar as raízes e a história da nossa família.</p>
          <p>O nome <strong>Xexéu</strong> é uma homenagem que atravessa gerações. Ele honra a memória de Mariano Xexéu e celebra a vida de seu filho, Pedro Mariano, grande inspiração para o nosso querido Vovô Beto.</p>
        </div>
      </section>

      <section class="section-family-container">
        <div>
          <h3 class="family-group-title"><span>✨ O Símbolo e Mascote</span><button class="btn-audio-mini" onclick="lerTexto('Toque nos personagens para ouvir!')">🔊</button></h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-especial" onclick="abrirFichaPersonagem('Xexéu')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_XEXEU.png" class="floating-char-img"><span class="floating-char-name">Xexéu</span><span class="floating-char-tag">Mascote Oficial</span></div>
            <div class="floating-char-card card-especial" onclick="abrirFichaPersonagem('Capilé')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994882/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_CAPILE.png" class="floating-char-img"><span class="floating-char-name">Capilé</span><span class="floating-char-tag">O Companheiro</span></div>
          </div>
        </div>

        <div>
          <h3 class="family-group-title"><span>💖 A Casa da Maya e do Theo</span><button class="btn-audio-mini" onclick="lerTexto('A Casa da Maya e do Theo.')">🔊</button></h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-f1" onclick="abrirFichaPersonagem('Maya')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994884/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_MAYA.png" class="floating-char-img"><span class="floating-char-name">Maya</span></div>
            <div class="floating-char-card card-f1" onclick="abrirFichaPersonagem('Theo')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_THEO.png" class="floating-char-img"><span class="floating-char-name">Theo</span></div>
            <div class="floating-char-card card-f1" onclick="abrirFichaPersonagem('Nina')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_NINA.png" class="floating-char-img"><span class="floating-char-name">Nina</span></div>
            <div class="floating-char-card card-f1" onclick="abrirFichaPersonagem('Iza')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_IZA.png" class="floating-char-img"><span class="floating-char-name">Iza</span></div>
          </div>
        </div>

        <div>
          <h3 class="family-group-title"><span>⚡ A Casa do Sam e da Lia</span><button class="btn-audio-mini" onclick="lerTexto('A Casa do Sam e da Lia.')">🔊</button></h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-f2" onclick="abrirFichaPersonagem('Sam')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_SAM.png" class="floating-char-img"><span class="floating-char-name">Sam</span></div>
            <div class="floating-char-card card-f2" onclick="abrirFichaPersonagem('Lia')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994884/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_LIA.png" class="floating-char-img"><span class="floating-char-name">Lia</span></div>
            <div class="floating-char-card card-f2" onclick="abrirFichaPersonagem('Joca')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_JOCA.png" class="floating-char-img"><span class="floating-char-name">Joca</span></div>
            <div class="floating-char-card card-f2" onclick="abrirFichaPersonagem('Leo')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_LEO.png" class="floating-char-img"><span class="floating-char-name">Leo</span></div>
          </div>
        </div>

        <div>
          <h3 class="family-group-title"><span>👵👴 Os Avós</span><button class="btn-audio-mini" onclick="lerTexto('Os queridos Avós.')">🔊</button></h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-avos" onclick="abrirFichaPersonagem('Beto')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_VOVO_BETO.png" class="floating-char-img"><span class="floating-char-name">Vovô Beto</span></div>
            <div class="floating-char-card card-avos" onclick="abrirFichaPersonagem('Hilda')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_VOVO_HILDA.png" class="floating-char-img"><span class="floating-char-name">Vovó Hilda</span></div>
          </div>
        </div>
      </section>

      <!-- SUPORTE INÍCIO -->
      <section class="interactive-card" style="background:#F0F9FF; border:3px solid #BAE6FD; text-align:left; margin-top:24px;">
        <h3 style="color:var(--tea-blue); font-size:20px; font-weight:900; margin-bottom:8px; display:flex; justify-content:space-between; align-items:center;">
          📬 Dúvidas ou Sugestões?
          <button class="btn-audio-mini" onclick="lerTexto('Precisa de ajuda ou quer enviar uma sugestão?')">🔊</button>
        </h3>
        <p style="font-size:14px; font-weight:600; color:#475569; margin-bottom:16px;">Sua mensagem vai direto para nossa equipe (turminhaxexeu@gmail.com).</p>
        <input type="email" id="suporteEmailInicio" class="vip-input" placeholder="Seu e-mail de contato">
        <textarea id="suporteMensagemInicio" class="vip-input" placeholder="Escreva aqui..." style="resize:vertical; min-height:100px;"></textarea>
        <button onclick="enviarSuporteReclamacao('Inicio')" id="btnEnviarSuporteInicio" style="background:var(--tea-blue); color:#FFF; border:none; padding:14px 24px; border-radius:12px; font-size:16px; font-weight:900; cursor:pointer; width:100%; transition:transform 0.2s;">Enviar Mensagem ✉️</button>
      </section>
    </main>

    <!-- PÁGINA 2: VÍDEOS, MÚSICAS & SONS -->
    <main id="pagina-videos" class="page-content content-wrapper">
      <div class="media-section-grid">
        <div class="video-card hover-float">
          <h3 style="font-size:20px; font-weight:900; color:var(--primary-dark); margin-bottom:16px; display:flex; justify-content:space-between; align-items:center;">
            📺 Episódios YouTube
            <button class="btn-audio-mini" onclick="lerTexto('Assista aos episódios no YouTube!')">🔊</button>
          </h3>
          <div class="video-wrapper"><iframe src="https://www.youtube-nocookie.com/embed/videosseries?list=PLh42qmbnReoE_pM4lig3DpJaNGWqoT9uJ" allowfullscreen></iframe></div>
        </div>
        <div class="video-card hover-float" style="border-color:#1DB954;">
          <h3 style="font-size:20px; font-weight:900; color:#1DB954; margin-bottom:16px; display:flex; justify-content:space-between; align-items:center;">
            🎧 Rádio da Turminha
            <button class="btn-audio-mini" style="background:#1DB954;" onclick="lerTexto('Ouça as músicas no Spotify!')">🔊</button>
          </h3>
          <div class="spotify-wrapper"><iframe src="https://open.spotify.com/embed/artist/6ykKQ3uP6Wl2REylKJAdJ6?utm_source=generator&theme=0" width="100%" height="352" frameBorder="0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy"></iframe></div>
        </div>
      </div>

      <div class="interactive-card">
        <h4 style="font-size:22px; font-weight:900; color:var(--tea-blue); margin-bottom:12px; display:flex; justify-content:space-between; align-items:center;">
          🌙 Sons e Acalento (Grátis & VIP)
          <button class="btn-audio-mini" onclick="lerTexto('Sons suaves para relaxar, focar ou dormir.')">🔊</button>
        </h4>
        <div class="media-card-grid">
          <div class="media-item-box" onclick="tocarSomReal('https://actions.google.com/sounds/v1/weather/light_rain.ogg')"><span style="font-size:36px;">🌧️</span><strong style="font-size:15px;">Chuva Suave</strong><span style="font-size:12px; color:#16A34A; font-weight:900;">GRÁTIS</span></div>
          <div class="media-item-box" onclick="tocarSomReal('https://actions.google.com/sounds/v1/animals/birds_arent_real.ogg')"><span style="font-size:36px;">🐦</span><strong style="font-size:15px;">Passarinhos</strong><span style="font-size:12px; color:#16A34A; font-weight:900;">GRÁTIS</span></div>
          <div class="media-item-box locked" onclick="abrirAreaProtegida('vip')"><span class="media-badge-vip">👑 VIP</span><span style="font-size:36px;">🌊</span><strong style="font-size:15px;">Ondas do Mar</strong></div>
          <div class="media-item-box locked" onclick="abrirAreaProtegida('vip')"><span class="media-badge-vip">👑 VIP</span><span style="font-size:36px;">🔥</span><strong style="font-size:15px;">Fogueira</strong></div>
          <div class="media-item-box locked" onclick="abrirAreaProtegida('vip')"><span class="media-badge-vip">👑 VIP</span><span style="font-size:36px;">🍃</span><strong style="font-size:15px;">Vento Suave</strong></div>
        </div>
      </div>
    </main>

    <!-- PÁGINA 3: JOGOS -->
    <main id="pagina-jogos" class="page-content content-wrapper">
      <div class="age-group-section">
        <h3 class="age-title">
          <span>🎮 Central de Jogos</span>
          <button class="btn-audio-mini" onclick="lerTexto('Bem-vindo aos jogos educativos!')">🔊</button>
        </h3>
        <nav class="games-subnav">
          <button id="subtab-lousa" class="subnav-btn active" onclick="mudarSubJogo('lousa')">🎨 Lousa Mágica</button>
          <button id="subtab-contar" class="subnav-btn" onclick="mudarSubJogo('contar')">🔢 Contar</button>
          <button id="subtab-letras" class="subnav-btn" onclick="mudarSubJogo('letras')">🔤 Letras</button>
          <button id="subtab-memoria" class="subnav-btn" onclick="mudarSubJogo('memoria')">🧠 Memória</button>
          <button id="subtab-quiz" class="subnav-btn" onclick="mudarSubJogo('quiz')">❓ Quiz</button>
        </nav>

        <div id="game-lousa" class="game-section-page active-game-page interactive-card">
          <h4 style="font-weight: 900; margin-bottom: 12px; font-size: 20px;">🎨 Lousa Mágica & Colorir</h4>
          <div id="coloringSelectGrid" class="coloring-select-grid"></div>
          
          <div class="brush-size-selector" style="display:flex; gap:10px; justify-content:center; margin-bottom:12px;">
            <button class="action-btn-pill active" style="min-height:38px; font-size:12px;" onclick="definirTamanhoPincel(4, this)">Fino ✏️</button>
            <button class="action-btn-pill" style="min-height:38px; font-size:12px;" onclick="definirTamanhoPincel(8, this)">Médio 🖌️</button>
            <button class="action-btn-pill" style="min-height:38px; font-size:12px;" onclick="definirTamanhoPincel(16, this)">Grosso 🖍️</button>
          </div>
          <canvas id="paintCanvas"></canvas>
          <div class="palette">
            <div class="color-dot" style="background: #3B82F6;" onclick="mudarCor('#3B82F6')"></div>
            <div class="color-dot" style="background: #EF4444;" onclick="mudarCor('#EF4444')"></div>
            <div class="color-dot" style="background: #10B981;" onclick="mudarCor('#10B981')"></div>
            <div class="color-dot" style="background: #F59E0B;" onclick="mudarCor('#F59E0B')"></div>
            <div class="color-dot" style="background: #8B5CF6;" onclick="mudarCor('#8B5CF6')"></div>
            <div class="color-dot" style="background: #000000;" onclick="mudarCor('#000000')"></div>
            <div class="color-dot" style="background: #FFFFFF; border: 2px dashed #CBD5E1; display:flex; justify-content:center; align-items:center;" onclick="mudarCor('#FFFFFF')" title="Borracha">🧽</div>
            <button class="action-btn-pill" style="background:#FEE2E2; border-color:#EF4444; color:#991B1B; min-height:42px;" onclick="limparCanvas()">Limpar 🗑️</button>
            <button class="action-btn-pill" style="background:#D1FAE5; border-color:#10B981; color:#065F46; min-height:42px;" onclick="salvarFotoDesenho()">Salvar 📸</button>
          </div>
        </div>

        <div id="game-contar" class="game-section-page interactive-card">
          <h4 style="font-weight:900; font-size:20px;">🔢 Vamos Contar?</h4>
          <div id="countDisplay" style="display:flex; justify-content:center; align-items:center; gap:16px; margin:24px 0; min-height:80px; flex-wrap:wrap;"></div>
          <div id="countOptions" class="game-btn-grid"></div>
        </div>

        <div id="game-letras" class="game-section-page interactive-card">
          <h4 style="font-weight:900; font-size:20px;">🔤 Qual é a Primeira Letra?</h4>
          <p style="font-size:16px; font-weight:700;">Nome: <strong id="nome-letra-personagem" style="color:var(--purple);">Xexéu</strong></p>
          <img id="img-letra-personagem" src="" style="width:120px; height:120px; object-fit:contain; margin:16px 0;">
          <div id="opcoes-letras" class="game-btn-grid"></div>
        </div>

        <div id="game-memoria" class="game-section-page interactive-card">
          <h4 style="font-weight:900; font-size:20px;">🧠 Jogo da Memória</h4>
          <div id="memoryBoard" class="memory-board" style="display:grid; grid-template-columns:repeat(4,1fr); gap:10px; max-width:360px; margin:16px auto;"></div>
        </div>

        <div id="game-quiz" class="game-section-page interactive-card">
          <h4 style="font-weight:900; font-size:20px;">❓ Quem é este Personagem?</h4>
          <img id="quiz-img" src="" style="width:120px; height:120px; object-fit:contain; margin:16px 0;">
          <div id="quiz-options" class="game-btn-grid"></div>
        </div>
      </div>
    </main>

    <!-- PÁGINA 4: ESPAÇO TEA -->
    <main id="pagina-tea" class="page-content content-wrapper">
      <div class="age-group-section">
        <div class="tea-box hover-float">
          <div style="display:flex; align-items:center; justify-content:space-between; margin-bottom:10px;">
            <div style="display:flex; align-items:center; gap:12px;">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_LEO.png" style="width:60px; height:60px; object-fit:contain;">
              <h3 style="margin:0; font-size:24px;">🧩 Espaço TEA com o Leo</h3>
            </div>
            <button class="btn-audio-mini" onclick="lerTexto('Espaço TEA com o Leo. Vamos fazer tudo com calma?')">🔊</button>
          </div>
          <p style="font-size: 15px; color: #475569; font-weight: 600;">"Oi! Eu sou o Leo. Vamos fazer tudo com calma?"</p>
        </div>

        <div class="interactive-card" style="border-color: #BAE6FD; margin-bottom: 20px;">
          <h4 style="color: var(--tea-blue); font-weight: 900; font-size: 18px; margin-bottom: 12px;">🗣️ Cartões de Fala (CAA)</h4>
          <div class="caa-grid" style="display:grid; grid-template-columns:repeat(auto-fit, minmax(130px,1fr)); gap:12px;">
            <div class="caa-btn hover-float" style="background:#FFF; border:2px solid #BAE6FD; border-radius:14px; padding:16px 8px; text-align:center; cursor:pointer;" onclick="lerTexto('Eu quero água, por favor.')"><span style="font-size:34px;">💧</span><p style="font-weight:800; color:var(--tea-blue); margin-top:6px;">Água</p></div>
            <div class="caa-btn hover-float" style="background:#FFF; border:2px solid #BAE6FD; border-radius:14px; padding:16px 8px; text-align:center; cursor:pointer;" onclick="lerTexto('Estou com fome.')"><span style="font-size:34px;">🍎</span><p style="font-weight:800; color:var(--tea-blue); margin-top:6px;">Comer</p></div>
            <div class="caa-btn hover-float" style="background:#FFF; border:2px solid #BAE6FD; border-radius:14px; padding:16px 8px; text-align:center; cursor:pointer;" onclick="lerTexto('Preciso ir ao banheiro.')"><span style="font-size:34px;">🚽</span><p style="font-weight:800; color:var(--tea-blue); margin-top:6px;">Banheiro</p></div>
            <div class="caa-btn hover-float" style="background:#FFF; border:2px solid #BAE6FD; border-radius:14px; padding:16px 8px; text-align:center; cursor:pointer;" onclick="lerTexto('Quero brincar.')"><span style="font-size:34px;">🧸</span><p style="font-weight:800; color:var(--tea-blue); margin-top:6px;">Brincar</p></div>
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
        <div class="book-card-grid" style="display:grid; grid-template-columns:repeat(auto-fit, minmax(200px,1fr)); gap:20px; margin-top:16px;">
          <div class="interactive-card" style="border: 3px dashed #CBD5E1;"><span style="font-size:50px;">🚧</span><strong style="font-size:18px; display:block; margin:10px 0;">Em Breve</strong></div>
        </div>
      </div>
    </main>

    <!-- PÁGINA 6: ROTINA -->
    <main id="pagina-rotina" class="page-content content-wrapper">
      <div class="age-group-section">
        <h3 class="age-title">
          <span>📅 Rotina & Cuidados</span>
          <button class="btn-audio-mini" onclick="lerTexto('Crie a sua rotina diária.')">🔊</button>
        </h3>
        <div class="interactive-card" style="text-align:left; margin-bottom:24px;">
          <h4 style="font-size:18px; font-weight:900; margin-bottom:12px;">Adicionar Tarefa na Rotina:</h4>
          <p style="font-size:13px; color:#64748B; margin-bottom:12px;">Grátis: Até 3 tarefas | VIP: Ilimitado!</p>
          <div class="rotina-add-box" style="display:flex; gap:8px; margin-bottom:20px; flex-wrap:wrap;">
            <input type="text" id="rotina-nova-texto" class="vip-input" style="flex:1; margin-bottom:0;" placeholder="Ex: Hora do banho 🛁">
            <button class="action-btn-pill" style="background:var(--primary); color:#FFF;" onclick="adicionarRotinaPersonalizada()">Adicionar ➕</button>
          </div>
          <div id="lista-rotinas-dinamica"></div>
        </div>
      </div>
    </main>

    <!-- PÁGINA 7: CONQUISTAS -->
    <main id="pagina-conquistas" class="page-content content-wrapper">
      <div class="age-group-section">
        <h3 class="age-title">
          <span>🏆 Minhas Conquistas</span>
          <button class="btn-audio-mini" onclick="lerTexto('Minhas conquistas e certificado de Super Fã!')">🔊</button>
        </h3>
        <div class="conquistas-box" style="background: linear-gradient(135deg, #FEF3C7 0%, #FFFBEB 100%); border: 2px solid #FCD34D; border-radius: 12px; padding: 14px 20px; margin-bottom: 16px; display: flex; justify-content: space-between; font-weight: 800; color: #92400E;">
          <span>⭐ Pontos: <strong id="placar-pontos">0</strong></span>
          <span id="medalha-status">Iniciante</span>
        </div>

        <div class="interactive-card hover-float" style="border: 3px double #F59E0B; background: #FFFBEB;">
          <h4 style="color:#92400E; font-size:22px; font-weight:900; margin-bottom:12px;">🎓 Certificado de Super Fã</h4>
          <input type="text" id="nome-certificado-input" placeholder="Digite o nome da criança" class="vip-input" style="border-color:#FCD34D; max-width:360px; margin:0 auto 12px; display:block;">
          <button onclick="gerarCertificadoGeral()" class="action-btn-pill" style="background:#D97706; color:#FFF; border:none; margin:0 auto;">Gerar Certificado ⭐</button>
          <div id="boxCertificadoResultado" style="display:none; margin-top:24px; padding:20px; background:#FFF; border-radius:12px; border:2px solid #FCD34D;">
            <h3 style="color:#1D4ED8; font-size:28px; text-transform:uppercase;" id="txtNomeCertificado"></h3>
            <p style="font-weight:800; color:#B45309; font-size:16px;">É oficialmente Super Fã da Turminha do Xexéu! 🌟</p>
          </div>
        </div>
      </div>
    </main>

    <!-- PÁGINA 8: ÁREA VIP (COM A LISTA COMPLETA DOS 10 BENEFÍCIOS) -->
    <main id="pagina-vip" class="page-content content-wrapper">
      <div class="age-group-section">
        <div class="vip-lock-container" style="background: linear-gradient(135deg, #FFFBEB 0%, #FEF3C7 100%); border: 3px solid #FCD34D; border-radius: var(--radius-lg); padding: 28px; text-align: center;">
          <h3 style="font-size:26px; color:#92400E; font-weight:900; display:flex; justify-content:center; align-items:center; gap:10px;">
            ⭐ Clube VIP da Turminha
            <button class="btn-audio-mini" onclick="lerTexto('Assine o Clube VIP e desbloqueie todas as ferramentas exclusivas!')">🔊</button>
          </h3>
          <div class="vip-price-tag" style="display:inline-block; background:#F59E0B; color:#FFF; font-weight:900; font-size:16px; padding:10px 24px; border-radius:30px; margin:14px 0;">Apenas R$ 6,00 / mês</div>
          
          <!-- LISTA COMPLETA DOS 10 BENEFÍCIOS QUE VOCÊ PEDIU -->
          <div style="background:#FFF; padding:24px; border-radius:16px; border:2px dashed #F59E0B; text-align:left; font-size:15px; margin:20px auto; color:#78350F; max-width: 850px;">
            <strong style="display:block; font-size:19px; margin-bottom:14px;">💖 O que o Clube VIP desbloqueia para os Pais e para as Crianças?</strong>
            <ul style="margin-left:22px; line-height:1.9; font-weight:600; display:flex; flex-direction:column; gap:6px;">
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

          <div class="vip-grid-forms" style="display:grid; grid-template-columns:repeat(auto-fit, minmax(280px,1fr)); gap:20px; max-width:850px; margin:20px auto 0;">
            <div class="vip-form-box" style="background:#FFF; padding:20px; border-radius:14px; border:2px solid #FCD34D; text-align:left;">
              <h4 style="font-size:18px; color:#92400E; margin-bottom:10px; font-weight:900;">✨ Desbloquear Acesso VIP</h4>
              <input type="email" id="cad-email" class="vip-input" placeholder="Seu E-mail">
              <input type="password" id="cad-senha" class="vip-input" placeholder="Crie uma Senha">
              <a href="javascript:void(0)" class="btn-vip-checkout" id="btnCheckoutVip" onclick="salvarECadastrar()" style="background:linear-gradient(135deg, #F59E0B, #D97706); color:#FFF; font-weight:800; padding:14px; border-radius:12px; text-decoration:none; display:block; text-align:center;">Quero Ser VIP por R$ 6,00 💳</a>
            </div>

            <div class="vip-form-box" style="background:#FFF; padding:20px; border-radius:14px; border:2px solid #CBD5E1; text-align:left;">
              <h4 style="font-size:18px; color:#1E293B; margin-bottom:10px; font-weight:900;">🔑 Já sou Assinante</h4>
              <input type="email" id="log-email" class="vip-input" placeholder="E-mail Cadastrado">
              <input type="password" id="log-senha" class="vip-input" placeholder="Sua Senha">
              <button onclick="fazerLogin()" id="btnLoginVip" class="action-btn-pill" style="width:100%; justify-content:center; background:#3B82F6; color:#FFF; border:none; min-height:48px;">Entrar no Clube VIP</button>
            </div>
          </div>
        </div>

        <!-- SUPORTE VIP -->
        <div class="interactive-card" style="background:#F0F9FF; border:3px solid #BAE6FD; text-align:left; margin-top:24px;">
          <h3 style="color:var(--tea-blue); font-size:20px; font-weight:900; margin-bottom:8px;">📬 Precisa de Ajuda ou quer enviar uma Sugestão?</h3>
          <p style="font-size:14px; font-weight:600; color:#475569; margin-bottom:16px;">Escreva para nós! Sua mensagem será enviada diretamente para <strong>turminhaxexeu@gmail.com</strong>.</p>
          <input type="email" id="suporteEmailVip" class="vip-input" placeholder="Seu e-mail de contato">
          <textarea id="suporteMensagemVip" class="vip-input" placeholder="Escreva aqui..." style="resize:vertical; min-height:100px;"></textarea>
          <button onclick="enviarSuporteReclamacao('Vip')" id="btnEnviarSuporteVip" style="background:var(--tea-blue); color:#FFF; border:none; padding:14px 24px; border-radius:12px; font-size:16px; font-weight:900; cursor:pointer; width:100%;">Enviar Mensagem ✉️</button>
        </div>
      </div>
    </main>

    <!-- CONFIG & PERFIL -->
    <main id="pagina-config" class="page-content content-wrapper">
      <div class="age-group-section">
        <h3 class="age-title">⚙️ Configurações do Portal</h3>
        <div class="interactive-card" style="text-align:left;">
          <p style="font-size:15px; font-weight:700;">Ajustes rápidos para os pais:</p>
          <button class="action-btn-pill" style="margin-top:10px;" onclick="abrirAreaProtegida('vip')">🔒 Alterar Senha Parental (Acessar VIP)</button>
        </div>
      </div>
    </main>

    <main id="pagina-perfil" class="page-content content-wrapper">
      <div class="age-group-section">
        <h3 class="age-title">👤 Perfil da Criança</h3>
        <div class="interactive-card">
          <p style="font-size:16px; font-weight:800; margin-bottom:16px;">Qual seu amiguinho favorito?</p>
          <div id="avatarEscolhaGrid" class="avatar-escolha-grid" style="display:flex; justify-content:center; gap:12px; flex-wrap:wrap;"></div>
        </div>
      </div>
    </main>

    <footer class="content-wrapper">
      <span>© Turminha do Xexéu — eve Design — Todos os direitos reservados.</span>
      <span><a onclick="abrirPrivacidade()">Política de Privacidade</a> | <a onclick="document.getElementById('cookieBanner').classList.remove('hidden')">Configurar Cookies</a></span>
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
      }
    }

    function salvarConfiguracaoInicial() {
      const nome = document.getElementById('onb-nome').value.trim();
      const senha = document.getElementById('onb-senha').value.trim();
      if(!nome || !senha) { alert("Preencha todos os campos!"); return; }
      localStorage.setItem('turminha_nome_crianca', nome);
      localStorage.setItem('turminha_senha_parental', senha);
      localStorage.setItem('turminha_configurado', 'true');
      document.getElementById('modalOnboarding').classList.remove('active');
      lerTexto(`Tudo pronto! Divirta-se na Turminha, ${nome}!`);
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
      const p = PERSONAGENS.find(x => x.nome === nome);
      if (!p) return;
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

    /* SUPORTE E VIP VIA PLANILHA */
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
      
      fetch(`${URL_SCRIPT}?email=${encodeURIComponent(email)}&senha=${encodeURIComponent(senha)}`)
        .then(res => res.json())
        .then(data => {
          if(data.liberado) { isUserVip = true; localStorage.setItem('turminha_vip_status', 'ativo'); alert("Acesso VIP Confirmado!"); window.location.reload(); } 
          else { alert("Senha incorreta ou assinatura pendente."); }
        }).catch(() => alert("Erro ao verificar conexão."));
    }

    /* ROTINAS */
    function renderizarRotinas() {
      const container = document.getElementById('lista-rotinas-dinamica'); if (!container) return; container.innerHTML = '';
      rotinasSalvas.forEach((r, idx) => {
        const div = document.createElement('div'); div.className = `rotina-item ${r.feito ? 'concluido' : ''}`;
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

    /* PARENTAL GATE CORRIGIDO (SEM LOOP DE RECARREGAMENTO) */
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
        fecharParentalGate(); 
        mudarPagina(destinoAposGate); 
        lerTexto("Acesso liberado.");
      } else {
        alert("Senha incorreta!"); lerTexto("Senha incorreta.");
      }
    }

    function mudarPagina(p) {
      const abas = ['inicio', 'videos', 'jogos', 'tea', 'livros', 'rotina', 'conquistas', 'vip', 'config', 'perfil'];
      abas.forEach(id => {
        const el = document.getElementById('pagina-' + id); const tab = document.getElementById('btn-tab-' + id);
        if (el) el.classList.remove('active-page'); if (tab) tab.classList.remove('active');
      });
      const target = document.getElementById('pagina-' + p); const targetTab = document.getElementById('btn-tab-' + p);
      if (target) target.classList.add('active-page'); if (targetTab) targetTab.classList.add('active');
      
      if (p === 'jogos') { renderizarLousaBtns(); setTimeout(redimensionarCanvas, 50); }
      if (p === 'perfil') criarSeletorAvatar();
      if (p === 'rotina') renderizarRotinas();
      window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    function mudarSubJogo(sub) {
      ['lousa', 'contar', 'letras', 'memoria', 'quiz'].forEach(s => {
        const el = document.getElementById('game-' + s); const tab = document.getElementById('subtab-' + s);
        if (el) el.classList.remove('active-game-page'); if (tab) tab.classList.remove('active');
      });
      const target = document.getElementById('game-' + sub); const tabTarget = document.getElementById('subtab-' + sub);
      if (target) target.classList.add('active-game-page'); if (tabTarget) tabTarget.classList.add('active');
      if (sub === 'lousa') setTimeout(redimensionarCanvas, 50);
    }

    /* LOUSA */
    const canvas = document.getElementById('paintCanvas'); const ctx = canvas ? canvas.getContext('2d') : null;
    let desenhando = false, corAtual = '#3B82F6', tamanhoPincel = 4, imgContornoAtual = null;

    function renderizarLousaBtns() {
      const grid = document.getElementById('coloringSelectGrid'); if (!grid) return; grid.innerHTML = '';
      const btnLivre = document.createElement('button'); btnLivre.className = 'btn-color-draw selected'; btnLivre.innerHTML = '✏️ Desenho Livre';
      btnLivre.onclick = () => { imgContornoAtual = null; limparCanvas(); document.querySelectorAll('.btn-color-draw').forEach(b => b.classList.remove('selected')); btnLivre.classList.add('selected'); };
      grid.appendChild(btnLivre);

      const limit = isUserVip ? PERSONAGENS.length : 3;
      for(let i = 0; i < limit; i++) {
        const item = PERSONAGENS[i]; const btn = document.createElement('button'); btn.className = 'btn-color-draw'; btn.innerHTML = `<img src="${item.img}"> ${item.nome}`;
        btn.onclick = () => carregarContornoPintar(item.lousa, btn); grid.appendChild(btn);
      }
      if(!isUserVip) {
        const btnVip = document.createElement('button'); btnVip.className = 'btn-color-draw'; btnVip.style.cssText = "border-color:#F59E0B; background:#FFFBEB; color:#92400E;";
        btnVip.innerHTML = '🔒 +9 Desenhos (VIP)'; btnVip.onclick = () => abrirAreaProtegida('vip'); grid.appendChild(btnVip);
      }
    }

    function redimensionarCanvas() {
      if (!canvas || !canvas.parentElement) return;
      canvas.width = canvas.parentElement.clientWidth - 24; canvas.height = window.innerWidth > 1024 ? 450 : 280;
      if (imgContornoAtual) desenharContorno(imgContornoAtual);
    }
    function definirTamanhoPincel(tam, btn) { tamanhoPincel = tam; document.querySelectorAll('.brush-size-selector .action-btn-pill').forEach(b => b.classList.remove('active')); if(btn) btn.classList.add('active'); }
    function mudarCor(c) { corAtual = c; }
    function limparCanvas() { if (ctx) ctx.clearRect(0, 0, canvas.width, canvas.height); if (imgContornoAtual) desenharContorno(imgContornoAtual); }
    function carregarContornoPintar(url, btn) {
      document.querySelectorAll('.btn-color-draw').forEach(b => b.classList.remove('selected')); if (btn) btn.classList.add('selected');
      limparCanvas(); const img = new Image(); img.crossOrigin = "Anonymous"; img.src = url;
      img.onload = () => { imgContornoAtual = img; desenharContorno(img); };
    }
    function desenharContorno(img) {
      const ratio = Math.min(canvas.width / img.width, canvas.height / img.height) * 0.85;
      const w = img.width * ratio; const h = img.height * ratio; const x = (canvas.width - w) / 2; const y = (canvas.height - h) / 2;
      ctx.globalAlpha = 0.35; ctx.drawImage(img, x, y, w, h); ctx.globalAlpha = 1.0;
    }
    function salvarFotoDesenho() { const link = document.createElement('a'); link.download = 'desenho.png'; link.href = canvas.toDataURL(); link.click(); lerTexto("Salvo!"); }

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
      for (let i = 0; i < qContar; i++) { const img = document.createElement('img'); img.src = char.img; img.style.cssText = 'width:55px; height:55px; object-fit:contain;'; display.appendChild(img); }
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
        card.style.cssText = "aspect-ratio:1; background:var(--primary); border-radius:12px; display:flex; align-items:center; justify-content:center; color:#FFF; font-size:20px; cursor:pointer;";
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
        img.style.cssText = `width:56px; height:56px; border-radius:50%; border:3px solid ${p.img === avatarAtual ? '#F59E0B' : '#CBD5E1'}; cursor:pointer; background:#FFF; padding:4px; transition:transform 0.2s;`;
        img.onclick = () => { document.querySelectorAll('#avatarEscolhaGrid img').forEach(b => b.style.borderColor = '#CBD5E1'); img.style.borderColor = '#F59E0B'; localStorage.setItem('turminha_avatar', p.img); lerTexto(`${p.nome} escolhido!`); };
        grid.appendChild(img);
      });
    }

    function gerarCertificadoGeral() {
      const nome = document.getElementById('nome-certificado-input').value.trim();
      if (!nome) { alert("Digite o nome da criança!"); return; }
      document.getElementById('txtNomeCertificado').innerText = nome;
      document.getElementById('boxCertificadoResultado').style.display = 'block';
      lerTexto(`Parabéns, ${nome}! Certificado Gerado.`);
    }

    window.onload = () => {
      verificarOnboarding();
      adicionarPontos(0); 
      carregarJogoContar(); carregarJogoLetra(); iniciarMemoria(); carregarQuiz(); 
      renderizarRotinas(); renderizarLousaBtns();
      window.addEventListener('resize', redimensionarCanvas); setTimeout(redimensionarCanvas, 200);
    };
  </script>
</body>
</html>
