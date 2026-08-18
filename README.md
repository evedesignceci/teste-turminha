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
      --radius-xl: 28px;
      --radius-lg: 20px;
      --radius-md: 14px;
      --shadow-sm: 0 4px 12px rgba(15, 23, 42, 0.05);
      --shadow-md: 0 8px 24px rgba(15, 23, 42, 0.08);
      --shadow-lg: 0 14px 32px rgba(59, 130, 246, 0.16);
    }

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
    body.sensory-mode .interactive-card, body.sensory-mode .tea-box, body.sensory-mode .video-card { background: #FFFFFF !important; border: 2px solid #CBD5E1 !important; }
    body.sensory-mode .floating-vip-badge, body.sensory-mode .cookie-banner { display: none !important; }

    * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Poppins', system-ui, sans-serif; -webkit-tap-highlight-color: transparent; }

    body {
      background: var(--bg-gradient);
      color: var(--text-main);
      min-height: 100vh;
      transition: background 0.3s ease;
      overflow-x: hidden;
    }

    @keyframes float { 0% { transform: translateY(0px); } 50% { transform: translateY(-8px); } 100% { transform: translateY(0px); } }
    @keyframes pulse { 0% { transform: scale(1); } 50% { transform: scale(1.05); } 100% { transform: scale(1); } }
    @keyframes slideUp { from { transform: translateY(100%); } to { transform: translateY(0); } }
    @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }

    .float-anim { animation: float 4s ease-in-out infinite; }
    .pulse-anim { animation: pulse 2.5s infinite; }
    .hover-float { transition: transform 0.3s ease; }
    .hover-float:hover { transform: translateY(-6px); }

    .app-container { width: 100%; min-height: 100vh; display: flex; flex-direction: column; gap: 20px; padding-bottom: 40px; }
    .content-wrapper { width: 100%; max-width: 1300px; margin-left: auto; margin-right: auto; }
    @media (max-width: 1340px) { .content-wrapper { width: calc(100% - 24px); } }

    /* CABEÇALHO */
    header {
      background: linear-gradient(135deg, #BAE6FD 0%, #E0F2FE 100%);
      display: flex; align-items: center; justify-content: space-between;
      border-radius: var(--radius-lg); padding: 16px 24px; margin-top: 16px;
      box-shadow: var(--shadow-sm); gap: 12px; flex-wrap: wrap;
    }
    .logo-img { max-width: 160px; height: auto; object-fit: contain; }
    
    .header-actions { display: flex; align-items: center; gap: 10px; flex-wrap: wrap; }
    .action-btn-pill {
      background: #FFFFFF; border: 2px solid var(--primary); color: var(--primary-dark);
      font-weight: 800; font-size: 14px; padding: 10px 18px; border-radius: 50px;
      cursor: pointer; display: flex; align-items: center; gap: 6px; min-height: 48px;
      box-shadow: var(--shadow-sm); transition: all 0.2s ease;
    }
    .action-btn-pill:hover { background: #E0F2FE; transform: scale(1.03); }
    .action-btn-pill.muted { background: #FEE2E2; border-color: #EF4444; color: #991B1B; }

    /* NAVEGAÇÃO OTIMIZADA E ESPAÇADA */
    .page-nav {
      display: flex; gap: 14px; background: #F0F9FF; padding: 12px;
      border-radius: var(--radius-lg); border: 2px solid #BAE6FD;
      overflow-x: auto; scrollbar-width: thin; flex-wrap: nowrap;
    }
    @media (min-width: 1024px) {
      .page-nav { flex-wrap: wrap; justify-content: center; }
    }
    .nav-tab-btn {
      flex: 0 0 auto; padding: 12px 24px; border: none; border-radius: var(--radius-md);
      font-weight: 800; font-size: 14px; cursor: pointer; background: transparent;
      color: var(--text-muted); display: flex; align-items: center; justify-content: center;
      gap: 6px; min-height: 54px; white-space: nowrap; transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }
    @media (min-width: 1024px) { .nav-tab-btn { flex: 1 1 auto; } }
    .nav-tab-btn:hover { background: #E0F2FE; color: var(--primary); transform: translateY(-2px); }
    .nav-tab-btn.active { background: var(--primary); color: #FFFFFF; box-shadow: 0 6px 16px rgba(59, 130, 246, 0.4); transform: translateY(-4px); }
    .nav-tab-btn.tea-tab { background: #E0F2FE; color: var(--tea-blue); border: 2px solid #7DD3FC; }
    .nav-tab-btn.tea-tab.active { background: var(--tea-blue); color: #FFF; border-color: transparent; }
    .nav-tab-btn.vip-tab { background: #FEF3C7; color: #92400E; border: 2px solid #FCD34D; }
    .nav-tab-btn.vip-tab.active { background: linear-gradient(135deg, #F59E0B, #D97706); color: #FFF; border-color: transparent; }

    .page-content { display: none; flex-direction: column; gap: 24px; animation: fadeIn 0.3s ease; }
    .page-content.active-page { display: flex; }

    /* SEÇÃO 1: INÍCIO E FAMÍLIAS */
    .banner-intro-grid { display: grid; grid-template-columns: 1fr; gap: 20px; }
    @media (min-width: 900px) { .banner-intro-grid { grid-template-columns: 1fr 1.2fr; align-items: stretch; } }
    
    .banner-container { width: 100%; border-radius: var(--radius-lg); overflow: hidden; box-shadow: var(--shadow-sm); }
    .banner-img { width: 100%; height: 100%; min-height: 240px; display: block; object-fit: cover; transition: transform 0.5s; }
    .banner-img:hover { transform: scale(1.02); }

    .intro-box {
      background: linear-gradient(135deg, #FEF3C7 0%, #FFFBEB 100%);
      border: 3px solid #FCD34D; border-radius: var(--radius-lg); padding: 24px;
      display: flex; flex-direction: column; justify-content: center; gap: 12px;
    }
    .intro-box h2 { font-size: 20px; font-weight: 900; color: #92400E; display: flex; justify-content: space-between; align-items: center; }
    .intro-box p { font-size: 14.5px; color: #78350F; line-height: 1.6; font-weight: 600; }

    .btn-audio-mini {
      background: linear-gradient(135deg, #FBBF24, #F59E0B); border: none; border-radius: 50%;
      width: 44px; height: 44px; min-width: 44px; cursor: pointer; font-size: 18px;
      display: flex; align-items: center; justify-content: center; color: #FFF;
      box-shadow: 0 4px 10px rgba(245, 158, 11, 0.4); transition: transform 0.2s;
    }
    .btn-audio-mini:hover { transform: scale(1.1) rotate(5deg); }

    /* REDES SOCIAIS */
    .social-round-section { display: flex; justify-content: center; align-items: center; gap: 14px; flex-wrap: wrap; background: #FFF; padding: 16px; border-radius: var(--radius-lg); box-shadow: var(--shadow-sm); border: 2px solid #E2E8F0; }
    .social-round-btn {
      width: 54px; height: 54px; border-radius: 50%; background: #F8FAFC; border: 2.5px solid #CBD5E1;
      display: flex; align-items: center; justify-content: center; text-decoration: none;
      box-shadow: var(--shadow-sm); transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }
    .social-round-btn:hover { transform: translateY(-5px) scale(1.1); border-color: var(--primary); background: #FFF; box-shadow: 0 8px 16px rgba(59, 130, 246, 0.2); }
    .social-round-btn img { width: 30px; height: 30px; object-fit: contain; }

    /* PERSONAGENS */
    .section-family-container { display: flex; flex-direction: column; gap: 32px; }
    .family-group-title { font-size: 20px; font-weight: 900; color: var(--primary-dark); margin-bottom: 12px; display: flex; align-items: center; justify-content: space-between; background: #FFF; padding: 14px 20px; border-radius: var(--radius-lg); box-shadow: var(--shadow-sm); border-left: 6px solid var(--primary); }
    
    .floating-cards-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); gap: 16px; }
    @media (min-width: 768px) { .floating-cards-grid { grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 20px; } }
    
    .floating-char-card {
      background: #FFFFFF; border-radius: var(--radius-lg); padding: 16px 12px;
      text-align: center; border: 3px solid #E2E8F0; box-shadow: var(--shadow-sm);
      display: flex; flex-direction: column; align-items: center; gap: 8px; cursor: pointer;
      transition: all 0.3s ease; position: relative; overflow: hidden;
    }
    .floating-char-card:hover { transform: translateY(-6px); box-shadow: var(--shadow-md); border-color: var(--primary); }
    .floating-char-img { width: 90px; height: 90px; object-fit: contain; border-radius: 50%; background: #F0F9FF; padding: 6px; transition: transform 0.3s; }
    .floating-char-card:hover .floating-char-img { transform: scale(1.1) rotate(3deg); }
    
    .floating-char-name { font-size: 16px; font-weight: 900; color: var(--text-main); }
    .floating-char-tag { font-size: 11px; font-weight: 800; padding: 4px 10px; border-radius: 20px; text-transform: uppercase; }
    .floating-char-desc { font-size: 12px; font-weight: 600; color: var(--text-muted); line-height: 1.4; display: -webkit-box; -webkit-line-clamp: 3; -webkit-box-orient: vertical; overflow: hidden; }

    .card-f1 { border-color: #F472B6; } .card-f1 .floating-char-tag { background: #FCE7F3; color: #DB2777; }
    .card-f2 { border-color: #60A5FA; } .card-f2 .floating-char-tag { background: #DBEAFE; color: #2563EB; }
    .card-avos { border-color: #FBBF24; } .card-avos .floating-char-tag { background: #FEF3C7; color: #D97706; }
    .card-especial { border-color: #A78BFA; } .card-especial .floating-char-tag { background: #EDE9FE; color: #7C3AED; }

    /* SEÇÃO DE SUPORTE (INÍCIO E VIP) */
    .support-form-box { background: #F0F9FF; border: 3px solid #BAE6FD; border-radius: var(--radius-lg); padding: 24px; text-align: left; }
    .support-form-box h3 { color: var(--tea-blue); font-size: 20px; font-weight: 900; margin-bottom: 8px; }
    .support-form-box p { font-size: 14px; font-weight: 600; color: #475569; margin-bottom: 16px; }
    .support-input { width: 100%; padding: 14px; font-size: 14px; font-family: 'Poppins'; border: 2px solid #7DD3FC; border-radius: 12px; margin-bottom: 12px; outline: none; }
    .support-input:focus { border-color: var(--primary); }

    /* VÍDEOS, MÚSICAS & ACALENTO */
    .media-section-grid { display: grid; grid-template-columns: 1fr; gap: 24px; }
    @media (min-width: 900px) { .media-section-grid { grid-template-columns: 1fr 1fr; } }
    .video-card { background: #FFFFFF; border-radius: var(--radius-lg); padding: 20px; box-shadow: var(--shadow-sm); border: 2px solid #E2E8F0; text-align: center; }
    .video-wrapper { position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; border-radius: var(--radius-md); }
    .video-wrapper iframe { position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0; }
    .spotify-wrapper { width: 100%; height: 352px; border-radius: 14px; overflow: hidden; border: 2px solid #1DB954; box-shadow: var(--shadow-sm); }
    .interactive-card { background: #F8FAFC; border-radius: var(--radius-md); padding: 20px; text-align: center; border: 2px solid #E2E8F0; width: 100%; }
    
    .media-card-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr)); gap: 16px; margin-top: 14px; }
    .media-item-box { background: #FFF; border: 2px solid #CBD5E1; border-radius: var(--radius-md); padding: 16px 12px; display: flex; flex-direction: column; align-items: center; gap: 8px; cursor: pointer; position: relative; transition: all 0.2s; }
    .media-item-box:hover { transform: translateY(-4px); border-color: var(--primary); box-shadow: 0 6px 12px rgba(59,130,246,0.15); }
    .media-item-box.locked { background: #FFFBEB; border-color: #FCD34D; }
    .media-badge-vip { position: absolute; top: 8px; right: 8px; background: #F59E0B; color: #FFF; font-size: 10px; font-weight: 800; padding: 4px 8px; border-radius: 8px; }

    /* JOGOS E LOUSA */
    .age-group-section { background: #FFFFFF; border-radius: var(--radius-lg); padding: 24px; border: 2px solid #E2E8F0; box-shadow: var(--shadow-sm); }
    .age-title { font-size: 22px; font-weight: 900; color: var(--primary-dark); margin-bottom: 16px; display: flex; align-items: center; justify-content: space-between; }
    
    .games-subnav { display: flex; gap: 10px; background: #E0F2FE; padding: 10px; border-radius: var(--radius-md); margin-bottom: 20px; overflow-x: auto; scrollbar-width: none; }
    @media (min-width: 1024px) { .games-subnav { justify-content: center; } }
    .subnav-btn { padding: 12px 18px; border: none; border-radius: 12px; font-weight: 800; font-size: 14px; cursor: pointer; background: #FFF; color: var(--primary-dark); transition: all 0.2s; white-space: nowrap; }
    .subnav-btn:hover { background: #BAE6FD; transform: translateY(-2px); }
    .subnav-btn.active { background: var(--primary); color: #FFF; box-shadow: 0 4px 10px rgba(59,130,246,0.3); }

    .game-section-page { display: none; } 
    .game-section-page.active-game-page { display: block; animation: fadeIn 0.3s; }

    /* LOUSA MÁGICA */
    #paintCanvas { background: #FFF; border: 4px solid var(--primary); border-radius: var(--radius-lg); width: 100%; height: 350px; touch-action: none; cursor: crosshair; }
    @media (min-width: 1024px) { #paintCanvas { height: 480px; } }

    .palette { display: flex; gap: 12px; justify-content: center; align-items: center; margin-top: 16px; flex-wrap: wrap; }
    .color-dot { width: 44px; height: 44px; border-radius: 50%; border: 3px solid #FFF; box-shadow: 0 4px 10px rgba(0,0,0,0.15); cursor: pointer; transition: transform 0.2s; display:flex; justify-content:center; align-items:center; }
    .color-dot:hover { transform: scale(1.15); }

    .coloring-select-grid { display: flex; justify-content: center; gap: 10px; margin-bottom: 16px; flex-wrap: wrap; max-height: 200px; overflow-y: auto; padding-bottom: 8px; }
    .btn-color-draw { background: #FFF; border: 2px solid #CBD5E1; padding: 10px 14px; border-radius: 12px; font-weight: 800; font-size: 13px; cursor: pointer; display: flex; align-items: center; gap: 6px; transition: all 0.2s; }
    .btn-color-draw.selected { border-color: var(--primary); background: #E0F2FE; transform: scale(1.05); box-shadow: 0 4px 10px rgba(59,130,246,0.2); }
    .btn-color-draw img { width: 26px; height: 26px; object-fit: contain; }

    .game-btn-grid { display: flex; justify-content: center; gap: 12px; flex-wrap: wrap; margin-top: 16px; }
    .btn-choice { background: var(--purple); color: #FFF; border: none; padding: 16px 24px; font-weight: 900; font-size: 18px; border-radius: 14px; cursor: pointer; min-width: 64px; box-shadow: 0 4px 14px rgba(139, 92, 246, 0.3); transition: transform 0.15s ease; }
    .btn-choice:active { transform: scale(0.92); }
    .btn-choice.acertou { background: #10B981 !important; transform: scale(1.1); box-shadow: 0 0 20px rgba(16, 185, 129, 0.6); }
    .btn-choice.errou { background: #EF4444 !important; transform: scale(0.95) rotate(-3deg); }

    .memory-board { display: grid; grid-template-columns: repeat(4, 1fr); gap: 12px; margin-top: 14px; max-width: 480px; margin-left: auto; margin-right: auto; }
    .memory-card { aspect-ratio: 1; background: var(--primary); border-radius: 14px; display: flex; align-items: center; justify-content: center; color: #FFF; font-weight: 900; font-size: 28px; cursor: pointer; transition: transform 0.2s; }
    .memory-card:active { transform: scale(0.95); }
    .memory-card.flipped { background: #FFF; border: 3px solid var(--primary); }
    .memory-card img { width: 85%; height: 85%; object-fit: contain; }

    /* ESPAÇO TEA */
    .emotion-card-grid { display: flex; gap: 12px; justify-content: center; flex-wrap: wrap; margin-top: 12px; }
    .emotion-card { background: #FFF; border: 2px solid #E2E8F0; border-radius: 16px; padding: 14px 12px; cursor: pointer; width: 110px; display: flex; flex-direction: column; align-items: center; transition: all 0.2s; }
    .emotion-card:hover { transform: translateY(-6px) scale(1.05); border-color: var(--tea-blue); box-shadow: 0 6px 16px rgba(2,132,199,0.15); }
    .emotion-card span { font-size: 40px; margin-bottom: 6px; }
    
    .caa-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(130px, 1fr)); gap: 12px; margin-top: 14px; }
    .caa-btn { background: #FFF; border: 2px solid #BAE6FD; border-radius: 14px; padding: 16px 8px; text-align: center; cursor: pointer; display: flex; flex-direction: column; align-items: center; transition: all 0.2s; }
    .caa-btn:hover { background: #F0F9FF; transform: translateY(-4px); border-color: var(--tea-blue); box-shadow: 0 6px 12px rgba(2,132,199,0.1); }
    .caa-btn span { font-size: 34px; }

    /* ROTINA */
    .rotina-item { display: flex; justify-content: space-between; align-items: center; background: #FFF; border: 2px solid #E2E8F0; padding: 12px 16px; border-radius: 12px; margin-bottom: 10px; font-size: 14px; font-weight: 700; transition: all 0.3s; }
    .rotina-item:hover { border-color: #CBD5E1; transform: translateX(4px); }
    .rotina-item.concluido { background: #DCFCE7; border-color: #86EFAC; opacity: 0.85; }
    .rotina-item.concluido .rotina-texto { text-decoration: line-through; color: #166534; }
    .rotina-add-box { display: flex; gap: 8px; margin-bottom: 20px; flex-wrap: wrap; }
    .rotina-add-box input { flex: 1; min-width: 200px; padding: 12px; border-radius: 10px; border: 2px solid #CBD5E1; font-family: 'Poppins'; font-weight: 600; outline: none; }
    .rotina-add-box input:focus { border-color: var(--primary); }
    .rotina-add-box button { background: var(--primary); color: #FFF; border: none; padding: 12px 20px; border-radius: 10px; font-weight: 800; cursor: pointer; transition: transform 0.2s; }
    .rotina-add-box button:hover { transform: scale(1.05); }

    /* ÁREA VIP */
    .vip-lock-container { background: linear-gradient(135deg, #FFFBEB 0%, #FEF3C7 100%); border: 3px solid #FCD34D; border-radius: var(--radius-lg); padding: 24px; text-align: center; }
    .vip-price-tag { display: inline-block; background: #F59E0B; color: #FFF; font-weight: 900; font-size: 16px; padding: 10px 24px; border-radius: 30px; margin: 14px 0; animation: pulse 2s infinite; }
    .vip-grid-forms { display: grid; grid-template-columns: 1fr; gap: 20px; max-width: 800px; margin: 20px auto 0; }
    @media (min-width: 768px) { .vip-grid-forms { grid-template-columns: 1fr 1fr; } }
    .vip-form-box { background: #FFF; padding: 20px; border-radius: var(--radius-md); border: 2px solid #FCD34D; text-align: left; transition: transform 0.3s; }
    .vip-form-box:hover { transform: translateY(-4px); box-shadow: var(--shadow-md); }
    .vip-input { width: 100%; padding: 12px; font-size: 14px; border: 2px solid #E2E8F0; border-radius: 10px; margin-bottom: 12px; outline: none; font-family: 'Poppins'; }
    .vip-input:focus { border-color: #F59E0B; }
    .btn-vip-checkout { background: linear-gradient(135deg, #F59E0B 0%, #D97706 100%); color: #FFF; font-weight: 800; font-size: 15px; padding: 14px 18px; border-radius: 12px; border: none; cursor: pointer; width: 100%; display: block; text-align: center; transition: all 0.2s; }
    .btn-vip-checkout:hover { transform: translateY(-3px) scale(1.02); box-shadow: 0 6px 16px rgba(245, 158, 11, 0.4); }

    /* MODAIS */
    .modal-overlay { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(15, 23, 42, 0.8); backdrop-filter: blur(6px); z-index: 99999; justify-content: center; align-items: center; padding: 20px; }
    .modal-overlay.active { display: flex; animation: fadeIn 0.3s; }
    .modal-box { background: #FFF; border-radius: var(--radius-lg); padding: 24px; max-width: 450px; width: 100%; text-align: center; border: 4px solid var(--primary); position: relative; box-shadow: 0 20px 40px rgba(0,0,0,0.3); }
    .modal-close { position: absolute; top: 16px; right: 16px; background: #F1F5F9; border: none; width: 36px; height: 36px; border-radius: 50%; font-weight: bold; font-size: 16px; cursor: pointer; transition: background 0.2s; }
    .modal-close:hover { background: #E2E8F0; color: #EF4444; }

    /* TOAST E COOKIES */
    .cookie-banner { position: fixed; bottom: 0; left: 0; width: 100%; background: #1E293B; color: #FFF; padding: 16px 24px; display: flex; align-items: center; justify-content: space-between; gap: 16px; flex-wrap: wrap; z-index: 99998; animation: slideUp 0.5s ease forwards; font-size: 13px; font-weight: 600; box-shadow: 0 -4px 20px rgba(0,0,0,0.2); }
    .cookie-banner.hidden { display: none; }
    .btn-cookie { background: #10B981; color: #FFF; border: none; padding: 10px 20px; border-radius: 8px; font-weight: 800; cursor: pointer; transition: transform 0.2s; }
    .btn-cookie:hover { transform: scale(1.05); }

    .floating-vip-badge { position: fixed; bottom: 24px; right: 24px; background: linear-gradient(135deg, #F59E0B 0%, #D97706 100%); color: #FFF; padding: 14px 24px; border-radius: 50px; font-size: 15px; font-weight: 900; box-shadow: 0 8px 24px rgba(245, 158, 11, 0.4); display: flex; align-items: center; gap: 8px; cursor: pointer; border: 2px solid #FDE68A; z-index: 999; transition: transform 0.3s cubic-bezier(0.4, 0, 0.2, 1); }
    .floating-vip-badge:hover { transform: scale(1.1) translateY(-5px); }

    #visualToast { position: fixed; bottom: 80px; left: 50%; transform: translateX(-50%) translateY(100px); background: #0F172A; color: #FFF; padding: 12px 24px; border-radius: 30px; font-size: 14px; font-weight: 700; transition: transform 0.3s; z-index: 999999; pointer-events: none; opacity: 0; }
    #visualToast.show { transform: translateX(-50%) translateY(0); opacity: 1; }

    footer { text-align: center; padding: 30px 20px; font-size: 13px; color: var(--text-muted); font-weight: 600; margin-top: auto; display: flex; flex-direction: column; gap: 8px; }
    footer a { color: var(--primary); text-decoration: underline; cursor: pointer; }
  </style>
</head>
<body onclick="desbloquearAudioMobileOnce()">

  <!-- BANNER DE COOKIES -->
  <div id="cookieBanner" class="cookie-banner">
    <div>🍪 Olá! A Turminha do Xexéu usa cookies (no seu próprio aparelho) para salvar o progresso dos jogos e suas rotinas. <a onclick="abrirPrivacidade()" style="color:#60A5FA; cursor:pointer; text-decoration:underline;">Ler Política</a>.</div>
    <button class="btn-cookie" onclick="aceitarCookies()">Entendi e Aceito!</button>
  </div>

  <div id="visualToast">Aviso</div>

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

  <!-- MODAL: POLÍTICA DE PRIVACIDADE -->
  <div id="modalPrivacidade" class="modal-overlay">
    <div class="modal-box" style="text-align:left;">
      <button class="modal-close" onclick="fecharPrivacidade()">✕</button>
      <h3 style="color:var(--primary-dark); font-weight:900; margin-bottom:12px; font-size:20px;">🔒 Política de Privacidade</h3>
      <p style="font-size:13px; color:var(--text-muted); line-height:1.6; margin-bottom:10px;">A Turminha do Xexéu valoriza a segurança das crianças. Não rastreamos dados pessoais sensíveis.</p>
      <ul style="font-size:13px; color:var(--text-muted); line-height:1.6; padding-left:20px;">
        <li>Seus pontos, desenhos e rotinas são salvos <strong>localmente</strong> no seu dispositivo (LocalStorage).</li>
        <li>Dados VIP (e-mail) são processados de forma segura apenas para liberar acesso ao conteúdo.</li>
        <li>Não exibimos anúncios de terceiros que rastreiam crianças.</li>
      </ul>
      <p style="font-size:13px; color:var(--text-muted); margin-top:10px; font-weight:700;">Dúvidas? turminhaxexeu@gmail.com</p>
    </div>
  </div>

  <!-- MODAL: PARENTAL GATE -->
  <div id="modalParentalGate" class="modal-overlay">
    <div class="modal-box" style="border-color:#F59E0B; max-width:400px;">
      <h3 style="color: #92400E; font-size: 22px; margin-bottom: 8px; font-weight: 900;">🔒 Acesso dos Pais</h3>
      <p style="font-size: 14px; color: #475569; margin-bottom: 16px; font-weight: 600;">Resolva a conta matemática para continuar:</p>
      <div id="desafioMatematicoTexto" style="font-size: 32px; font-weight: 900; color: #1E293B; margin: 12px 0;">3 + 4 = ?</div>
      <input type="number" id="respostaDesafio" style="width: 120px; padding: 12px; font-size: 22px; text-align: center; border: 3px solid #CBD5E1; border-radius: 12px; margin-bottom: 20px; font-weight: 900; outline: none;" placeholder="?">
      <div style="display: flex; gap: 12px; justify-content: center;">
        <button onclick="fecharParentalGate()" style="padding: 14px 24px; border: none; border-radius: 12px; background: #E2E8F0; font-weight: 800; cursor: pointer; font-size: 15px;">Voltar</button>
        <button onclick="verificarParentalGate()" style="padding: 14px 28px; border: none; border-radius: 12px; background: #F59E0B; color: #FFF; font-weight: 900; cursor: pointer; font-size: 15px;">Entrar ➔</button>
      </div>
    </div>
  </div>

  <!-- BOTÃO FLUTUANTE VIP -->
  <div class="floating-vip-badge float-anim" onclick="abrirAreaProtegida('vip')">
    <span style="font-size:18px;">⭐</span>
    <span>Seja VIP (R$ 6,00)</span>
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
        <button class="action-btn-pill" onclick="mudarPagina('perfil')"><span>👤</span></button>
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
      <div class="top-vip-announcement" onclick="abrirAreaProtegida('vip')">
        <span>💡 Dica: Se o som estiver mudo, toque nos 3 pontinhos e escolha "Abrir no Chrome" ou "Abrir no Safari"!<br>⭐ Desbloqueie todo o Drive de Atividades e Ferramentas TEA por R$ 6,00/mês! Clique Aqui! 💖</span>
      </div>

      <section class="banner-intro-grid">
        <div class="banner-container"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994339/BANNER_SITE_TURMINHA_DO_XEXEU.png" class="banner-img"></div>
        <div class="intro-box hover-float">
          <h2><span>✨ Educando com Alegria e Amor</span><button class="btn-audio-mini" onclick="lerTexto('Mais do que um nome divertido, a Turminha do Xexéu é o nosso jeito de honrar as raízes e a história da nossa família.')">🔊</button></h2>
          <p>Mais do que um nome divertido, a <strong>Turminha do Xexéu</strong> é o nosso jeito de honrar as raízes e a história da nossa família.</p>
          <p>O nome <strong>Xexéu</strong> é uma homenagem que atravessa gerações. Ele honra a memória de Mariano Xexéu e celebra a vida de seu filho, Pedro Mariano, grande inspiração para o nosso querido Vovô Beto.</p>
          <p>A Vovó Hilda é inspirada na inesquecível Astrogilda Grispym, representando o amor que não conhece o tempo.</p>
        </div>
      </section>

      <section class="social-round-section">
        <a href="https://www.youtube.com/@turminhaxe_xeu" target="_blank" class="social-round-btn"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908275/YT.png" alt="YouTube"></a>
        <a href="https://music.youtube.com/channel/UC8KOg4IH-h0YNrpKlfIl2Vw" target="_blank" class="social-round-btn"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908275/YT_MUSIC.png"></a>
        <a href="https://www.instagram.com/turminhaxe_xeu/" target="_blank" class="social-round-btn"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908273/INDTAGRAM.png"></a>
        <a href="https://www.tiktok.com/@turminhaxe_xeu" target="_blank" class="social-round-btn"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908275/TIKTOK.png"></a>
        <a href="https://open.spotify.com/intl-pt/artist/6ykKQ3uP6Wl2REylKJAdJ6?si=QqrYhcP2REaiUA9LFtjT4g" target="_blank" class="social-round-btn"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908274/SPOTIFY.png"></a>
        <a href="https://www.facebook.com/profile.php?id=61585431586796" target="_blank" class="social-round-btn"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908273/FACEBOOK.png"></a>
        <a href="https://www.threads.net/@turminhaxe_xeu" target="_blank" class="social-round-btn"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908274/THRENDS.png"></a>
        <a href="https://br.pinterest.com/turminhaxe_xeu" target="_blank" class="social-round-btn"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908274/PINTEREST.png"></a>
      </section>

      <section class="section-family-container">
        <div>
          <h3 class="family-group-title"><span>✨ O Símbolo e Mascote</span><button class="btn-audio-mini" onclick="lerTexto('Toque nos personagens para ouvir!')">🔊</button></h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-especial" onclick="abrirFichaPersonagem('Xexéu')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_XEXEU.png" class="floating-char-img"><span class="floating-char-name">Xexéu</span><span class="floating-char-tag">Mascote Oficial</span><p class="floating-char-desc">Inspirado no pássaro xexéu e no nome do bisavô Mariano Xexéu.</p></div>
            <div class="floating-char-card card-especial" onclick="abrirFichaPersonagem('Capilé')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994882/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_CAPILE.png" class="floating-char-img"><span class="floating-char-name">Capilé</span><span class="floating-char-tag">O Companheiro</span><p class="floating-char-desc">Cachorrinho de orelhas grandes e coleira azul-celeste!</p></div>
          </div>
        </div>

        <div>
          <h3 class="family-group-title"><span>💖 A Casa da Maya e do Theo</span><button class="btn-audio-mini" onclick="lerTexto('A Casa da Maya e do Theo.')">🔊</button></h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-f1" onclick="abrirFichaPersonagem('Maya')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994884/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_MAYA.png" class="floating-char-img"><span class="floating-char-name">Maya</span><span class="floating-char-tag">Mãe & Guia</span><p class="floating-char-desc">Mãe dedicada da Iza e da Nina. Extremamente organizada e atenciosa.</p></div>
            <div class="floating-char-card card-f1" onclick="abrirFichaPersonagem('Theo')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_THEO.png" class="floating-char-img"><span class="floating-char-name">Theo</span><span class="floating-char-tag">Pai Protetor</span><p class="floating-char-desc">Pai da Iza e da Nina. Calmo, observador e com um sorriso tranquilo.</p></div>
            <div class="floating-char-card card-f1" onclick="abrirFichaPersonagem('Nina')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_NINA.png" class="floating-char-img"><span class="floating-char-name">Nina</span><span class="floating-char-tag">Super Esperta</span><p class="floating-char-desc">Super esperta, tem cabelos cacheados e adora aprender!</p></div>
            <div class="floating-char-card card-f1" onclick="abrirFichaPersonagem('Iza')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_IZA.png" class="floating-char-img"><span class="floating-char-name">Iza</span><span class="floating-char-tag">A Vaidosa</span><p class="floating-char-desc">Vestidinho rosa, cabelos ondulados e um jeitinho charmoso.</p></div>
          </div>
        </div>

        <div>
          <h3 class="family-group-title"><span>⚡ A Casa do Sam e da Lia</span><button class="btn-audio-mini" onclick="lerTexto('A Casa do Sam e da Lia.')">🔊</button></h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-f2" onclick="abrirFichaPersonagem('Sam')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_SAM.png" class="floating-char-img"><span class="floating-char-name">Sam</span><span class="floating-char-tag">Pai Inventor</span><p class="floating-char-desc">Paizão ruivo do Joca e do Leo. Adora construir brinquedos.</p></div>
            <div class="floating-char-card card-f2" onclick="abrirFichaPersonagem('Lia')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994884/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_LIA.png" class="floating-char-img"><span class="floating-char-name">Lia</span><span class="floating-char-tag">Mãe Alegria</span><p class="floating-char-desc">Mãe do Joca e do Leo. Estilosa, traz energia contagiante.</p></div>
            <div class="floating-char-card card-f2" onclick="abrirFichaPersonagem('Joca')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_JOCA.png" class="floating-char-img"><span class="floating-char-name">Joca</span><span class="floating-char-tag">O Divertido</span><p class="floating-char-desc">Menino de camiseta verde! Engraçado e super companheiro.</p></div>
            <div class="floating-char-card card-f2" onclick="abrirFichaPersonagem('Leo')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_LEO.png" class="floating-char-img"><span class="floating-char-name">Leo</span><span class="floating-char-tag">Explorador Focado</span><p class="floating-char-desc">Amante de detalhes e focado em suas descobertas.</p></div>
          </div>
        </div>

        <div>
          <h3 class="family-group-title"><span>👵👴 Os Avós</span><button class="btn-audio-mini" onclick="lerTexto('Os queridos Avós.')">🔊</button></h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-avos" onclick="abrirFichaPersonagem('Beto')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_VOVO_BETO.png" class="floating-char-img"><span class="floating-char-name">Vovô Beto</span><span class="floating-char-tag">Vovô Coruja</span><p class="floating-char-desc">Usa óculos quadrados. Traz paciência, bom humor e energia.</p></div>
            <div class="floating-char-card card-avos" onclick="abrirFichaPersonagem('Hilda')"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_VOVO_HILDA.png" class="floating-char-img"><span class="floating-char-name">Vovó Hilda</span><span class="floating-char-tag">Vovó Acolhedora</span><p class="floating-char-desc">Usa óculos redondos. Guardando doçura, abraços e valores.</p></div>
          </div>
        </div>
      </section>

      <!-- FORM DE SUPORTE (INÍCIO) -->
      <section class="support-form-box">
        <h3>📬 Precisa de Ajuda ou quer enviar uma Sugestão?</h3>
        <p>Escreva para nós! Sua mensagem será enviada diretamente para <strong>turminhaxexeu@gmail.com</strong>.</p>
        <input type="email" id="suporteEmailInicio" class="support-input" placeholder="Digite seu e-mail para retornarmos">
        <textarea id="suporteMensagemInicio" class="support-input" placeholder="Escreva aqui sua dúvida, sugestão ou reclamação..." style="resize: vertical; min-height: 100px;"></textarea>
        <button onclick="enviarSuporteReclamacao('Inicio')" id="btnEnviarSuporteInicio" style="background: var(--tea-blue); color: #FFF; border: none; padding: 14px 24px; border-radius: 12px; font-size: 16px; font-weight: 900; cursor: pointer; width: 100%; transition: transform 0.2s;">Enviar Mensagem ✉️</button>
      </section>
    </main>

    <!-- PÁGINA 2: VÍDEOS, MÚSICAS & SONS -->
    <main id="pagina-videos" class="page-content content-wrapper">
      <div class="media-section-grid">
        <div class="video-card hover-float">
          <h3 style="font-size:20px; font-weight:900; color:var(--primary-dark); margin-bottom:16px;">📺 Episódios no YouTube</h3>
          <div class="video-wrapper">
            <iframe src="https://www.youtube-nocookie.com/embed/videosseries?list=PLh42qmbnReoE_pM4lig3DpJaNGWqoT9uJ" allowfullscreen></iframe>
          </div>
        </div>
        <div class="video-card hover-float" style="border-color:#1DB954;">
          <h3 style="font-size:20px; font-weight:900; color:#1DB954; margin-bottom:16px;">🎧 Rádio da Turminha</h3>
          <div class="spotify-wrapper">
            <iframe style="border-radius:12px" src="https://open.spotify.com/embed/artist/6ykKQ3uP6Wl2REylKJAdJ6?utm_source=generator&theme=0" width="100%" height="352" frameBorder="0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy"></iframe>
          </div>
        </div>
      </div>

      <div class="interactive-card">
        <h4 style="font-size:22px; font-weight:900; color:var(--tea-blue); margin-bottom:12px;">🌙 Sons e Acalento (Grátis & VIP)</h4>
        <p style="font-size:14px; font-weight:600; color:#475569;">Sons suaves para relaxar, focar ou dormir.</p>
        <div class="media-card-grid">
          <div class="media-item-box" onclick="tocarSomReal('https://cdn.freesound.org/previews/237/237729_4284968-lq.mp3')"><span style="font-size:36px;">🌧️</span><strong style="font-size:15px;">Chuva Suave</strong><span style="font-size:12px; color:#16A34A; font-weight:900;">GRÁTIS</span></div>
          <div class="media-item-box" onclick="tocarSomReal('https://cdn.freesound.org/previews/322/322744_5121236-lq.mp3')"><span style="font-size:36px;">🐦</span><strong style="font-size:15px;">Passarinhos</strong><span style="font-size:12px; color:#16A34A; font-weight:900;">GRÁTIS</span></div>
          <div class="media-item-box locked" onclick="abrirAreaProtegida('vip')"><span class="media-badge-vip">👑 VIP</span><span style="font-size:36px;">🌊</span><strong style="font-size:15px;">Ondas do Mar</strong><span style="font-size:12px; color:#D97706; font-weight:900;">Desbloquear</span></div>
          <div class="media-item-box locked" onclick="abrirAreaProtegida('vip')"><span class="media-badge-vip">👑 VIP</span><span style="font-size:36px;">🔥</span><strong style="font-size:15px;">Fogueira</strong><span style="font-size:12px; color:#D97706; font-weight:900;">Desbloquear</span></div>
          <div class="media-item-box locked" onclick="abrirAreaProtegida('vip')"><span class="media-badge-vip">👑 VIP</span><span style="font-size:36px;">🍃</span><strong style="font-size:15px;">Vento Suave</strong><span style="font-size:12px; color:#D97706; font-weight:900;">Desbloquear</span></div>
        </div>
      </div>
    </main>

    <!-- PÁGINA 3: JOGOS -->
    <main id="pagina-jogos" class="page-content content-wrapper">
      <div class="age-group-section">
        <h3 class="age-title"><span>🎮 Central de Jogos</span></h3>
        <nav class="games-subnav">
          <button id="subtab-lousa" class="subnav-btn active" onclick="mudarSubJogo('lousa')">🎨 Lousa Mágica</button>
          <button id="subtab-contar" class="subnav-btn" onclick="mudarSubJogo('contar')">🔢 Contar</button>
          <button id="subtab-letras" class="subnav-btn" onclick="mudarSubJogo('letras')">🔤 Letras</button>
          <button id="subtab-memoria" class="subnav-btn" onclick="mudarSubJogo('memoria')">🧠 Memória</button>
          <button id="subtab-quiz" class="subnav-btn" onclick="mudarSubJogo('quiz')">❓ Quiz</button>
        </nav>

        <!-- LOUSA MÁGICA -->
        <div id="game-lousa" class="game-section-page active-game-page interactive-card">
          <h4 style="font-weight: 900; margin-bottom: 12px; font-size: 20px;">🎨 Lousa Mágica & Colorir</h4>
          <div id="coloringSelectGrid" class="coloring-select-grid"></div>
          
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
            <div class="color-dot" style="background: #000000;" onclick="mudarCor('#000000')"></div>
            <!-- BORRACHA -->
            <div class="color-dot" style="background: #FFFFFF; border: 2px dashed #CBD5E1; display:flex; align-items:center; justify-content:center; font-size:18px;" onclick="mudarCor('#FFFFFF')" title="Borracha">🧽</div>
            
            <button onclick="limparCanvas()" style="padding:10px 18px; font-weight:800; border-radius:12px; border:none; background:#FEE2E2; color:#DC2626; cursor:pointer; font-size: 14px; margin-left:10px;">Limpar 🗑️</button>
            <button onclick="salvarFotoDesenho()" style="padding:10px 18px; font-weight:800; border-radius:12px; border:none; background:#D1FAE5; color:#065F46; cursor:pointer; font-size: 14px;">Salvar 📸</button>
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
          <div id="memoryBoard" class="memory-board"></div>
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
          <div style="display:flex; align-items:center; justify-content:center; gap:12px; margin-bottom:10px;">
            <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_LEO.png" style="width:60px; height:60px; object-fit:contain;">
            <h3 style="margin:0; font-size:24px;">🧩 Espaço TEA com o Leo</h3>
          </div>
          <p style="font-size: 15px; color: #475569; font-weight: 600;">"Oi! Eu sou o Leo. Vamos fazer tudo com calma?"</p>
        </div>

        <div class="interactive-card" style="border-color: #BAE6FD; margin-bottom: 20px;">
          <h4 style="color: var(--tea-blue); font-weight: 900; font-size: 18px; margin-bottom: 12px;">🗣️ Cartões de Fala (CAA)</h4>
          <div class="caa-grid">
            <div class="caa-btn hover-float" onclick="lerTexto('Eu quero água, por favor.')"><span>💧</span><p>Água</p></div>
            <div class="caa-btn hover-float" onclick="lerTexto('Estou com fome.')"><span>🍎</span><p>Comer</p></div>
            <div class="caa-btn hover-float" onclick="lerTexto('Preciso ir ao banheiro.')"><span>🚽</span><p>Banheiro</p></div>
            <div class="caa-btn hover-float" onclick="lerTexto('Quero brincar.')"><span>🧸</span><p>Brincar</p></div>
            <div class="caa-btn hover-float" onclick="lerTexto('Quero descansar.')"><span>💤</span><p>Descansar</p></div>
            <div class="caa-btn hover-float" onclick="lerTexto('Preciso de ajuda.')"><span>🤝</span><p>Ajuda</p></div>
          </div>
        </div>

        <div class="interactive-card" style="border-color: #BAE6FD;">
          <h4 style="color: var(--tea-blue); font-weight: 900; font-size: 18px; margin-bottom: 12px;">❤️ Como estou me sentindo?</h4>
          <div class="emotion-card-grid">
            <div class="emotion-card hover-float" onclick="responderMinhaEmocao('Feliz')"><span>😄</span><p style="color: #16A34A;">Feliz</p></div>
            <div class="emotion-card hover-float" onclick="responderMinhaEmocao('Calmo')"><span>😌</span><p style="color: var(--tea-blue);">Calmo</p></div>
            <div class="emotion-card hover-float" onclick="responderMinhaEmocao('Triste')"><span>😢</span><p style="color: #475569;">Triste</p></div>
            <div class="emotion-card hover-float" onclick="responderMinhaEmocao('Bravo')"><span>😤</span><p style="color: #DC2626;">Bravo</p></div>
          </div>
        </div>
      </div>
    </main>

    <!-- PÁGINA 5: LIVROS -->
    <main id="pagina-livros" class="page-content content-wrapper">
      <div class="age-group-section">
        <h3 class="age-title">📚 Biblioteca da Turminha</h3>
        <p style="font-size:15px; font-weight:600; color:#475569; text-align:center;">As histórias mágicas da Turminha estão sendo escritas e ilustradas com muito amor!</p>
        <div class="book-card-grid">
          <div class="book-card float-anim"><span style="font-size:50px;">🚧</span><strong style="font-size:18px; display:block; margin:10px 0;">Em Breve</strong><span style="font-size:14px; color:#64748B;">História 1</span></div>
          <div class="book-card float-anim" style="animation-delay: 1s;"><span style="font-size:50px;">🚧</span><strong style="font-size:18px; display:block; margin:10px 0;">Em Breve</strong><span style="font-size:14px; color:#64748B;">História 2</span></div>
          <div class="book-card float-anim" style="animation-delay: 2s;"><span style="font-size:50px;">🚧</span><strong style="font-size:18px; display:block; margin:10px 0;">Em Breve</strong><span style="font-size:14px; color:#64748B;">História VIP</span></div>
        </div>
      </div>
    </main>

    <!-- PÁGINA 6: ROTINA -->
    <main id="pagina-rotina" class="page-content content-wrapper">
      <div class="age-group-section">
        <h3 class="age-title">📅 Rotina & Cuidados (Crie a sua!)</h3>
        <div class="interactive-card" style="text-align:left; margin-bottom:24px;">
          <h4 style="font-size:18px; font-weight:900; margin-bottom:12px;">Adicionar Tarefa na Rotina:</h4>
          <p style="font-size:13px; color:#64748B; margin-bottom:12px;">Grátis: Até 3 tarefas simultâneas | VIP: Ilimitado!</p>
          <div class="rotina-add-box">
            <input type="text" id="rotina-nova-texto" placeholder="Ex: Hora do banho 🛁">
            <button onclick="adicionarRotinaPersonalizada()">Adicionar ➕</button>
          </div>
          <div id="lista-rotinas-dinamica"></div>
        </div>
      </div>
    </main>

    <!-- PÁGINA 7: CONQUISTAS -->
    <main id="pagina-conquistas" class="page-content content-wrapper">
      <div class="age-group-section">
        <h3 class="age-title">🏆 Minhas Conquistas</h3>
        <div class="conquistas-box">
          <span>⭐ Pontos: <strong id="placar-pontos">0</strong></span>
          <span id="medalha-status">Iniciante</span>
        </div>

        <div class="interactive-card hover-float" style="border: 3px double #F59E0B; background: #FFFBEB;">
          <h4 style="color:#92400E; font-size:22px; font-weight:900; margin-bottom:12px;">🎓 Certificado de Super Fã</h4>
          <input type="text" id="nome-certificado-input" placeholder="Digite o nome da criança" style="padding:14px; border-radius:12px; border:2px solid #FCD34D; font-size:16px; font-weight:700; outline:none; margin-bottom:16px; width:100%; max-width:360px;">
          <br>
          <button onclick="gerarCertificadoGeral()" style="background:#D97706; color:#FFF; border:none; padding:14px 28px; border-radius:12px; font-size:16px; font-weight:900; cursor:pointer; transition:transform 0.2s;">Gerar Certificado ⭐</button>
          <div id="boxCertificadoResultado" style="display:none; margin-top:24px; padding:20px; background:#FFF; border-radius:12px; border:2px solid #FCD34D;">
            <h3 style="color:#1D4ED8; font-size:28px; text-transform:uppercase;" id="txtNomeCertificado"></h3>
            <p style="font-weight:800; color:#B45309; font-size:16px;">É oficialmente Super Fã da Turminha do Xexéu! 🌟</p>
          </div>
        </div>
      </div>
    </main>

    <!-- PÁGINA 8: ÁREA VIP -->
    <main id="pagina-vip" class="page-content content-wrapper">
      <div class="age-group-section">
        <div class="vip-lock-container">
          <h3 style="font-size:26px; color:#92400E; font-weight:900;">⭐ Clube VIP da Turminha do Xexéu</h3>
          <div class="vip-price-tag">Apenas R$ 6,00 / mês</div>
          
          <div style="background:#FFF; padding:24px; border-radius:16px; border:2px dashed #F59E0B; text-align:left; font-size:16px; margin:20px auto; color:#78350F; max-width: 800px;">
            <strong style="display:block; font-size:20px; margin-bottom:12px;">👑 Benefícios MUITO VIP:</strong>
            <ul style="margin-left:24px; line-height:1.8; font-weight:600;">
              <li>📁 <strong>Drive Pedagógico:</strong> Arquivos em PDF de alta qualidade para imprimir e colorir em casa.</li>
              <li>📅 <strong>Rotina Ilimitada:</strong> Crie quantas tarefas visuais diárias quiser.</li>
              <li>🎨 <strong>Lousa Completa:</strong> Desbloqueie todos os 12 personagens para colorir.</li>
              <li>🧩 <strong>CAA Editável Livre:</strong> Adicione seus próprios emojis e frases de comunicação livremente.</li>
              <li>🎵 <strong>Sons Exclusivos:</strong> Fogueira, Vento, Ondas e mais acalentos.</li>
            </ul>
          </div>

          <div class="vip-grid-forms">
            <div class="vip-form-box">
              <h4 style="font-size:18px;">✨ Quero Assinar o VIP</h4>
              <input type="email" id="cad-email" class="vip-input" placeholder="Seu e-mail principal">
              <input type="password" id="cad-senha" class="vip-input" placeholder="Crie uma senha parental">
              <a href="javascript:void(0)" class="btn-vip-checkout" id="btnCheckoutVip" onclick="salvarECadastrar()">Quero Ser VIP por R$ 6,00 💳</a>
            </div>

            <div class="vip-form-box" style="border-color: #CBD5E1;">
              <h4 style="font-size:18px; color: #1E293B;">🔑 Já sou Assinante</h4>
              <input type="email" id="log-email" class="vip-input" placeholder="E-mail cadastrado">
              <input type="password" id="log-senha" class="vip-input" placeholder="Sua senha">
              <button onclick="fazerLogin()" id="btnLoginVip" style="width:100%; padding:14px; background:#3B82F6; color:#FFF; border:none; border-radius:12px; font-weight:900; font-size:16px; cursor:pointer; transition:transform 0.2s;">Entrar no Painel</button>
            </div>
          </div>
        </div>

        <!-- FORM DE SUPORTE (VIP) -->
        <div class="support-form-box" style="margin-top: 24px;">
          <h3>📬 Precisa de Ajuda ou quer enviar uma Sugestão?</h3>
          <p>Escreva para nós! Sua mensagem será enviada diretamente para <strong>turminhaxexeu@gmail.com</strong>.</p>
          <input type="email" id="suporteEmailVip" class="support-input" placeholder="Digite seu e-mail para retornarmos">
          <textarea id="suporteMensagemVip" class="support-input" placeholder="Escreva aqui sua dúvida, sugestão ou reclamação..." style="resize: vertical; min-height: 100px;"></textarea>
          <button onclick="enviarSuporteReclamacao('Vip')" id="btnEnviarSuporteVip" style="background: var(--tea-blue); color: #FFF; border: none; padding: 14px 24px; border-radius: 12px; font-size: 16px; font-weight: 900; cursor: pointer; width: 100%; transition: transform 0.2s;">Enviar Mensagem ✉️</button>
        </div>
      </div>
    </main>

    <!-- PÁGINAS OCULTAS: CONFIG & PERFIL -->
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
          <div id="avatarEscolhaGrid" class="avatar-escolha-grid"></div>
        </div>
      </div>
    </main>

    <footer class="content-wrapper">
      <span>© Turminha do Xexéu — eve Design — Todos os direitos reservados.</span>
      <span><a onclick="abrirPrivacidade()">Política de Privacidade</a> | <a onclick="document.getElementById('cookieBanner').classList.remove('hidden')">Configurar Cookies</a></span>
    </footer>

  </div>

  <script>
    /* CONEXÃO COM GOOGLE APPS SCRIPT */
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
    let desafioResultadoEsperado = 0;
    let destinoAposGate = 'vip';
    let somAcalentoAtual = null;

    const PERSONAGENS = [
      { nome: 'Xexéu', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_XEXEU.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994876/DESENHOS_DA_LOUSA_XEXEU.png', letra: 'X', tag: 'Mascote Oficial', quem: 'Pássaro azul de boina amarela.', gosto: 'Cantar, voar e contar histórias.', frase: 'Educando com alegria!' },
      { nome: 'Capilé', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994882/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_CAPILE.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994874/DESENHOS_DA_LOUSA_CAPILE.png', letra: 'C', tag: 'O Companheiro', quem: 'Cachorrinho fiel.', gosto: 'Correr e brincar.', frase: 'Sempre pronto para a brincadeira!' },
      { nome: 'Maya', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994884/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_MAYA.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994875/DESENHOS_DA_LOUSA_MAYA.png', letra: 'M', tag: 'Mãe & Guia', quem: 'Mãe dedicada e porto seguro.', gosto: 'Ler histórias em família.', frase: 'O amor transforma tudo.' },
      { nome: 'Theo', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_THEO.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994877/DESENHOS_DA_LOUSA_THEO.png', letra: 'T', tag: 'Pai Protetor', quem: 'Pai paciente e atencioso.', gosto: 'Ensinar e dar abraços.', frase: 'Com calma aprendemos melhor.' },
      { nome: 'Nina', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_NINA.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994876/DESENHOS_DA_LOUSA_NINA.png', letra: 'N', tag: 'Super Esperta', quem: 'Menina de cabelos cacheados.', gosto: 'Descobrir coisas novas.', frase: 'Aprender é super divertido!' },
      { nome: 'Iza', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_IZA.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994873/DESENHOS_DA_LOUSA_IZA.png', letra: 'I', tag: 'A Vaidosa', quem: 'Menina charmosa.', gosto: 'Cantar e usar laços bonitos.', frase: 'Ser gentil é lindo!' },
      { nome: 'Sam', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_SAM.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994876/DESENHOS_DA_LOUSA_SAM.png', letra: 'S', tag: 'Pai Inventor', quem: 'Paizão ruivo apaixonado por criar.', gosto: 'Montar máquinas.', frase: 'Toda ideia é uma invenção!' },
      { nome: 'Lia', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994884/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_LIA.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994875/DESENHOS_DA_LOUSA_LIA.png', letra: 'L', tag: 'Mãe Alegria', quem: 'Mãe cheia de energia positiva.', gosto: 'Dançar.', frase: 'A alegria é nosso superpoder!' },
      { nome: 'Joca', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_JOCA.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994874/DESENHOS_DA_LOUSA_JOCA.png', letra: 'J', tag: 'O Divertido', quem: 'Menino engraçado.', gosto: 'Fazer piadas.', frase: 'O importante é se divertir!' },
      { nome: 'Leo', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_LEO.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994875/DESENHOS_DA_LOUSA_LEO.png', letra: 'L', tag: 'Explorador Focado', quem: 'Observador detalhista.', gosto: 'Organizar rotinas.', frase: 'Tudo no nosso próprio tempo.' },
      { nome: 'Beto', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_VOVO_BETO.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994876/DESENHOS_DA_LOUSA_VOVO_BETO.png', letra: 'B', tag: 'Vovô Coruja', quem: 'Vovô de risada boa.', gosto: 'Passear ao ar livre.', frase: 'A família é a maior riqueza.' },
      { nome: 'Hilda', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_VOVO_HILDA.png', lousa: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994877/DESENHOS_DA_LOUSA_VOVO_HILDA.png', letra: 'H', tag: 'Vovó Acolhedora', quem: 'Vovó de abraços doces.', gosto: 'Fazer bolos.', frase: 'O amor não envelhece.' }
    ];

    /* APP SCRIPT: ENVIO DE SUPORTE E CADASTRO VIP */
    function enviarSuporteReclamacao(local) {
      const email = document.getElementById('suporteEmail' + local).value.trim();
      const mensagem = document.getElementById('suporteMensagem' + local).value.trim();
      const btn = document.getElementById('btnEnviarSuporte' + local);

      if (!email || !mensagem) { alert("⚠️ Preencha o e-mail e a mensagem!"); return; }
      btn.innerText = "Enviando... ⏳"; btn.disabled = true;

      fetch(URL_SCRIPT, {
        method: "POST", mode: "no-cors", headers: { "Content-Type": "application/json" },
        body: JSON.stringify({ tipo: "SUPORTE", email: email, mensagem: mensagem })
      }).then(() => {
        lerTexto("Sua mensagem foi enviada!");
        document.getElementById('suporteEmail' + local).value = ''; document.getElementById('suporteMensagem' + local).value = '';
        btn.innerText = "Mensagem Enviada! ✅"; btn.style.background = "#10B981";
        setTimeout(() => { btn.innerText = "Enviar Mensagem ✉️"; btn.style.background = "var(--tea-blue)"; btn.disabled = false; }, 3000);
      }).catch((e) => {
        alert("❌ Erro ao enviar. Tente novamente."); btn.innerText = "Enviar Mensagem ✉️"; btn.disabled = false;
      });
    }

    function salvarECadastrar() {
      const email = document.getElementById('cad-email').value.trim();
      const senha = document.getElementById('cad-senha').value.trim();
      if (!email || !senha) { alert("Preencha o e-mail e crie a senha!"); return; }
      
      const btn = document.getElementById('btnCheckoutVip');
      btn.innerText = "Processando... ⏳";
      
      fetch(URL_SCRIPT, {
        method: "POST", mode: "no-cors", headers: { "Content-Type": "application/json" },
        body: JSON.stringify({ tipo: "NOVO_CLIENTE", email: email, senha: senha })
      }).then(() => {
        lerTexto("Cadastro iniciado!");
        window.open("https://pay.kiwify.com.br/avOqrEg", "_blank");
        btn.innerText = "Quero Ser VIP por R$ 6,00 💳";
      }).catch(() => { btn.innerText = "Quero Ser VIP por R$ 6,00 💳"; });
    }

    function fazerLogin() {
      const email = document.getElementById('log-email').value.trim();
      const senha = document.getElementById('log-senha').value.trim();
      
      if (senha === SENHA_MESTRA) { 
          isUserVip = true; localStorage.setItem('turminha_vip_status', 'ativo'); 
          alert("Acesso Mestre Liberado!"); lerTexto("Bem-vindo de volta ao VIP!"); 
          window.location.reload(); return; 
      }
      
      if (!email || !senha) { alert("Preencha o e-mail e a senha."); return; }
      
      const btn = document.getElementById('btnLoginVip');
      btn.innerText = "Verificando... ⏳";
      
      fetch(`${URL_SCRIPT}?email=${encodeURIComponent(email)}&senha=${encodeURIComponent(senha)}`)
        .then(res => res.json())
        .then(data => {
          if(data.liberado) {
            isUserVip = true; localStorage.setItem('turminha_vip_status', 'ativo'); 
            alert("Acesso Confirmado!"); window.location.reload();
          } else {
            alert("Senha incorreta ou assinatura pendente."); btn.innerText = "Entrar no Painel";
          }
        })
        .catch(() => { alert("Erro ao verificar conexão."); btn.innerText = "Entrar no Painel"; });
    }

    /* FUNÇÕES BÁSICAS GERAIS */
    function lerTexto(texto) {
      exibirToast(texto);
      if (!audioAtivo || !('speechSynthesis' in window)) return;
      try { window.speechSynthesis.cancel(); const u = new SpeechSynthesisUtterance(texto); u.lang = 'pt-BR'; u.rate = 1.0; u.pitch = 1.05; window.speechSynthesis.speak(u); } catch (e) {}
    }

    function desbloquearAudioMobileOnce() { if (!audioUnlocked && 'speechSynthesis' in window) { window.speechSynthesis.speak(new SpeechSynthesisUtterance("")); audioUnlocked = true; } }

    function abrirFichaPersonagem(nome) {
      const p = PERSONAGENS.find(x => x.nome === nome);
      if (!p) return;
      document.getElementById('ficha-img').src = p.img; document.getElementById('ficha-nome').innerText = p.nome; document.getElementById('ficha-apelido').innerText = `"${p.tag}"`;
      document.getElementById('ficha-quem').innerText = p.quem; document.getElementById('ficha-gosto').innerText = p.gosto; document.getElementById('ficha-frase').innerText = p.frase;
      document.getElementById('btnFichaOuvir').onclick = () => lerTexto(`Oi! Eu sou ${p.nome}, ${p.tag}. ${p.quem} ${p.frase}`);
      document.getElementById('modalFichaPersonagem').classList.add('active'); lerTexto(`Conheça ${p.nome}!`);
    }

    function fecharFichaPersonagem() { document.getElementById('modalFichaPersonagem').classList.remove('active'); }
    function abrirPrivacidade() { document.getElementById('modalPrivacidade').classList.add('active'); }
    function fecharPrivacidade() { document.getElementById('modalPrivacidade').classList.remove('active'); }
    function aceitarCookies() { localStorage.setItem('turminha_cookies_aceito', 'true'); document.getElementById('cookieBanner').classList.add('hidden'); }

    function alternarAudioGlobal() {
      audioAtivo = !audioAtivo; const btn = document.getElementById('toggleAudioBtn');
      if (audioAtivo) { btn.classList.remove('muted'); document.getElementById('audioIcon').innerText = '🔊'; lerTexto("Voz ligada!"); } 
      else { if ('speechSynthesis' in window) window.speechSynthesis.cancel(); btn.classList.add('muted'); document.getElementById('audioIcon').innerText = '🔇'; exibirToast("Voz desligada!"); }
    }

    function toggleSensoryMode() {
      const ativado = document.body.classList.toggle('sensory-mode'); document.getElementById('btnSensoryHeader').innerHTML = ativado ? '🌿 Normal' : '🌿 Modo Calmo';
      if (somAcalentoAtual) { somAcalentoAtual.pause(); somAcalentoAtual = null; } lerTexto(ativado ? "Modo Calmo ativado" : "Modo normal ativado");
    }

    function exibirToast(t) {
      const toast = document.getElementById('visualToast'); if (!toast) return; toast.innerText = t; toast.classList.add('show'); setTimeout(() => toast.classList.remove('show'), 2800);
    }

    /* SISTEMA DE ROTINA (GRÁTIS VS VIP) */
    function renderizarRotinas() {
      const container = document.getElementById('lista-rotinas-dinamica'); container.innerHTML = '';
      rotinasSalvas.forEach((r, idx) => {
        const div = document.createElement('div'); div.className = `rotina-item ${r.feito ? 'concluido' : ''}`;
        div.innerHTML = `
          <span class="rotina-texto">${r.texto}</span>
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
      if (!texto) { alert("Escreva a tarefa antes de adicionar."); return; }
      if (!isUserVip && rotinasSalvas.length >= 3) { alert("🔒 No modo Grátis, você pode ter até 3 rotinas. Assine o VIP para ter Rotinas Ilimitadas!"); abrirAreaProtegida('vip'); return; }
      rotinasSalvas.push({ id: Date.now(), texto: texto, feito: false });
      localStorage.setItem('turminha_rotina', JSON.stringify(rotinasSalvas));
      document.getElementById('rotina-nova-texto').value = ''; renderizarRotinas(); lerTexto("Nova rotina adicionada!");
    }

    function toggleRotinaStatus(index) {
      rotinasSalvas[index].feito = !rotinasSalvas[index].feito;
      if(rotinasSalvas[index].feito) { adicionarPontos(5); lerTexto("Tarefa concluída!"); }
      localStorage.setItem('turminha_rotina', JSON.stringify(rotinasSalvas)); renderizarRotinas();
    }
    function removerRotina(index) { rotinasSalvas.splice(index, 1); localStorage.setItem('turminha_rotina', JSON.stringify(rotinasSalvas)); renderizarRotinas(); }

    /* PARENTAL GATE E NAVEGAÇÃO */
    function abrirAreaProtegida(destino) {
      destinoAposGate = destino; const n1 = Math.floor(Math.random() * 5) + 2; const n2 = Math.floor(Math.random() * 4) + 1; desafioResultadoEsperado = n1 + n2;
      document.getElementById('desafioMatematicoTexto').innerText = `${n1} + ${n2} = ?`; document.getElementById('respostaDesafio').value = ''; document.getElementById('modalParentalGate').classList.add('active');
    }
    function fecharParentalGate() { document.getElementById('modalParentalGate').classList.remove('active'); }
    function verificarParentalGate() {
      const resp = parseInt(document.getElementById('respostaDesafio').value);
      if (resp === desafioResultadoEsperado) { fecharParentalGate(); mudarPagina(destinoAposGate); lerTexto("Acesso liberado."); } 
      else { alert("Resposta incorreta! Tente novamente."); abrirAreaProtegida(destinoAposGate); }
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

    function responderMinhaEmocao(e) {
      if (e === 'Feliz') lerTexto("Que coisa maravilhosa estar feliz!"); else if (e === 'Calmo') lerTexto("Que momento bom e tranquilo.");
      else if (e === 'Triste') lerTexto("Tudo bem ficar triste. A Turminha te abraça."); else if (e === 'Bravo') lerTexto("Vamos respirar fundo juntos e acalmar.");
    }

    function tocarSomReal(url) {
      if (somAcalentoAtual) { somAcalentoAtual.pause(); if (somAcalentoAtual.src === url) { somAcalentoAtual = null; lerTexto("Som pausado"); return; } }
      somAcalentoAtual = new Audio(url); somAcalentoAtual.loop = true; somAcalentoAtual.play().catch(() => {}); lerTexto("Tocando som relaxante.");
    }

    /* CANVAS / LOUSA MÁGICA COM DESENHO LIVRE E VIP LOGIC */
    const canvas = document.getElementById('paintCanvas'); const ctx = canvas ? canvas.getContext('2d') : null;
    let desenhando = false, corAtual = '#3B82F6', tamanhoPincel = 4, imgContornoAtual = null;

    function renderizarLousaBtns() {
      const grid = document.getElementById('coloringSelectGrid');
      grid.innerHTML = '';
      
      const btnLivre = document.createElement('button');
      btnLivre.className = 'btn-color-draw selected';
      btnLivre.innerHTML = '✏️ Desenho Livre';
      btnLivre.onclick = () => { imgContornoAtual = null; limparCanvas(); document.querySelectorAll('.btn-color-draw').forEach(b => b.classList.remove('selected')); btnLivre.classList.add('selected'); };
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
        btnVip.className = 'btn-color-draw float-anim';
        btnVip.style.borderColor = '#F59E0B'; btnVip.style.background = '#FFFBEB'; btnVip.style.color = '#92400E';
        btnVip.innerHTML = '🔒 +9 Desenhos (VIP)';
        btnVip.onclick = () => abrirAreaProtegida('vip');
        grid.appendChild(btnVip);
      }
    }

    function redimensionarCanvas() {
      if (!canvas || !canvas.parentElement) return;
      canvas.width = canvas.parentElement.clientWidth - (window.innerWidth > 1024 ? 48 : 24); canvas.height = window.innerWidth > 1024 ? 480 : (window.innerWidth > 768 ? 350 : 260);
      if (imgContornoAtual) desenharContorno(imgContornoAtual);
    }

    function definirTamanhoPincel(tam, btn) { tamanhoPincel = tam; document.querySelectorAll('.btn-brush-size').forEach(b => b.classList.remove('active')); if (btn) btn.classList.add('active'); }
    function mudarCor(c) { corAtual = c; }
    function limparCanvas() { if (ctx) ctx.clearRect(0, 0, canvas.width, canvas.height); if (imgContornoAtual) desenharContorno(imgContornoAtual); }

    function carregarContornoPintar(url, btn) {
      document.querySelectorAll('.btn-color-draw').forEach(b => b.classList.remove('selected')); if (btn) btn.classList.add('selected');
      limparCanvas(); const img = new Image(); img.crossOrigin = "Anonymous"; img.src = url;
      img.onload = () => { imgContornoAtual = img; desenharContorno(img); };
    }

    function desenharContorno(img) {
      const ratio = Math.min(canvas.width / img.width, canvas.height / img.height) * 0.85;
      const w = img.width * ratio; const h = img.height * ratio;
      const x = (canvas.width - w) / 2; const y = (canvas.height - h) / 2;
      ctx.globalAlpha = 0.35; ctx.drawImage(img, x, y, w, h); ctx.globalAlpha = 1.0;
    }

    function salvarFotoDesenho() { const link = document.createElement('a'); link.download = 'meu-desenho.png'; link.href = canvas.toDataURL(); link.click(); lerTexto("Salvo com sucesso!"); }

    if (canvas) {
      const getPos = (e) => { const r = canvas.getBoundingClientRect(); const cx = e.touches ? e.touches[0].clientX : e.clientX; const cy = e.touches ? e.touches[0].clientY : e.clientY; return { x: cx - r.left, y: cy - r.top }; };
      const iniciar = (e) => { desenhando = true; const p = getPos(e); ctx.beginPath(); ctx.moveTo(p.x, p.y); ctx.strokeStyle = corAtual; ctx.lineWidth = tamanhoPincel; ctx.lineCap = 'round'; };
      const mover = (e) => { if (!desenhando) return; const p = getPos(e); ctx.lineTo(p.x, p.y); ctx.stroke(); if(e.preventDefault) e.preventDefault(); };
      const parar = () => { desenhando = false; };
      
      canvas.addEventListener('mousedown', iniciar); canvas.addEventListener('mousemove', mover); canvas.addEventListener('mouseup', parar);
      canvas.addEventListener('touchstart', iniciar, { passive: false }); canvas.addEventListener('touchmove', mover, { passive: false }); canvas.addEventListener('touchend', parar);
    }

    /* MINIGAMES SIMPLES */
    let qContar = 0;
    function carregarJogoContar() {
      qContar = Math.floor(Math.random() * 4) + 1; const char = PERSONAGENS[Math.floor(Math.random() * PERSONAGENS.length)];
      const display = document.getElementById('countDisplay'); display.innerHTML = '';
      for (let i = 0; i < qContar; i++) { const img = document.createElement('img'); img.src = char.img; img.style.cssText = 'width:60px; height:60px; object-fit:contain; margin:0 4px;'; display.appendChild(img); }
      const opts = document.getElementById('countOptions'); opts.innerHTML = '';
      for (let n = 1; n <= 4; n++) {
        const btn = document.createElement('button'); btn.className = 'btn-choice'; btn.innerText = n;
        btn.onclick = () => { if (n === qContar) { btn.classList.add('acertou'); lerTexto("Acertou!"); adicionarPontos(5); setTimeout(() => { btn.classList.remove('acertou'); carregarJogoContar(); }, 800); } else { btn.classList.add('errou'); lerTexto("Tente de novo!"); setTimeout(() => btn.classList.remove('errou'), 500); } };
        opts.appendChild(btn);
      }
    }

    let pLetraAtual = null;
    function carregarJogoLetra() {
      pLetraAtual = PERSONAGENS[Math.floor(Math.random() * PERSONAGENS.length)];
      document.getElementById('nome-letra-personagem').innerText = pLetraAtual.nome; document.getElementById('img-letra-personagem').src = pLetraAtual.img;
      const container = document.getElementById('opcoes-letras'); container.innerHTML = '';
      const alfabeto = ['A', 'B', 'C', 'D', 'E', 'F', 'I', 'J', 'L', 'M', 'N', 'P', 'S', 'T', 'X']; let opcoes = [pLetraAtual.letra];
      while (opcoes.length < 3) { let l = alfabeto[Math.floor(Math.random() * alfabeto.length)]; if (!opcoes.includes(l)) opcoes.push(l); }
      opcoes.sort(() => Math.random() - 0.5).forEach(l => {
        const btn = document.createElement('button'); btn.className = 'btn-choice'; btn.innerText = l;
        btn.onclick = () => { if (l === pLetraAtual.letra) { btn.classList.add('acertou'); lerTexto("Muito bem!"); adicionarPontos(5); setTimeout(() => { btn.classList.remove('acertou'); carregarJogoLetra(); }, 800); } else { btn.classList.add('errou'); lerTexto("Tente outra vez!"); setTimeout(() => btn.classList.remove('errou'), 500); } };
        container.appendChild(btn);
      });
    }

    let cMem = [], pCarta = null, travaMem = false, acertosMem = 0;
    function iniciarMemoria() {
      acertosMem = 0; const sorteados = [...PERSONAGENS].sort(() => Math.random() - 0.5).slice(0, 4); const imgs = sorteados.map(p => p.img);
      cMem = [...imgs, ...imgs].sort(() => Math.random() - 0.5); const board = document.getElementById('memoryBoard'); board.innerHTML = '';
      cMem.forEach(src => {
        const card = document.createElement('div'); card.className = 'memory-card'; card.dataset.img = src; card.innerText = '❓';
        card.onclick = () => {
          if (travaMem || card.classList.contains('flipped')) return;
          card.classList.add('flipped'); card.innerHTML = `<img src="${src}">`;
          if (!pCarta) pCarta = card;
          else {
            if (pCarta.dataset.img === src) { acertosMem++; lerTexto("Achou o par!"); pCarta = null; adicionarPontos(3); if (acertosMem === 4) { adicionarPontos(10); setTimeout(iniciarMemoria, 1800); } } 
            else { travaMem = true; setTimeout(() => { pCarta.classList.remove('flipped'); pCarta.innerText = '❓'; card.classList.remove('flipped'); card.innerText = '❓'; pCarta = null; travaMem = false; }, 900); }
          }
        };
        board.appendChild(card);
      });
    }

    function carregarQuiz() {
      const pAtual = PERSONAGENS[Math.floor(Math.random() * PERSONAGENS.length)];
      document.getElementById('quiz-img').src = pAtual.img; const container = document.getElementById('quiz-options'); container.innerHTML = '';
      let opcoes = [pAtual.nome]; while (opcoes.length < 3) { let o = PERSONAGENS[Math.floor(Math.random() * PERSONAGENS.length)].nome; if (!opcoes.includes(o)) opcoes.push(o); }
      opcoes.sort(() => Math.random() - 0.5).forEach(o => {
        const btn = document.createElement('button'); btn.className = 'btn-choice'; btn.style.fontSize = '14px'; btn.innerText = o;
        btn.onclick = () => { if (o === pAtual.nome) { btn.classList.add('acertou'); lerTexto("Isso mesmo!"); adicionarPontos(5); setTimeout(() => { btn.classList.remove('acertou'); carregarQuiz(); }, 800); } else { btn.classList.add('errou'); lerTexto("Tente novamente!"); setTimeout(() => btn.classList.remove('errou'), 500); } };
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
      grid.innerHTML = ''; const avatarAtual = localStorage.getItem('turminha_avatar') || PERSONAGENS[0].img;
      PERSONAGENS.forEach(p => {
        const img = document.createElement('img'); img.src = p.img; img.className = 'avatar-escolha-btn' + (p.img === avatarAtual ? ' selecionado' : '');
        img.onclick = () => { document.querySelectorAll('.avatar-escolha-btn').forEach(b => b.classList.remove('selecionado')); img.classList.add('selecionado'); localStorage.setItem('turminha_avatar', p.img); lerTexto(`${p.nome} escolhido como avatar!`); };
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
      adicionarPontos(0); carregarJogoContar(); carregarJogoLetra(); iniciarMemoria(); carregarQuiz(); renderizarRotinas();
      renderizarLousaBtns();
      if (localStorage.getItem('turminha_cookies_aceito') === 'true') document.getElementById('cookieBanner').classList.add('hidden');
      window.addEventListener('resize', redimensionarCanvas); setTimeout(redimensionarCanvas, 200);
    };
  </script>
</body>
</html>
