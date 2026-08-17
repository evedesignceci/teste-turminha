<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <title>Turminha do Xexéu - Portal Oficial</title>
  
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
      --radius-xl: 24px;
      --radius-lg: 16px;
      --radius-md: 12px;
      --shadow-sm: 0 4px 12px rgba(15, 23, 42, 0.05);
      --shadow-md: 0 8px 20px rgba(15, 23, 42, 0.08);
      --shadow-lg: 0 14px 30px rgba(59, 130, 246, 0.15);
    }

    /* MODO SENSORIAL PROFUNDO E CALMANTE */
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
    body.sensory-mode .tea-box, 
    body.sensory-mode .vip-card-box, 
    body.sensory-mode .vip-lock-container, 
    body.sensory-mode .interactive-card,
    body.sensory-mode .video-card { background: #FFFFFF !important; border: 2px solid #CBD5E1 !important; }
    
    body.sensory-mode .browser-notice-box,
    body.sensory-mode .top-vip-announcement,
    body.sensory-mode .social-round-section,
    body.sensory-mode .floating-vip-badge {
      display: none !important;
    }

    * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Poppins', system-ui, -apple-system, sans-serif; -webkit-tap-highlight-color: transparent; }

    body { background: var(--bg-gradient); color: var(--text-main); display: flex; justify-content: center; min-height: 100vh; padding: 8px 8px 50px; transition: background 0.3s ease; }

    .app-container { width: 100%; max-width: 1120px; background: rgba(255, 255, 255, 0.98); backdrop-filter: blur(10px); border-radius: var(--radius-xl); box-shadow: var(--shadow-lg); overflow: hidden; display: flex; flex-direction: column; gap: 20px; padding-bottom: 24px; border: 3px solid #FFFFFF; }

    header { padding: 14px 20px; background: linear-gradient(135deg, #BAE6FD 0%, #E0F2FE 100%); display: flex; align-items: center; justify-content: space-between; border-radius: var(--radius-lg); margin: 12px 12px 0; box-shadow: var(--shadow-sm); }
    .logo-img { max-width: 150px; height: auto; object-fit: contain; }

    .audio-toggle-btn { background: #FFFFFF; border: 2.5px solid var(--primary); color: var(--primary-dark); font-weight: 800; font-size: 13px; padding: 8px 14px; border-radius: 50px; cursor: pointer; display: flex; align-items: center; gap: 6px; box-shadow: var(--shadow-sm); }
    .audio-toggle-btn.muted { background: #FEE2E2; border-color: #EF4444; color: #991B1B; }

    .page-nav { display: flex; justify-content: center; gap: 8px; background: #F0F9FF; padding: 6px; border-radius: var(--radius-lg); margin: 0 12px; border: 2px solid #BAE6FD; flex-wrap: wrap; }
    .nav-tab-btn { flex: 1; min-width: 95px; max-width: 180px; padding: 12px 8px; border: none; border-radius: var(--radius-md); font-weight: 800; font-size: 13px; cursor: pointer; background: transparent; color: var(--text-muted); display: flex; align-items: center; justify-content: center; gap: 6px; }
    .nav-tab-btn.active { background: var(--primary); color: #FFFFFF; box-shadow: 0 4px 12px rgba(59, 130, 246, 0.35); }
    .nav-tab-btn.vip-tab { background: #FEF3C7; color: #92400E; border: 2px solid #FCD34D; }
    .nav-tab-btn.vip-tab.active { background: linear-gradient(135deg, #F59E0B, #D97706); color: #FFF; box-shadow: 0 4px 12px rgba(245, 158, 11, 0.4); border-color: transparent; }
    .nav-tab-btn.tea-tab { background: #E0F2FE; color: var(--tea-blue); border: 2px solid #7DD3FC; }
    .nav-tab-btn.tea-tab.active { background: var(--tea-blue); color: #FFF; box-shadow: 0 4px 12px rgba(2, 132, 199, 0.35); border-color: transparent; }

    .browser-notice-box { margin: 0 16px; background: #EFF6FF; border: 2px solid #93C5FD; border-radius: var(--radius-md); padding: 10px 14px; text-align: center; color: #1E40AF; font-size: 12.5px; font-weight: 700; box-shadow: var(--shadow-sm); display: flex; align-items: center; justify-content: center; gap: 8px; }
    .top-vip-announcement { margin: 0 12px -10px; background: linear-gradient(135deg, #FEF3C7 0%, #FDE68A 100%); border: 2px dashed #F59E0B; border-radius: var(--radius-md); padding: 10px 14px; text-align: center; color: #92400E; font-size: 12px; font-weight: 800; cursor: pointer; box-shadow: var(--shadow-sm); }

    .page-content { display: none; flex-direction: column; gap: 22px; animation: fadeIn 0.3s ease; }
    .page-content.active-page { display: flex; }
    @keyframes fadeIn { from { opacity: 0; transform: translateY(6px); } to { opacity: 1; transform: translateY(0); } }

    .banner-intro-grid { display: flex; flex-direction: column; gap: 16px; padding: 0 16px; }
    @media (min-width: 850px) { .banner-intro-grid { display: grid; grid-template-columns: 1fr 1.2fr; align-items: stretch; } }
    .banner-container { width: 100%; border-radius: var(--radius-lg); overflow: hidden; box-shadow: var(--shadow-md); }
    .banner-img { width: 100%; height: 100%; min-height: 190px; display: block; object-fit: cover; }

    .intro-box { width: 100%; background: linear-gradient(135deg, #FEF3C7 0%, #FFFBEB 100%); border: 2.5px solid #FCD34D; border-radius: var(--radius-lg); padding: 20px; text-align: left; display: flex; flex-direction: column; justify-content: center; box-shadow: var(--shadow-sm); }
    .intro-box-header { display: flex; align-items: center; justify-content: space-between; margin-bottom: 10px; }
    .intro-box h2 { font-size: 18px; font-weight: 900; color: #92400E; }
    .intro-box p { font-size: 13px; color: #78350F; line-height: 1.6; font-weight: 600; margin-bottom: 8px; }

    .btn-audio-mini { background: linear-gradient(135deg, #FBBF24, #F59E0B); border: none; border-radius: 50%; width: 36px; height: 36px; cursor: pointer; font-size: 16px; display: flex; align-items: center; justify-content: center; color: #FFF; box-shadow: 0 4px 10px rgba(245, 158, 11, 0.35); flex-shrink: 0; }

    .social-round-section { padding: 0 16px; display: flex; justify-content: center; align-items: center; gap: 10px; flex-wrap: wrap; }
    .social-round-btn { width: 44px; height: 44px; border-radius: 50%; background: #FFF; border: 2.5px solid #E2E8F0; display: flex; align-items: center; justify-content: center; text-decoration: none; box-shadow: var(--shadow-sm); }
    .social-round-btn img { width: 24px; height: 24px; object-fit: contain; }

    .section-family-container { padding: 0 16px; display: flex; flex-direction: column; gap: 24px; }
    .family-group-title { font-size: 18px; font-weight: 900; color: var(--primary-dark); margin-bottom: 12px; display: flex; align-items: center; justify-content: space-between; }
    
    .floating-cards-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr)); gap: 14px; }
    @media (min-width: 900px) { .floating-cards-grid { grid-template-columns: repeat(4, 1fr); } }
    .floating-char-card { background: #FFFFFF; border-radius: var(--radius-lg); padding: 16px 12px; text-align: center; border: 3px solid #E2E8F0; box-shadow: var(--shadow-sm); display: flex; flex-direction: column; align-items: center; gap: 8px; cursor: pointer; }
    .floating-char-img { width: 85px; height: 85px; object-fit: contain; border-radius: 50%; background: #F8FAFC; padding: 4px; }
    .floating-char-name { font-size: 16px; font-weight: 900; color: var(--text-main); }
    .floating-char-tag { font-size: 10px; font-weight: 800; padding: 3px 10px; border-radius: 20px; text-transform: uppercase; }
    .floating-char-desc { font-size: 12px; font-weight: 600; color: var(--text-muted); line-height: 1.4; }

    .card-f1 { border-color: #F472B6; } .card-f1 .floating-char-tag { background: #FCE7F3; color: #DB2777; }
    .card-f2 { border-color: #60A5FA; } .card-f2 .floating-char-tag { background: #DBEAFE; color: #2563EB; }
    .card-avos { border-color: #FBBF24; } .card-avos .floating-char-tag { background: #FEF3C7; color: #D97706; }
    .card-especial { border-color: #A78BFA; } .card-especial .floating-char-tag { background: #EDE9FE; color: #7C3AED; }

    .char-details-box { margin: 0 16px; background: linear-gradient(135deg, #EFF6FF 0%, #FFFFFF 100%); border: 2.5px solid var(--primary); border-radius: var(--radius-lg); padding: 18px; text-align: center; }

    /* JOGOS & SUBNAV (AMOSTRAS VIP INCLUSAS) */
    .games-subnav { display: flex; justify-content: center; gap: 6px; background: #E0F2FE; padding: 6px; border-radius: var(--radius-md); margin-bottom: 14px; flex-wrap: wrap; }
    .subnav-btn { padding: 10px 12px; border: none; border-radius: 10px; font-weight: 800; font-size: 12px; cursor: pointer; background: #FFF; color: var(--primary-dark); box-shadow: 0 2px 6px rgba(0,0,0,0.04); }
    .subnav-btn.active { background: var(--primary); color: #FFF; }
    .subnav-btn.vip-preview-btn { background: #FEF3C7; color: #92400E; border: 2px solid #FCD34D; }
    .subnav-btn.vip-preview-btn.active { background: #F59E0B; color: #FFF; }

    .game-section-page { display: none; } 
    .game-section-page.active-game-page { display: block; }

    .age-group-section { margin: 0 16px; background: #FFFFFF; border-radius: var(--radius-lg); padding: 18px; border: 2px solid #E2E8F0; box-shadow: var(--shadow-sm); }
    .age-title { font-size: 19px; font-weight: 900; color: var(--primary-dark); margin-bottom: 14px; display: flex; align-items: center; justify-content: space-between; }
    
    .interactive-card { background: #F8FAFC; border-radius: var(--radius-md); padding: 16px; text-align: center; border: 2px solid #E2E8F0; display: flex; flex-direction: column; align-items: center; position: relative; }
    .conquistas-box { background: linear-gradient(135deg, #FEF3C7 0%, #FFFBEB 100%); border: 2px solid #FCD34D; border-radius: var(--radius-md); padding: 12px 16px; margin-bottom: 16px; display: flex; align-items: center; justify-content: space-between; font-weight: 800; color: #92400E; font-size: 13.5px; box-shadow: var(--shadow-sm); }

    /* Lousa Mágica Proporcional */
    .coloring-select-grid { display: none; justify-content: center; gap: 6px; margin-bottom: 12px; flex-wrap: wrap; }
    .coloring-select-grid.active { display: flex; }
    .btn-color-draw { background: #FFF; border: 2px solid #CBD5E1; padding: 6px 10px; border-radius: 10px; font-weight: 700; font-size: 11px; cursor: pointer; display: flex; align-items: center; gap: 6px; }
    .btn-color-draw.selected { border-color: var(--primary); background: #E0F2FE; }
    .btn-color-draw img { width: 22px; height: 22px; object-fit: contain; }
    .lousa-controls-bar { display: flex; align-items: center; justify-content: center; gap: 12px; background: #E0F2FE; padding: 8px 12px; border-radius: 12px; margin-bottom: 12px; flex-wrap: wrap; width: 100%; }
    .lousa-controls-bar label { font-size: 12px; font-weight: 800; color: var(--primary-dark); display: flex; align-items: center; gap: 6px; }
    .lousa-container { width: 100%; display: flex; flex-direction: column; align-items: center; position: relative; }
    #paintCanvas { background: #FFF; border: 3px solid var(--primary); border-radius: var(--radius-lg); width: 100%; max-width: 600px; height: 320px; touch-action: none; cursor: crosshair; }
    .palette { display: flex; gap: 8px; justify-content: center; align-items: center; margin-top: 12px; flex-wrap: wrap; width: 100%; }
    .color-dot { width: 34px; height: 34px; border-radius: 50%; border: 3px solid #FFF; box-shadow: 0 2px 6px rgba(0,0,0,0.2); cursor: pointer; }

    .game-btn-grid { display: flex; justify-content: center; gap: 8px; flex-wrap: wrap; margin-top: 12px; }
    .btn-choice { background: var(--purple); color: #FFF; border: none; padding: 10px 18px; font-weight: 800; font-size: 14px; border-radius: 12px; cursor: pointer; box-shadow: 0 3px 10px rgba(139, 92, 246, 0.3); transition: all 0.2s ease; }
    .btn-choice:active { transform: scale(0.92); }
    .btn-choice.acertou { background: #10B981 !important; transform: scale(1.1); box-shadow: 0 0 15px rgba(16, 185, 129, 0.6); }
    .btn-choice.errou { background: #EF4444 !important; transform: scale(0.95); }

    .memory-board { display: grid; grid-template-columns: repeat(4, 1fr); gap: 8px; margin-top: 12px; max-width: 320px; margin-left: auto; margin-right: auto; }
    .memory-card { aspect-ratio: 1; background: var(--primary); border-radius: 12px; display: flex; align-items: center; justify-content: center; color: #FFF; font-weight: 900; font-size: 20px; cursor: pointer; transition: transform 0.2s; }
    .memory-card:active { transform: scale(0.95); }
    .memory-card.flipped { background: #FFF; border: 2.5px solid var(--primary); }
    .memory-card img { width: 80%; height: 80%; object-fit: contain; }

    /* ESTILOS VIP */
    .vip-lock-container { background: linear-gradient(135deg, #FFFBEB 0%, #FEF3C7 100%); border: 3px solid #FCD34D; border-radius: var(--radius-lg); padding: 22px 16px; text-align: center; box-shadow: var(--shadow-sm); }
    .vip-lock-header-clickable { cursor: pointer; user-select: none; }
    .vip-price-tag { display: inline-block; background: #F59E0B; color: #FFF; font-weight: 900; font-size: 14px; padding: 8px 20px; border-radius: 30px; margin-bottom: 12px; }
    .vip-heart-msg { background: #FFFFFF; border: 2px dashed #F59E0B; border-radius: var(--radius-md); padding: 14px; margin: 12px auto; max-width: 700px; color: #78350F; font-size: 13px; line-height: 1.5; font-weight: 600; text-align: left; }
    .vip-grid-forms { display: grid; grid-template-columns: 1fr; gap: 16px; max-width: 700px; margin: 16px auto 0; }
    @media (min-width: 650px) { .vip-grid-forms { grid-template-columns: 1fr 1fr; } }
    .vip-form-box { background: #FFF; padding: 16px; border-radius: var(--radius-md); border: 2px solid #FCD34D; text-align: left; }
    .vip-form-box h4 { font-size: 15px; color: #92400E; margin-bottom: 10px; font-weight: 900; }
    .vip-input { width: 100%; padding: 10px; font-size: 13px; border: 2px solid #E2E8F0; border-radius: 10px; margin-bottom: 10px; outline: none; }
    .btn-vip-checkout { background: linear-gradient(135deg, #F59E0B 0%, #D97706 100%); color: #FFF; font-weight: 800; font-size: 14px; padding: 12px 16px; border-radius: 12px; border: none; cursor: pointer; width: 100%; text-decoration: none; display: block; text-align: center; }

    .vip-content-unlocked { display: none; flex-direction: column; gap: 16px; }
    .vip-content-unlocked.active-vip { display: flex; }
    .vip-card-box { background: #FFF; border: 2px solid #E2E8F0; border-radius: var(--radius-lg); padding: 16px; box-shadow: var(--shadow-sm); }

    .drive-banner-box { background: linear-gradient(135deg, #E0F2FE 0%, #DBEAFE 100%); border: 2.5px solid #3B82F6; border-radius: var(--radius-md); padding: 16px; text-align: center; margin-bottom: 16px; }
    .btn-drive { display: inline-block; background: #2563EB; color: #FFF; font-weight: 800; font-size: 13px; padding: 10px 20px; border-radius: 10px; text-decoration: none; margin-top: 8px; transition: transform 0.2s;}
    .btn-drive:hover { transform: scale(1.05); }

    .vip-internal-tabs { display: flex; justify-content: center; gap: 8px; margin-bottom: 16px; flex-wrap: wrap; background: #FFFBEB; padding: 8px; border-radius: var(--radius-lg); border: 2px solid #FCD34D;}
    .vip-int-btn { flex: 1; min-width: 140px; padding: 10px 14px; border-radius: 10px; border: 2px solid transparent; font-weight: 900; font-size: 14px; cursor: pointer; background: transparent; color: #92400E; transition: all 0.2s; }
    .vip-int-btn.active { background: #F59E0B; color: #FFF; box-shadow: 0 4px 10px rgba(245, 158, 11, 0.3); border-color: #D97706; }
    
    .vip-sub-area { display: none; flex-direction: column; gap: 16px; animation: fadeIn 0.3s ease; }
    .vip-sub-area.active-area { display: flex; }

    .rotina-item { display: flex; justify-content: space-between; align-items: center; background: #FFF; border: 2px solid #E2E8F0; padding: 10px 14px; border-radius: 10px; margin-bottom: 8px; transition: all 0.2s; }
    .rotina-item.concluido { background: #DCFCE7; border-color: #86EFAC; opacity: 0.8; }
    .rotina-item.concluido .rotina-texto { text-decoration: line-through; color: #166534; }
    .btn-concluir-rotina { background: #10B981; color: #FFF; border: none; padding: 6px 12px; border-radius: 8px; font-weight: 800; font-size: 12px; cursor: pointer; }
    .btn-remover-rotina { background: #EF4444; color: #FFF; border: none; padding: 6px 10px; border-radius: 8px; font-weight: 800; font-size: 12px; cursor: pointer; }

    .certificado-container { background: linear-gradient(135deg, #FFFBEB, #FEF3C7); border: 4px double #F59E0B; border-radius: 12px; padding: 20px; text-align: center; position: relative; }
    .certificado-container h3 { font-family: 'Georgia', serif; font-size: 22px; color: #92400E; margin-bottom: 10px; }
    .certificado-nome { font-size: 26px; font-weight: 900; color: var(--primary-dark); text-transform: uppercase; margin: 15px 0; border-bottom: 2px solid #92400E; display: inline-block; min-width: 200px; }
    
    .radio-vip-box { background: #1E293B; border-radius: var(--radius-lg); padding: 20px; text-align: center; color: #FFF; position: relative; overflow: hidden; }
    .radio-vip-box::before { content: ''; position: absolute; top: -50%; left: -50%; width: 200%; height: 200%; background: radial-gradient(circle, rgba(139, 92, 246, 0.2) 0%, transparent 70%); animation: pulse 4s infinite; z-index: 0; pointer-events: none; }
    @keyframes pulse { 0% { transform: scale(0.9); } 50% { transform: scale(1.1); } 100% { transform: scale(0.9); } }
    .radio-btn { background: #10B981; color: #FFF; border: none; padding: 12px 24px; border-radius: 30px; font-weight: 900; font-size: 16px; cursor: pointer; z-index: 1; position: relative; display: inline-flex; align-items: center; gap: 8px; text-decoration: none; box-shadow: 0 4px 15px rgba(16, 185, 129, 0.4); }

    .acalento-grid { display: flex; gap: 10px; justify-content: center; flex-wrap: wrap; margin-top: 15px; }
    .acalento-btn { background: #FFF; border: 2.5px solid var(--tea-blue); border-radius: 12px; width: 95px; padding: 12px 6px; display: flex; flex-direction: column; justify-content: center; align-items: center; cursor: pointer; transition: transform 0.2s, background 0.2s; }
    .acalento-btn:hover { background: var(--tea-light); transform: scale(1.05); }
    .acalento-btn span { font-size: 28px; }
    .acalento-btn p { font-size: 11px; font-weight: 800; color: var(--tea-blue); margin: 6px 0 0 0; text-align: center; }

    .perfil-selector-box { background: #F8FAFC; border: 2px solid #CBD5E1; border-radius: var(--radius-md); padding: 14px; text-align: center; }
    .avatar-escolha-grid { display: flex; justify-content: center; gap: 8px; flex-wrap: wrap; margin-top: 8px; }
    .avatar-escolha-btn { width: 48px; height: 48px; border-radius: 50%; border: 2.5px solid #CBD5E1; cursor: pointer; object-fit: contain; background: #FFF; padding: 3px; }
    .avatar-escolha-btn.selecionado { border-color: #F59E0B; transform: scale(1.08); box-shadow: 0 4px 10px rgba(245,158,11,0.4); }

    .video-section { padding: 0 16px; }
    .video-card { background: #FFFFFF; border-radius: var(--radius-lg); padding: 18px; box-shadow: var(--shadow-sm); border: 2px solid #E2E8F0; text-align: center; margin-bottom: 14px; }
    .video-header { display: flex; align-items: center; justify-content: space-between; margin-bottom: 12px; }
    .video-header h3 { font-size: 17px; font-weight: 900; color: var(--primary-dark); }
    .video-wrapper { position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; border-radius: var(--radius-md); }
    .video-wrapper iframe { position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0; }

    .support-form-box { background: #FFFBEB; border: 2px solid #FCD34D; border-radius: var(--radius-lg); padding: 18px; margin: 0 16px 20px; box-shadow: var(--shadow-sm); }
    .support-form-box h5 { color: #92400E; font-size: 16px; font-weight: 900; margin-bottom: 6px; }
    .support-form-box p { font-size: 12.5px; color: #78350F; margin-bottom: 12px; font-weight: 600; }
    .support-input, .support-textarea { width: 100%; padding: 10px 14px; border: 2px solid #FCD34D; border-radius: 10px; font-size: 13px; margin-bottom: 10px; background: #FFF; outline: none; }
    .support-textarea { resize: vertical; min-height: 80px; }
    .support-btn { background: #D97706; color: #FFF; border: none; padding: 12px 18px; border-radius: 10px; font-weight: 800; font-size: 14px; cursor: pointer; width: 100%; }

    #visualToast { position: fixed; bottom: 15px; left: 50%; transform: translateX(-50%) translateY(100px); background: #0F172A; color: #FFF; padding: 10px 20px; border-radius: 30px; font-size: 12px; font-weight: 700; box-shadow: 0 8px 20px rgba(0,0,0,0.2); transition: transform 0.3s ease; z-index: 99999; pointer-events: none; }
    #visualToast.show { transform: translateX(-50%) translateY(0); }
    .floating-vip-badge { position: fixed; bottom: 16px; right: 16px; background: linear-gradient(135deg, #F59E0B 0%, #D97706 100%); color: #FFF; padding: 10px 16px; border-radius: 50px; font-size: 12.5px; font-weight: 800; box-shadow: 0 6px 18px rgba(245, 158, 11, 0.4); display: flex; align-items: center; gap: 6px; cursor: pointer; border: 2px solid #FDE68A; z-index: 9999; }
    
    footer { text-align: center; padding: 16px 16px 20px; border-top: 1px solid #E2E8F0; font-size: 12px; color: var(--text-muted); font-weight: 600; margin-top: 20px; display: flex; flex-direction: column; gap: 8px;}
    footer a { color: var(--primary); text-decoration: underline; cursor: pointer; }
    
    .tea-box { background: var(--tea-light); border: 2px solid #BAE6FD; border-radius: var(--radius-lg); padding: 20px; text-align: center; margin-bottom: 20px; }
    .tea-box h3 { color: var(--tea-blue); font-weight: 900; margin-bottom: 10px; }
    .btn-sensorial { background: #FFF; color: var(--tea-blue); border: 2px solid var(--tea-blue); padding: 10px 20px; border-radius: 20px; font-weight: 800; cursor: pointer; display: inline-flex; align-items: center; gap: 8px; margin-top: 10px; transition: all 0.3s; }
    .btn-sensorial.ativo { background: var(--tea-blue); color: #FFF; }
    .emotion-card { background: #FFF; border: 2px solid #E2E8F0; border-radius: 12px; padding: 15px; cursor: pointer; width: 100px; display: flex; flex-direction: column; align-items: center; justify-content: center; transition: transform 0.2s;}
    .emotion-card:hover { border-color: var(--tea-blue); transform: scale(1.05); }
    .emotion-card img { width: 50px; height: 50px; object-fit: contain; margin-bottom: 10px; }
    
    .fade-transition { opacity: 1; transition: opacity 0.8s ease-in-out; }
    .fade-out { opacity: 0; }

    .caa-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; margin-top: 15px; }
    .caa-btn { background: #FFF; border: 2px solid #BAE6FD; border-radius: 12px; padding: 10px; text-align: center; cursor: pointer; transition: all 0.2s; }
    .caa-btn:active { background: #E0F2FE; border-color: var(--tea-blue); transform: scale(0.95); }
    .caa-btn span { display: block; font-size: 28px; margin-bottom: 5px; }
    .caa-btn p { font-size: 11px; font-weight: 800; color: var(--tea-blue); margin: 0; }

    .timer-bar-bg { width: 100%; height: 24px; background: #E2E8F0; border-radius: 12px; overflow: hidden; margin: 15px 0; border: 2px solid #CBD5E1; }
    .timer-bar-fill { width: 100%; height: 100%; background: #10B981; transition: width 1s linear, background-color 0.5s ease; }
    .timer-btns { display: flex; justify-content: center; gap: 8px; flex-wrap: wrap; }
    .timer-btn { background: var(--tea-blue); color: #FFF; border: none; padding: 8px 12px; border-radius: 8px; font-weight: 800; font-size: 12px; cursor: pointer; }

    .lock-modal { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(15, 23, 42, 0.9); z-index: 99999; justify-content: center; align-items: center; padding: 16px; backdrop-filter: blur(6px); }
    .lock-modal.active { display: flex; }
    .lock-box { background: #FFF; padding: 24px; border-radius: var(--radius-lg); text-align: center; max-width: 350px; width: 100%; border: 3px solid #EF4444; }
    .lock-box h3 { color: #991B1B; margin-bottom: 10px; font-weight: 900; }
    .lock-box p { font-size: 12px; color: #475569; margin-bottom: 15px; font-weight: 600; }
    .lock-input { width: 100%; padding: 10px; font-size: 14px; border: 2px solid #CBD5E1; border-radius: 8px; margin-bottom: 12px; text-align: center; outline: none; }
    .lock-btn { background: #EF4444; color: #FFF; border: none; padding: 10px; width: 100%; border-radius: 8px; font-weight: 800; cursor: pointer; }

    .modal-overlay { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(15, 23, 42, 0.6); z-index: 10000; justify-content: center; align-items: center; padding: 16px; backdrop-filter: blur(4px); }
    .modal-overlay.active { display: flex; }
    .modal-content { background: #FFF; width: 100%; max-width: 600px; border-radius: var(--radius-lg); padding: 24px; box-shadow: var(--shadow-lg); max-height: 85vh; overflow-y: auto; position: relative; }
    .modal-close { position: absolute; top: 16px; right: 16px; background: #F1F5F9; border: none; width: 32px; height: 32px; border-radius: 50%; font-weight: bold; cursor: pointer; color: #475569; }
    .modal-content h3 { color: var(--primary-dark); margin-bottom: 12px; font-weight: 900; }
    .modal-content p { font-size: 13px; color: var(--text-muted); line-height: 1.6; margin-bottom: 10px; font-weight: 500; }

    .cookie-banner { position: fixed; bottom: 0; left: 0; width: 100%; background: #1E293B; color: #FFF; padding: 16px; text-align: center; font-size: 13px; z-index: 100000; display: flex; justify-content: center; align-items: center; gap: 16px; flex-wrap: wrap; transform: translateY(100%); transition: transform 0.4s ease; box-shadow: 0 -4px 10px rgba(0,0,0,0.1); }
    .cookie-banner.show { transform: translateY(0); }
    .btn-cookie { background: #10B981; color: #FFF; border: none; padding: 8px 16px; border-radius: 8px; font-weight: 800; cursor: pointer; }
  </style>
</head>
<body onclick="desbloquearAudioMobileOnce()">

  <div id="visualToast">Aviso do sistema</div>

  <!-- MODAL DE BLOQUEIO POR SENHA (TEMPO ESGOTADO) -->
  <div id="modalBloqueioTempo" class="lock-modal">
    <div class="lock-box">
      <h3>⏰ O Tempo de Uso Acabou!</h3>
      <p>Para desbloquear o portal e voltar a brincar, insira a <strong>senha parental</strong> cadastrada:</p>
      <input type="password" id="senhaDesbloqueio" class="lock-input" placeholder="Digite a senha">
      <button class="lock-btn" onclick="tentarDesbloquearTela()">Desbloquear com Senha 🔓</button>
    </div>
  </div>

  <!-- Banner de Cookies LGPD -->
  <div id="cookieBanner" class="cookie-banner">
    <p style="margin:0;">🍪 A Turminha do Xexéu utiliza cookies (salvos no seu aparelho) para salvar seu progresso. <a onclick="abrirPrivacidade()" style="color:#3B82F6; text-decoration:underline; cursor:pointer;">Saiba mais</a>.</p>
    <button class="btn-cookie" onclick="aceitarCookies()">Entendi e Aceito!</button>
  </div>

  <!-- Modal Política de Privacidade -->
  <div class="modal-overlay" id="modalPrivacidade">
    <div class="modal-content">
      <button class="modal-close" onclick="fecharPrivacidade()">X</button>
      <h3>🔒 Política de Privacidade da Turminha</h3>
      <p>A <strong>Turminha do Xexéu</strong> (eve Design) tem um compromisso absoluto com a segurança e a privacidade da sua família, em conformidade com a LGPD.</p>
      <p><strong>1. Dados Locais e Seguros:</strong> O portal utiliza armazenamento local (Local Storage). Suas pontuações, avatares e rotinas ficam salvas <strong>exclusivamente no seu celular ou computador</strong>.</p>
      <p><strong>2. Área VIP:</strong> Os dados cadastrados são utilizados exclusivamente para autenticação no Clube VIP.</p>
      <p>Dúvidas? Envie um e-mail para: turminhaxexeu@gmail.com</p>
    </div>
  </div>

  <div class="floating-vip-badge" onclick="mudarPagina('vip')">
    <span>⭐</span>
    <span>Seja VIP (R$ 6,00)</span>
  </div>

  <div class="app-container">

    <header>
      <a href="https://www.youtube.com/@turminhaxe_xeu" target="_blank" title="YouTube da Turminha">
        <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908275/TURMINHA_LOGO.png" alt="Logo Turminha do Xexéu" class="logo-img">
      </a>
      <div style="display:flex; align-items:center; gap:8px;">
        <button id="btnSensoryHeader" class="btn-sensorial" style="padding: 6px 12px; font-size:11px;" onclick="toggleSensoryMode()">
          <span>🌿</span> Modo Calmo
        </button>
        <button id="toggleAudioBtn" class="audio-toggle-btn" onclick="alternarAudioGlobal()">
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
      <button id="btn-tab-vip" class="nav-tab-btn vip-tab" onclick="mudarPagina('vip')">⭐ Área VIP</button>
    </nav>

    <div class="browser-notice-box">
      <span>💡 Dica: Se o som estiver mudo, toque nos 3 pontinhos e escolha <strong>"Abrir no Chrome"</strong> ou <strong>"Abrir no Safari"</strong>!</span>
    </div>

    <div class="top-vip-announcement" onclick="mudarPagina('vip')">
      <span>⭐ Desbloqueie todo o Drive de Atividades e Ferramentas TEA por R$ 6,00/mês! Clique Aqui! 💖</span>
    </div>

    <!-- PÁGINA INÍCIO -->
    <main id="pagina-inicio" class="page-content active-page">
      <section class="banner-intro-grid">
        <div class="banner-container">
          <a href="https://www.youtube.com/@turminhaxe_xeu" target="_blank">
            <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786906934/Banner_para_youtube_streamer_de_jogos_rosa_feminino_e_delicado.png" alt="Capa da Turminha do Xexéu" class="banner-img">
          </a>
        </div>
        <div class="intro-box">
          <div class="intro-box-header">
            <h2>✨ Educando com Alegria e Amor</h2>
            <button class="btn-audio-mini" onclick="lerTexto('Mais do que um nome divertido, a Turminha do Xexéu é o nosso jeito de honrar as raízes e a história da nossa família.')" title="Ouvir">🔊</button>
          </div>
          <p>Mais do que um nome divertido, a <strong>Turminha do Xexéu</strong> é o nosso jeito de honrar as raízes e a história da nossa família.</p>
          <p>O nome <strong>Xexéu</strong> é uma homenagem que atravessa gerações. Ele honra a memória de <em>Mariano Xexéu</em> e celebra a vida de seu filho, <em>Pedro Mariano</em>, grande inspiração para o nosso querido <strong>Vovô Beto</strong>.</p>
          <p>A <strong>Vovó Hilda</strong> é inspirada na inesquecível <em>Astrogilda Grispym</em>, representando o amor que não conhece o tempo.</p>
        </div>
      </section>

      <section class="social-round-section">
        <a href="https://www.youtube.com/@turminhaxe_xeu" target="_blank" class="social-round-btn" title="YouTube"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908275/YT.png" alt="YouTube"></a>
        <a href="https://www.instagram.com/turminhaxe_xeu" target="_blank" class="social-round-btn" title="Instagram"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908273/INDTAGRAM.png" alt="Instagram"></a>
        <a href="https://www.tiktok.com/@turminhaxe_xeu" target="_blank" class="social-round-btn" title="TikTok"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908275/TIKTOK.png" alt="TikTok"></a>
        <a href="https://open.spotify.com/intl-pt/artist/6ykKQ3uP6Wl2REylKJAdJ6" target="_blank" class="social-round-btn" title="Spotify"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908274/SPOTIFY.png" alt="Spotify"></a>
        <a href="https://music.youtube.com/channel/UC8KOg4IH-h0YNrpKlfIl2Vw" target="_blank" class="social-round-btn" title="YouTube Music"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908275/YT_MUSIC.png" alt="YouTube Music"></a>
        <a href="https://www.facebook.com/profile.php?id=61585431586796" target="_blank" class="social-round-btn" title="Facebook"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908273/FACEBOOK.png" alt="Facebook"></a>
        <a href="https://www.threads.net/@turminhaxe_xeu" target="_blank" class="social-round-btn" title="Threads"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786908274/THRENDS.png" alt="Threads"></a>
      </section>

      <section class="section-family-container">
        <div>
          <h3 class="family-group-title">
            ✨ O Símbolo e Mascote
            <button class="btn-audio-mini" style="width:30px; height:30px; font-size:14px;" onclick="lerTexto('O Símbolo e Mascote da Turminha do Xexéu.')">🔊</button>
          </h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-especial" onclick="tocarVozETexto('Xexéu')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786902347/xexeu.png" class="floating-char-img" alt="Xexéu">
              <span class="floating-char-name">Xexéu</span>
              <span class="floating-char-tag">Mascote Oficial</span>
              <p class="floating-char-desc">Inspirado no pássaro xexéu e no nome do bisavô Mariano Xexéu. É o espírito alegre e o guardião da nossa história!</p>
            </div>
            <div class="floating-char-card card-especial" onclick="tocarVozETexto('Capilé')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786902348/capile.png" class="floating-char-img" alt="Capilé">
              <span class="floating-char-name">Capilé</span>
              <span class="floating-char-tag">O Companheiro</span>
              <p class="floating-char-desc">Cachorrinho de orelhas grandes e coleira azul-celeste com pingente de osso dourado!</p>
            </div>
          </div>
        </div>

        <div>
          <h3 class="family-group-title">
            💖 A Casa da Maya e do Theo
            <button class="btn-audio-mini" style="width:30px; height:30px; font-size:14px;" onclick="lerTexto('A Casa da Maya e do Theo.')">🔊</button>
          </h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-f1" onclick="tocarVozETexto('Maya')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786907604/16.png" class="floating-char-img" alt="Maya">
              <span class="floating-char-name">Maya</span>
              <span class="floating-char-tag">Mãe & Guia</span>
              <p class="floating-char-desc">Mãe dedicada da Iza e da Nina. Extremamente organizada, atenciosa e porto seguro da família.</p>
            </div>
            <div class="floating-char-card card-f1" onclick="tocarVozETexto('Theo')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786907605/17.png" class="floating-char-img" alt="Theo">
              <span class="floating-char-name">Theo</span>
              <span class="floating-char-tag">Pai Protetor</span>
              <p class="floating-char-desc">Pai da Iza e da Nina. Calmo, observador e com um sorriso tranquilo para apoiar as meninas.</p>
            </div>
            <div class="floating-char-card card-f1" onclick="tocarVozETexto('Nina')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786903228/Sem_nome_512_x_512_px_1.png" class="floating-char-img" alt="Nina">
              <span class="floating-char-name">Nina</span>
              <span class="floating-char-tag">Super Esperta</span>
              <p class="floating-char-desc">Super esperta, tem cabelos cacheados e adora aprender coisas novas com os amigos!</p>
            </div>
            <div class="floating-char-card card-f1" onclick="tocarVozETexto('Iza')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786902350/iza.png" class="floating-char-img" alt="Iza">
              <span class="floating-char-name">Iza</span>
              <span class="floating-char-tag">A Vaidosa</span>
              <p class="floating-char-desc">Vestidinho rosa, cabelos ondulados e um jeitinho charmoso e doce por onde passa.</p>
            </div>
          </div>
        </div>

        <div>
          <h3 class="family-group-title">
            ⚡ A Casa do Sam e da Lia
            <button class="btn-audio-mini" style="width:30px; height:30px; font-size:14px;" onclick="lerTexto('A Casa do Sam e da Lia.')">🔊</button>
          </h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-f2" onclick="tocarVozETexto('Sam')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786907601/14.png" class="floating-char-img" alt="Sam">
              <span class="floating-char-name">Sam</span>
              <span class="floating-char-tag">Pai Inventor</span>
              <p class="floating-char-desc">Paizão ruivo do Joca e do Leo. Descontraído, adora construir brinquedos e invenções.</p>
            </div>
            <div class="floating-char-card card-f2" onclick="tocarVozETexto('Lia')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786907602/15.png" class="floating-char-img" alt="Lia">
              <span class="floating-char-name">Lia</span>
              <span class="floating-char-tag">Mãe Alegria</span>
              <p class="floating-char-desc">Mãe do Joca e do Leo. Estilosa e alegre, traz energia contagiante para o dia a dia.</p>
            </div>
            <div class="floating-char-card card-f2" onclick="tocarVozETexto('Joca')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786902350/joca.png" class="floating-char-img" alt="Joca">
              <span class="floating-char-name">Joca</span>
              <span class="floating-char-tag">O Divertido</span>
              <p class="floating-char-desc">Menino de camiseta verde! Engraçado e super companheiro em qualquer brincadeira.</p>
            </div>
            <div class="floating-char-card card-f2" onclick="tocarVozETexto('Leo')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786902347/leo.png" class="floating-char-img" alt="Leo">
              <span class="floating-char-name">Leo</span>
              <span class="floating-char-tag">Explorador Focado</span>
              <p class="floating-char-desc">Irmão do Joca. Amante de detalhes e focado em suas descobertas com muita imaginação.</p>
            </div>
          </div>
        </div>

        <div>
          <h3 class="family-group-title">
            👵👴 Os Avós
            <button class="btn-audio-mini" style="width:30px; height:30px; font-size:14px;" onclick="lerTexto('Os Avós da Turminha.')">🔊</button>
          </h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-avos" onclick="tocarVozETexto('Beto')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786902348/vovo_beto.png" class="floating-char-img" alt="Vovô Beto">
              <span class="floating-char-name">Vovô Beto</span>
              <span class="floating-char-tag">Vovô Coruja</span>
              <p class="floating-char-desc">Usa óculos quadrados. Inspirado no querido Pedro Mariano, traz paciência, bom humor e energia contagiante.</p>
            </div>
            <div class="floating-char-card card-avos" onclick="tocarVozETexto('Hilda')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786902347/vovo_hilda.png" class="floating-char-img" alt="Vovó Hilda">
              <span class="floating-char-name">Vovó Hilda</span>
              <span class="floating-char-tag">Vovó Acolhedora</span>
              <p class="floating-char-desc">Usa óculos redondos. Inspirada na inesquecível Astrogilda Grispym, guardando doçura, abraços e valores preciosos.</p>
            </div>
          </div>
        </div>
      </section>

      <section class="char-details-box" id="detalhes-personagem">
        <h3 id="detalhe-nome" style="color: var(--primary-dark); font-weight: 900; font-size: 16px;">Clique em um personagem acima para ouvir!</h3>
        <p id="detalhe-texto" style="font-weight: 600; color: var(--text-muted); margin-top: 4px; font-size: 13px;">A narração apresentará os amigos da Turminha para você!</p>
      </section>
      
      <section class="video-section">
        <div class="video-card">
          <div class="video-header">
            <h3>🎬 Episódios em Destaque</h3>
            <button class="btn-audio-mini" onclick="lerTexto('Assista aos episódios da Turminha do Xexéu!')" title="Ouvir">🔊</button>
          </div>
          <div class="video-wrapper">
            <iframe src="https://www.youtube-nocookie.com/embed/videosseries?list=PLh42qmbnReoE_pM4lig3DpJaNGWqoT9uJ" allowfullscreen></iframe>
          </div>
        </div>
      </section>
    </main>

    <!-- PÁGINA VÍDEOS -->
    <main id="pagina-videos" class="page-content">
      <section class="video-section">
        <div class="video-card">
          <div class="video-header">
            <h3>🎬 Canal Oficial - Playlist Completa</h3>
          </div>
          <div class="video-wrapper">
            <iframe src="https://www.youtube-nocookie.com/embed/videosseries?list=PLh42qmbnReoE_pM4lig3DpJaNGWqoT9uJ" allowfullscreen></iframe>
          </div>
        </div>
      </section>
    </main>

    <!-- PÁGINA JOGOS (COM AMOSTRAS VIP UNIFICADAS) -->
    <main id="pagina-jogos" class="page-content">
      <div class="age-group-section">
        <h3 class="age-title">
          🎮 Área de Jogos da Turminha
          <button class="btn-audio-mini" style="width:30px; height:30px; font-size:14px;" onclick="lerTexto('Bem-vindo à Área de Jogos da Turminha!')">🔊</button>
        </h3>
        
        <div class="conquistas-box">
          <span>🏆 Suas Conquistas: <strong id="placar-pontos">0</strong> pontos</span>
          <span id="medalha-status">⭐ Iniciante da Turminha</span>
        </div>

        <!-- TEMPORIZADOR GERAL (LIMITADO A 2 MIN NO GRÁTIS) -->
        <div class="interactive-card" style="border-color: #BAE6FD; margin-bottom: 16px; background: #F0F9FF;">
          <h4 style="color: var(--tea-blue); font-weight: 900; font-size: 14px; margin-bottom: 4px;">⏳ Temporizador de Uso</h4>
          <p style="font-size: 11px; color: #475569; font-weight: 600; margin-bottom: 8px;">Defina um limite de tempo (Grátis: até 2 min | VIP: até 30 min).</p>
          <div class="timer-btns" id="botoesTemporizadorGeral"></div>
          <div class="timer-bar-bg" style="margin: 8px 0;">
            <div id="barra-temporizador" class="timer-bar-fill" style="width: 100%;"></div>
          </div>
          <p id="texto-temporizador" style="font-weight: 900; color: #475569; font-size: 16px; margin:0; text-align:center;">0:00</p>
        </div>

        <nav class="games-subnav">
          <button id="subtab-lousa" class="subnav-btn active" onclick="mudarSubJogo('lousa')">🎨 Lousa Mágica</button>
          <button id="subtab-contar" class="subnav-btn" onclick="mudarSubJogo('contar')">🔢 Contar</button>
          <button id="subtab-letras" class="subnav-btn" onclick="mudarSubJogo('letras')">🔤 Letras</button>
          <button id="subtab-memoria" class="subnav-btn" onclick="mudarSubJogo('memoria')">🧠 Memória</button>
          <button id="subtab-quiz" class="subnav-btn" onclick="mudarSubJogo('quiz')">❓ Quiz</button>
          <!-- Amostras VIP aparecem na aba de jogos com indicação -->
          <button id="subtab-vip-historia" class="subnav-btn vip-preview-btn" onclick="mudarSubJogo('vip-historia')">🔒 📖 Histórias VIP</button>
          <button id="subtab-vip-cor" class="subnav-btn vip-preview-btn" onclick="mudarSubJogo('vip-cor')">🔒 🎨 Cores VIP</button>
        </nav>

        <!-- 1. LOUSA MÁGICA -->
        <div id="game-lousa" class="game-section-page active-game-page interactive-card lousa-container">
          <h4 style="font-weight: 800; margin-bottom: 10px; font-size: 17px;">🎨 Lousa Mágica & Desenhos</h4>
          <div class="lousa-mode-tabs" style="margin-bottom:10px;">
            <button id="btn-mode-free" class="subnav-btn active" onclick="setLousaMode('free')">✏️ Livre</button>
            <button id="btn-mode-color" class="subnav-btn" onclick="setLousaMode('color')">🖼️ Pintar</button>
          </div>
          <div id="coloringSelectGrid" class="coloring-select-grid">
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786904227/12.png', 'Xexéu', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786902347/xexeu.png" alt="Xexéu"> Xexéu</button>
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786904227/11.png', 'Capilé', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786902348/capile.png" alt="Capilé"> Capilé</button>
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786904225/7.png', 'Maya', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786907604/16.png" alt="Maya"> Maya</button>
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786904225/8.png', 'Theo', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786907605/17.png" alt="Theo"> Theo</button>
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786904227/10.png', 'Nina', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786903228/Sem_nome_512_x_512_px_1.png" alt="Nina"> Nina</button>
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786904225/9.png', 'Iza', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786902350/iza.png" alt="Iza"> Iza</button>
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786904223/3.png', 'Sam', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786907601/14.png" alt="Sam"> Sam</button>
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786904223/4.png', 'Lia', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786907602/15.png" alt="Lia"> Lia</button>
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786904223/6.png', 'Joca', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786902350/joca.png" alt="Joca"> Joca</button>
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786904223/5.png', 'Leo', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786902347/leo.png" alt="Leo"> Leo</button>
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786904221/2.png', 'Beto', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786902348/vovo_beto.png" alt="Beto"> Beto</button>
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786904221/1.png', 'Hilda', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786902347/vovo_hilda.png" alt="Hilda"> Hilda</button>
          </div>
          <div class="lousa-controls-bar">
            <label>🖌️ Pincel: <input type="range" id="brushSizeInput" min="2" max="22" value="6" onchange="mudarTamanhoPincel(this.value)"></label>
            <label>🔍 Zoom: <input type="range" id="zoomScaleInput" min="50" max="100" value="85" onchange="mudarZoomGuia(this.value)"></label>
          </div>
          <canvas id="paintCanvas"></canvas>
          <div class="palette">
            <div class="color-dot" style="background: #3B82F6;" onclick="mudarCor('#3B82F6')"></div>
            <div class="color-dot" style="background: #EF4444;" onclick="mudarCor('#EF4444')"></div>
            <div class="color-dot" style="background: #10B981;" onclick="mudarCor('#10B981')"></div>
            <div class="color-dot" style="background: #F59E0B;" onclick="mudarCor('#F59E0B')"></div>
            <div class="color-dot" style="background: #8B5CF6;" onclick="mudarCor('#8B5CF6')"></div>
            <div class="color-dot" style="background: #000000;" onclick="mudarCor('#000000')"></div>
            <input type="color" id="colorPicker" onchange="mudarCor(this.value)" style="width: 34px; height: 34px; border:none; cursor:pointer; background:none;">
            <button onclick="limparCanvas()" style="padding: 8px 12px; font-weight: 800; border-radius: 8px; border: none; background: #FEE2E2; color: #DC2626; cursor: pointer; font-size: 12px;">Limpar 🗑️</button>
            <button onclick="salvarFotoDesenho()" style="padding: 8px 12px; font-weight: 800; border-radius: 8px; border: none; background: #D1FAE5; color: #065F46; cursor: pointer; font-size: 12px;">📸 Salvar</button>
          </div>
        </div>

        <!-- 2. VAMOS CONTAR -->
        <div id="game-contar" class="game-section-page interactive-card">
          <h4 style="font-weight: 800; font-size: 18px; margin-bottom: 6px;">🔢 Vamos Contar?</h4>
          <p style="font-size: 13.5px; color: var(--text-muted); margin-bottom: 14px;">Quantos amiguinhos aparecem abaixo?</p>
          <div id="countDisplay" style="display: flex; justify-content: center; align-items: center; gap: 8px; margin: 16px 0; min-height: 80px; flex-wrap: wrap;"></div>
          <div id="countOptions" class="game-btn-grid"></div>
        </div>

        <!-- 3. PRIMEIRAS LETRAS -->
        <div id="game-letras" class="game-section-page interactive-card">
          <h4 style="font-weight: 800; font-size: 18px; margin-bottom: 6px;">🔤 Qual é a Primeira Letra?</h4>
          <p style="font-size: 13.5px; font-weight: 700; margin-top: 4px;">Nome: <strong id="nome-letra-personagem" style="color: var(--purple); font-size: 17px;">Xexéu</strong></p>
          <img id="img-letra-personagem" src="" alt="Personagem" style="width: 100px; height: 100px; object-fit: contain; margin: 12px 0;">
          <div id="opcoes-letras" class="game-btn-grid"></div>
        </div>

        <!-- 4. JOGO DA MEMÓRIA -->
        <div id="game-memoria" class="game-section-page interactive-card">
          <h4 style="font-weight: 800; font-size: 18px; margin-bottom: 6px;">🧠 Jogo da Memória</h4>
          <p style="font-size: 13.5px; color: var(--text-muted); margin-bottom: 12px;">Encontre os 4 pares dos amigos!</p>
          <div id="memoryBoard" class="memory-board"></div>
        </div>

        <!-- 5. QUIZ -->
        <div id="game-quiz" class="game-section-page interactive-card" style="align-items: stretch;">
          <h4 style="font-weight: 800; margin-bottom: 14px; font-size: 18px; text-align: center;">❓ Desafios da Turminha</h4>
          <div style="display: flex; flex-direction: column; gap: 16px; max-width: 450px; margin: 0 auto; width: 100%;">
            <div style="background: #FFF; padding: 14px; border-radius: 12px; border: 2px solid #E2E8F0; text-align: center;">
              <p style="font-size: 13px; font-weight: 800; color: var(--primary-dark);">Quem é este personagem?</p>
              <img id="quiz-img" src="" alt="Quiz" style="width: 75px; height: 75px; object-fit: contain; margin: 8px 0;">
              <div id="quiz-options" style="display: flex; flex-direction: column; gap: 6px;"></div>
            </div>
          </div>
        </div>

        <!-- 6. JOGO VIP DE HISTÓRIAS (AMOSTRA NA ABA DE JOGOS) -->
        <div id="game-vip-historia" class="game-section-page interactive-card">
          <h4 style="font-weight: 800; margin-bottom: 10px; font-size: 18px; color: #92400E;">📖 Desafio das Histórias (Amostra VIP)</h4>
          <div id="avisoVipBlocoHistoria" style="padding: 20px; text-align: center;">
            <p style="font-size: 13px; color: #78350F; margin-bottom: 12px;">Este minijogo avançado é exclusivo para membros do Clube VIP. Torne-se assinante para liberar este e outros conteúdos!</p>
            <button onclick="mudarPagina('vip')" class="support-btn" style="background:#F59E0B; max-width:200px; margin:0 auto;">Quero Ser VIP ⭐</button>
          </div>
          <div id="conteudoVipHistoriaReal" style="display:none; width:100%;">
            <p id="vip-historia-txt" style="font-size: 14px; font-weight: 800; color: #78350F; margin-bottom: 14px;"></p>
            <div id="vip-historia-options" style="display: flex; flex-direction: column; gap: 8px; width: 100%; max-width: 380px; margin: 0 auto;"></div>
          </div>
        </div>

        <!-- 7. JOGO VIP DE CORES (AMOSTRA NA ABA DE JOGOS) -->
        <div id="game-vip-cor" class="game-section-page interactive-card">
          <h4 style="font-weight: 800; margin-bottom: 10px; font-size: 18px; color: #92400E;">🎨 Cores & Detalhes Secretos (Amostra VIP)</h4>
          <div id="avisoVipBlocoCor" style="padding: 20px; text-align: center;">
            <p style="font-size: 13px; color: #78350F; margin-bottom: 12px;">Desafio de cores exclusivo para assinantes VIP!</p>
            <button onclick="mudarPagina('vip')" class="support-btn" style="background:#F59E0B; max-width:200px; margin:0 auto;">Quero Ser VIP ⭐</button>
          </div>
          <div id="conteudoVipCorReal" style="display:none; width:100%;">
            <p id="vip-cor-txt" style="font-size: 14px; font-weight: 800; color: #78350F; margin-bottom: 8px;"></p>
            <img id="vip-cor-img" src="" alt="Detalhe VIP" style="width: 80px; height: 80px; object-fit: contain; margin-bottom: 10px;">
            <div id="vip-cor-options" style="display: flex; justify-content: center; gap: 8px; flex-wrap: wrap;"></div>
          </div>
        </div>

      </div>
    </main>

    <!-- PÁGINA ESPAÇO TEA -->
    <main id="pagina-tea" class="page-content">
      <div class="age-group-section">
        
        <div id="tea-onboarding-box" class="tea-box" style="background: #FFF; border: 2.5px solid var(--tea-blue);">
          <h3>🧩 Configure seu Espaço TEA</h3>
          <p style="font-size: 13px; color: #334155; font-weight: 600; margin-bottom: 15px;">Personalize a experiência com o nome da criança e crie sua senha parental para o temporizador:</p>
          
          <div style="max-width: 400px; margin: 0 auto; text-align: left;">
            <label style="font-size: 11px; font-weight: 800; color: var(--tea-blue); display: block; margin-bottom: 4px;">Nome da Criança ou Responsável:</label>
            <input type="text" id="tea-nome-crianca" class="vip-input" placeholder="Ex: Lucas">

            <label style="font-size: 11px; font-weight: 800; color: var(--tea-blue); display: block; margin-bottom: 4px;">E-mail de Contato:</label>
            <input type="email" id="tea-email" class="vip-input" placeholder="seu@email.com">
            
            <label style="font-size: 11px; font-weight: 800; color: var(--tea-blue); display: block; margin-bottom: 4px;">Senha Parental (para destravar o tempo):</label>
            <input type="password" id="tea-senha" class="vip-input" placeholder="Senha secreta">
            
            <button onclick="salvarOnboardingTea()" class="support-btn" style="background: var(--tea-blue); margin-top: 10px;">Salvar e Entrar no Espaço TEA 🚀</button>
          </div>
        </div>

        <div id="tea-conteudo-liberado" style="display: none; flex-direction: column; gap: 22px;">
          <div class="tea-box">
            <h3 id="saudacao-espaco-tea">🌿 Espaço Personalizado Ativo</h3>
            <p style="font-size: 12px; color: #475569; font-weight: 600; margin-top: 4px;">Ambiente seguro de regulação sensorial e apoio à comunicação.</p>
          </div>

          <h4 style="color: var(--tea-blue); font-weight: 800; text-align: center; margin-bottom: 15px;">Jornada das Emoções do Dia</h4>
          <div class="interactive-card" style="border-color: #BAE6FD; margin-bottom: 24px; position:relative; min-height: 270px; overflow:hidden;">
            
            <div id="emocoes-passo-1" class="fade-transition" style="width: 100%;">
              <p style="font-weight: 700; margin-bottom: 15px;">Como o(a) <strong id="tea-emocao-nome" style="color: var(--tea-blue);">Xexéu</strong> está se sentindo hoje?</p>
              <img id="tea-emocao-img" src="https://res.cloudinary.com/oactqmgs/image/upload/v1786902347/xexeu.png" alt="Personagem do Dia" style="width: 100px; height: 100px; object-fit: contain; margin-bottom: 20px;">
              
              <div style="display: flex; gap: 15px; justify-content: center; flex-wrap: wrap;">
                <div class="emotion-card" onclick="responderEmocao('Feliz')">
                  <div style="font-size: 35px;">😄</div>
                  <p style="font-weight: 800; color: #16A34A; margin-top: 5px; font-size:12px;">Feliz</p>
                </div>
                <div class="emotion-card" onclick="responderEmocao('Calmo')">
                  <div style="font-size: 35px;">😌</div>
                  <p style="font-weight: 800; color: var(--tea-blue); margin-top: 5px; font-size:12px;">Calmo</p>
                </div>
                <div class="emotion-card" onclick="responderEmocao('Triste')">
                  <div style="font-size: 35px;">😢</div>
                  <p style="font-weight: 800; color: #475569; margin-top: 5px; font-size:12px;">Triste</p>
                </div>
              </div>
            </div>

            <div id="emocoes-passo-2" class="fade-transition fade-out" style="width: 100%; display: none; position: absolute; top: 16px; left: 0;">
              <p style="font-weight: 900; color: var(--primary-dark); font-size: 18px; margin-bottom: 15px;">E você? Como está se sentindo agora?</p>
              
              <div style="display: flex; gap: 10px; justify-content: center; flex-wrap: wrap;">
                <div class="emotion-card" onclick="responderMinhaEmocao('Feliz')" style="width: 80px; padding:10px;">
                  <div style="font-size: 30px;">😄</div>
                  <p style="font-weight: 800; color: #16A34A; margin-top: 5px; font-size:11px;">Feliz</p>
                </div>
                <div class="emotion-card" onclick="responderMinhaEmocao('Calmo')" style="width: 80px; padding:10px;">
                  <div style="font-size: 30px;">😌</div>
                  <p style="font-weight: 800; color: var(--tea-blue); margin-top: 5px; font-size:11px;">Calmo</p>
                </div>
                <div class="emotion-card" onclick="responderMinhaEmocao('Triste')" style="width: 80px; padding:10px;">
                  <div style="font-size: 30px;">😢</div>
                  <p style="font-weight: 800; color: #475569; margin-top: 5px; font-size:11px;">Triste</p>
                </div>
                <div class="emotion-card" onclick="responderMinhaEmocao('Bravo')" style="width: 80px; padding:10px;">
                  <div style="font-size: 30px;">😤</div>
                  <p style="font-weight: 800; color: #DC2626; margin-top: 5px; font-size:11px;">Bravo</p>
                </div>
              </div>
            </div>

          </div>

          <h4 style="color: var(--tea-blue); font-weight: 800; text-align: center; margin-bottom: 15px;">Comunicação Básica (CAA)</h4>
          <div class="interactive-card" style="border-color: #BAE6FD;">
            <p style="font-weight: 700; margin-bottom: 5px; font-size: 13px;">Toque no desenho para falar:</p>
            <div class="caa-grid">
              <div class="caa-btn" onclick="lerTexto('Eu quero água, por favor.')"><span>💧</span><p>Água</p></div>
              <div class="caa-btn" onclick="lerTexto('Estou com fome.')"><span>🍎</span><p>Comer</p></div>
              <div class="caa-btn" onclick="lerTexto('Preciso ir ao banheiro.')"><span>🚽</span><p>Banheiro</p></div>
            </div>
            <p style="font-size: 11px; color: #64748B; margin-top: 10px;">✨ Quer <strong>adicionar novos botões personalizados e ilimitados</strong>? Conheça o <strong>Clube VIP</strong>!</p>
          </div>
        </div>

      </div>
    </main>

    <!-- PÁGINA VIP -->
    <main id="pagina-vip" class="page-content">
      <div class="age-group-section">
        <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 14px;">
          <h3 class="age-title" style="color: #1E293B; margin: 0;">⭐ Clube VIP da Turminha</h3>
          <button class="btn-audio-mini" onclick="lerTexto('Faça parte do Clube VIP e tenha acesso a ferramentas avançadas para os pais!')" title="Ouvir">🔊</button>
        </div>

        <!-- VISÃO BLOQUEADA -->
        <div id="vip-locked-view" class="vip-lock-container">
          <div class="vip-lock-header-clickable" title="Clique para assinar" onclick="document.getElementById('cad-email').focus()">
            <h3>🧸 Ferramentas Avançadas, Temporizador Completo e Configuração de Voz</h3>
            <div class="vip-price-tag" style="margin-top: 10px;">Acesso Ilimitado: R$ 6,00 / mês</div>
          </div>
          
          <div class="vip-heart-msg">
            <p style="margin-bottom: 6px;">💖 <strong>O que o Clube VIP desbloqueia para os Pais e para as Crianças?</strong></p>
            <ul style="text-align: left; margin: 8px 0 8px 18px; font-weight: 600;">
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
          
          <div class="vip-grid-forms">
            <div class="vip-form-box" id="caixa-cadastro-vip">
              <h4>✨ Desbloquear Acesso VIP</h4>
              <label style="font-size: 11px; font-weight: 700; color: var(--text-muted); display: block; margin-bottom: 3px;">Seu E-mail:</label>
              <input type="email" id="cad-email" class="vip-input" placeholder="seu@email.com">
              
              <label style="font-size: 11px; font-weight: 700; color: var(--text-muted); display: block; margin-bottom: 3px;">Crie uma Senha:</label>
              <input type="password" id="cad-senha" class="vip-input" placeholder="Senha secreta">
              
              <a href="https://pay.kiwify.com.br/avOqrEg" target="_blank" class="btn-vip-checkout" onclick="salvarECadastrar()">Quero Ser VIP por R$ 6,00 💳</a>
            </div>

            <div class="vip-form-box" style="border-color: #CBD5E1;">
              <h4 style="color: #1E293B;">🔑 Já sou Assinante</h4>
              <label style="font-size: 11px; font-weight: 700; color: var(--text-muted); display: block; margin-bottom: 3px;">E-mail Cadastrado:</label>
              <input type="email" id="log-email" class="vip-input" placeholder="seu@email.com">
              
              <label style="font-size: 11px; font-weight: 700; color: var(--text-muted); display: block; margin-bottom: 3px;">Sua Senha:</label>
              <input type="password" id="log-senha" class="vip-input" placeholder="Sua senha">
              
              <button type="button" onclick="fazerLogin()" style="width:100%; padding: 10px; background: #3B82F6; color: #FFF; border: none; border-radius: 10px; font-weight: 800; cursor: pointer;">Entrar no Clube VIP</button>
            </div>
          </div>
        </div>

        <!-- VISÃO DESBLOQUEADA (ÁREA VIP) -->
        <div id="vip-unlocked-view" class="vip-content-unlocked">
          <div style="background: #D1FAE5; border: 2px solid #10B981; padding: 12px 16px; border-radius: 12px; display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 8px;">
            <div>
              <h4 style="color: #065F46; font-size: 15px; font-weight: 900; margin-bottom: 2px;">🎉 Bem-vindo ao Clube VIP!</h4>
              <p style="font-size: 11.5px; color: #047857; margin: 0; font-weight: 600;">Seu acesso parental e de ferramentas avançadas está ativo.</p>
            </div>
            <button onclick="sairVIP()" style="background: #EF4444; color: #FFF; border: none; padding: 8px 14px; border-radius: 8px; font-weight: 800; font-size: 11.5px; cursor: pointer;">🔒 Sair</button>
          </div>

          <div class="perfil-selector-box">
            <h4 style="color: #1E293B; font-size: 14px; font-weight: 900; margin-bottom: 2px;">👤 Seu Perfil de Super Fã</h4>
            <div id="avatarEscolhaGrid" class="avatar-escolha-grid"></div>
          </div>

          <div class="vip-internal-tabs">
            <button id="tab-vip-geral" class="vip-int-btn active" onclick="alternarAbaVip('geral')">🌟 Diversão VIP</button>
            <button id="tab-vip-tea" class="vip-int-btn" onclick="alternarAbaVip('tea')">🧩 Especial Pais & TEA (VIP)</button>
          </div>

          <!-- SUB-ÁREA 1: DIVERSÃO VIP -->
          <div id="conteudo-vip-geral" class="vip-sub-area active-area">
            
            <div class="certificado-container">
              <h3>Diploma de Super Fã</h3>
              <p style="font-size: 12px; color: #78350F; margin-bottom: 10px;">Digite o nome da criança para gerar o certificado oficial!</p>
              <input type="text" id="nome-certificado" placeholder="Nome da Criança" style="padding: 8px; border-radius: 8px; border: 2px solid #FCD34D; outline: none; margin-bottom: 10px; width: 80%; max-width: 250px;">
              <br>
              <button onclick="gerarCertificado()" style="background: #D97706; color: #FFF; border: none; padding: 8px 16px; border-radius: 8px; font-weight: 800; cursor: pointer;">Gerar Diploma 🎓</button>
              <div id="certificado-resultado" style="display:none; margin-top: 15px;">
                <span class="certificado-nome" id="exibir-nome-certificado"></span>
                <p style="font-weight: 800; color: #B45309; font-size: 14px;">É oficialmente Super Fã da Turminha do Xexéu! 🌟</p>
              </div>
            </div>

            <div class="radio-vip-box">
              <h3 style="margin-bottom: 6px; font-weight: 900;">🎵 Rádio da Turminha</h3>
              <p style="font-size: 13px; color: #94A3B8; margin-bottom: 15px;">Ouça todas as músicas oficiais direto no Spotify!</p>
              <a href="https://open.spotify.com/intl-pt/artist/6ykKQ3uP6Wl2REylKJAdJ6?si=H4uu2B9pSd2GIwIs1Tx8Rg" target="_blank" class="radio-btn">▶️ Abrir Músicas no Spotify</a>
            </div>

            <div class="drive-banner-box">
              <h4 style="color: #1E3A8A; font-size: 17px; font-weight: 900;">📁 Drive Oficial da Turminha</h4>
              <p style="font-size: 12.5px; color: #1E40AF; margin-top: 4px; font-weight: 600;">Baixe Wallpapers de alta qualidade e Desenhos para Colorir!</p>
              <a href="https://drive.google.com/drive/folders/1gi1SjbtPXWuFBxhfMEuRpK2z4BFPXIBP?usp=drive_link" target="_blank" class="btn-drive">Acessar Pasta Oficial 📥</a>
            </div>

            <div class="video-card">
              <div class="video-header">
                <h3>🎬 Episódios Secretos e Prévias VIP</h3>
              </div>
              <div class="video-wrapper">
                <iframe src="https://www.youtube-nocookie.com/embed/videosseries?list=PLFR1LwoD9sys" allowfullscreen></iframe>
              </div>
            </div>
          </div>

          <!-- SUB-ÁREA 2: ESPECIAL PAIS & TEA -->
          <div id="conteudo-vip-tea" class="vip-sub-area">
            
            <div class="vip-card-box" style="background: #EFF6FF; border-color: #93C5FD;">
              <h4 style="color: #1E40AF; font-weight: 900; font-size: 15px; margin-bottom: 6px;">🔊 Configuração de Voz dos Cartões</h4>
              <p style="font-size: 12px; color: #1E3A8A; font-weight: 600; margin-bottom: 12px;">Escolha o tom de voz e a velocidade de leitura para o site inteiro.</p>
              
              <div style="display: flex; flex-direction: column; gap: 8px; text-align: left;">
                <label style="font-size: 11px; font-weight: 800; color: #1E40AF;">Selecione a Voz Disponível:</label>
                <select id="selectVozVip" class="vip-input" onchange="mudarVozSelecionada(this.value)" style="background: #FFF;">
                  <option value="">Carregando vozes...</option>
                </select>

                <label style="font-size: 11px; font-weight: 800; color: #1E40AF;">Velocidade de Fala (<span id="txtVelocidade">1.0x</span>):</label>
                <input type="range" id="rangeVelocidade" min="0.7" max="1.3" step="0.05" value="1.0" oninput="mudarVelocidadeFala(this.value)">
              </div>
            </div>

            <!-- PRANCHA DE COMUNICAÇÃO EDITÁVEL -->
            <div class="vip-card-box" style="border-color: #BAE6FD;">
              <h4 style="color: var(--tea-blue); font-weight: 900; font-size: 15px; margin-bottom: 5px;">💬 Prancha de Comunicação Editável (CAA)</h4>
              <p style="font-size: 12px; color: #475569; font-weight: 600;">Adicione quantos botões personalizados você quiser para a rotina da criança.</p>
              
              <div style="background: #F8FAFC; padding: 10px; border-radius: 8px; border: 2px dashed #BAE6FD; margin: 10px 0; display: flex; gap: 6px; flex-wrap: wrap;">
                <input type="text" id="caaEmojiInput" placeholder="Emoji (ex: 🧸)" style="width: 60px; padding: 6px; text-align:center; border: 1px solid #CBD5E1; border-radius:6px;">
                <input type="text" id="caaTextoInput" placeholder="Frase (ex: Quero meu ursinho)" style="flex:1; padding: 6px; border: 1px solid #CBD5E1; border-radius:6px; font-size:12px;">
                <button onclick="adicionarBotaoCaaVip()" style="background: var(--tea-blue); color:#FFF; border:none; padding: 6px 12px; border-radius:6px; font-weight:800; cursor:pointer;">Adicionar ➕</button>
              </div>

              <div id="caaGridVip" class="caa-grid"></div>
            </div>

            <!-- CAIXA DO ACALENTO COMPLETA (SONS REAIS FUNCIONAIS) -->
            <div class="vip-card-box" style="background: #F8FAFC; border-color: #94A3B8;">
              <h4 style="color: #334155; margin-bottom: 6px; font-size: 15px; font-weight: 900;">🎧 Caixa do Acalento (Sons Relaxantes)</h4>
              <p style="font-size: 12px; color: #64748B; font-weight: 600;">Regulação sensorial para momentos de crise ou transição.</p>
              <div class="acalento-grid">
                <button class="acalento-btn" onclick="tocarSomReal('https://cdn.freesound.org/previews/237/237729_4284968-lq.mp3')"><span>🌧️</span><p>Chuva Suave</p></button>
                <button class="acalento-btn" onclick="tocarSomReal('https://cdn.freesound.org/previews/322/322744_5121236-lq.mp3')"><span>🐦</span><p>Pássaros</p></button>
                <button class="acalento-btn" onclick="tocarSomReal('https://cdn.freesound.org/previews/400/400632_5121236-lq.mp3')"><span>🌊</span><p>Ondas do Mar</p></button>
              </div>
            </div>

            <!-- ROTINA DE SUPER FORÇA -->
            <div class="vip-card-box" style="background: #F0FDF4; border-color: #86EFAC;">
              <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap;">
                <div>
                  <h4 style="color: #166534; margin-bottom: 6px; font-size: 15px; font-weight: 900;">🌟 Rotina de Super Força</h4>
                  <p style="font-size: 12px; color: #15803D; font-weight: 600; margin-bottom: 12px;">Controle visual para vitaminas e remedinhos. Salvo <strong>apenas no aparelho</strong>.</p>
                </div>
                <button class="btn-audio-mini" onclick="lerTexto('Toda vez que você cuidar da saúde, marque aqui para ganhar pontos!')" title="Ouvir">🔊</button>
              </div>

              <div style="background: #FFF; padding: 10px; border-radius: 10px; border: 2px dashed #86EFAC; margin-bottom: 14px; display: flex; gap: 8px; flex-wrap: wrap; align-items: center;">
                <select id="rotina-icone" style="padding: 8px; border-radius: 8px; border: 2px solid #CBD5E1; outline: none; font-size: 14px;">
                  <option value="💧">💧 Gotinha</option>
                  <option value="🥄">🥄 Xarope</option>
                  <option value="💊">💊 Comprimido</option>
                  <option value="🍎">🍎 Vitamina</option>
                </select>
                <input type="text" id="rotina-texto" placeholder="Ex: Vitamina C da Manhã" style="flex: 1; padding: 8px; border-radius: 8px; border: 2px solid #CBD5E1; outline: none; font-size: 13px;">
                <button onclick="adicionarRotinaVip()" style="background: #10B981; color: #FFF; border: none; padding: 8px 14px; border-radius: 8px; font-weight: 800; cursor: pointer;">Adicionar ➕</button>
              </div>

              <div id="lista-rotinas-vip"></div>
            </div>

          </div>

        </div>

      </div>
    </main>

    <section class="support-form-box">
      <h5>📬 Precisa de Ajuda ou quer enviar uma Sugestão?</h5>
      <p>Escreva para nós! Sua mensagem será enviada diretamente para <strong>turminhaxexeu@gmail.com</strong>.</p>
      <input type="email" id="suporteEmail" class="support-input" placeholder="Seu e-mail para contato">
      <textarea id="suporteMensagem" class="support-textarea" placeholder="Digite sua mensagem aqui..."></textarea>
      <button onclick="enviarSuporteReclamacao()" class="support-btn" id="btnEnviarSuporte">Enviar Mensagem ✉️</button>
    </section>

    <footer>
      <span>© Turminha do Xexéu - eve Design - Todos os direitos reservados</span>
      <a onclick="abrirPrivacidade()">Política de Privacidade</a>
    </footer>

  </div>

  <script>
    let audioAtivo = true;
    let audioUnlocked = false; 
    let vozesDisponiveis = [];
    let vozSelecionadaIndex = localStorage.getItem('turminha_voz_index') || 0;
    let velocidadeFala = parseFloat(localStorage.getItem('turminha_velocidade') || 1.0);
    
    let pontosConquista = parseInt(localStorage.getItem('turminha_pontos') || '0');
    let listaRotinasSuperForca = JSON.parse(localStorage.getItem('turminha_rotinas')) || [];
    let listaCaaVip = JSON.parse(localStorage.getItem('turminha_caa_vip')) || [
      { emoji: '🧸', texto: 'Quero meu brinquedo' },
      { emoji: '🍎', texto: 'Estou com fome' },
      { emoji: '💤', texto: 'Quero descansar' }
    ];
    let timerInterval = null;
    let somAcalentoAtual = null;
    
    const SENHA_MESTRA_CRIADORA = "65628467";
    const URL_SCRIPT = "https://script.google.com/macros/s/AKfycbxkMvHbuXfZWEfd1tzLDvk4YzIW66alJyp2J9VGm-8nQV1iotNqaDLDieEeVblb6RcTMA/exec";
    
    const TODOS_PERSONAGENS = [
      { nome: 'Xexéu', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786902347/xexeu.png', letra: 'X' },
      { nome: 'Capilé', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786902348/capile.png', letra: 'C' },
      { nome: 'Maya', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786907604/16.png', letra: 'M' },
      { nome: 'Theo', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786907605/17.png', letra: 'T' },
      { nome: 'Nina', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786903228/Sem_nome_512_x_512_px_1.png', letra: 'N' },
      { nome: 'Iza', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786902350/iza.png', letra: 'I' },
      { nome: 'Sam', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786907601/14.png', letra: 'S' },
      { nome: 'Lia', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786907602/15.png', letra: 'L' },
      { nome: 'Joca', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786902350/joca.png', letra: 'J' },
      { nome: 'Leo', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786902347/leo.png', letra: 'L' },
      { nome: 'Beto', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786902348/vovo_beto.png', letra: 'B' },
      { nome: 'Hilda', img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786902347/vovo_hilda.png', letra: 'H' }
    ];

    const INFO_PERSONAGENS = {
      'Xexéu': { nome: "Xexéu", desc: "O pássaro azul de boina amarela! Inspirado no pássaro xexéu e no nome do bisavô Mariano Xexéu." },
      'Capilé': { nome: "Capilé", desc: "O Capilé é o cachorrinho de orelhas grandes e coleira azul-celeste com pingente de osso dourado!" },
      'Maya': { nome: "Maya", desc: "A Maya é a mãe dedicada da Iza e da Nina. Extremamente organizada e atenciosa." },
      'Theo': { nome: "Theo", desc: "O Theo é o pai da Iza e da Nina. Calmo, observador e com um sorriso tranquilo." },
      'Nina': { nome: "Nina", desc: "A Nina é super esperta e adora aprender coisas novas com seus cabelos cacheados!" },
      'Iza': { nome: "Iza", desc: "A Iza é a vaidosa da Turminha! De vestidinho rosa e cabelos ondulados." },
      'Sam': { nome: "Sam", desc: "O Sam é o paizão ruivo do Joca e do Leo. Descontraído, adora construir brinquedos." },
      'Lia': { nome: "Lia", desc: "A Lia é a mãe do Joca e do Leo. Estilosa e alegre, traz energia contagiante." },
      'Joca': { nome: "Joca", desc: "O Joca é o menino de camiseta verde! Doidinho e engraçado." },
      'Leo': { nome: "Leo", desc: "O Leo é focado em suas descobertas com muita imaginação." },
      'Beto': { nome: "Vovô Beto", desc: "Usa óculos quadrados. Traz paciência, bom humor e energia contagiante." },
      'Hilda': { nome: "Vovó Hilda", desc: "Usa óculos redondos. Guardando doçura, abraços e valores preciosos." }
    };

    function carregarVozes() {
      if ('speechSynthesis' in window) {
        vozesDisponiveis = window.speechSynthesis.getVoices();
        const select = document.getElementById('selectVozVip');
        if (select && vozesDisponiveis.length > 0) {
          select.innerHTML = '';
          vozesDisponiveis.forEach((voz, index) => {
            if (voz.lang.includes('pt') || voz.lang.includes('PT')) {
              const opt = document.createElement('option');
              opt.value = index;
              opt.innerText = `${voz.name} (${voz.lang})`;
              if (index == vozSelecionadaIndex) opt.selected = true;
              select.appendChild(opt);
            }
          });
        }
      }
    }

    if ('speechSynthesis' in window) {
      window.speechSynthesis.onvoiceschanged = carregarVozes;
      carregarVozes();
    }

    function desbloquearAudioMobileOnce() {
      if (!audioUnlocked && 'speechSynthesis' in window) {
        window.speechSynthesis.speak(new SpeechSynthesisUtterance(""));
        audioUnlocked = true;
      }
    }

    function mudarVozSelecionada(index) {
      vozSelecionadaIndex = index;
      localStorage.setItem('turminha_voz_index', index);
      lerTexto("Voz alterada com sucesso!");
    }

    function mudarVelocidadeFala(val) {
      velocidadeFala = parseFloat(val);
      localStorage.setItem('turminha_velocidade', velocidadeFala);
      const txt = document.getElementById('txtVelocidade');
      if(txt) txt.innerText = `${velocidadeFala}x`;
    }

    function lerTexto(texto) {
      exibirAvisoVisual(texto);
      if (!audioAtivo) return;
      if ('speechSynthesis' in window) {
        try {
          window.speechSynthesis.cancel(); 
          const utterance = new SpeechSynthesisUtterance(texto);
          utterance.lang = 'pt-BR';
          utterance.rate = velocidadeFala; 
          utterance.pitch = 1.05; 
          
          if (vozesDisponiveis.length === 0) {
            vozesDisponiveis = window.speechSynthesis.getVoices();
          }
          
          if (vozesDisponiveis[vozSelecionadaIndex]) {
            utterance.voice = vozesDisponiveis[vozSelecionadaIndex];
          } else {
            const vozPt = vozesDisponiveis.find(v => v.lang.includes('pt-BR') || v.lang.includes('pt'));
            if (vozPt) utterance.voice = vozPt;
          }
          
          window.speechSynthesis.speak(utterance);
        } catch (e) { console.log(e); }
      }
    }

    function tocarVozETexto(chave) {
      const p = INFO_PERSONAGENS[chave];
      if (!p) return;
      document.getElementById('detalhe-nome').innerText = p.nome;
      document.getElementById('detalhe-texto').innerText = p.desc;
      lerTexto(p.desc);
    }

    function alternarAudioGlobal() {
      audioAtivo = !audioAtivo;
      const btn = document.getElementById('toggleAudioBtn');
      if ('speechSynthesis' in window) window.speechSynthesis.cancel();
      
      if (audioAtivo) {
        btn.classList.remove('muted');
        document.getElementById('audioIcon').innerText = '🔊';
        document.getElementById('audioText').innerText = 'Voz';
        lerTexto("A voz da Turminha está ativada!");
      } else {
        btn.classList.add('muted');
        document.getElementById('audioIcon').innerText = '🔇';
        document.getElementById('audioText').innerText = 'Mudo';
        exibirAvisoVisual("Voz desligada!");
      }
    }

    function exibirAvisoVisual(texto) {
      const toast = document.getElementById('visualToast');
      if (toast) {
        toast.innerText = texto;
        toast.classList.add('show');
        setTimeout(() => toast.classList.remove('show'), 2500);
      }
    }

    function verificarCookies() {
      const aceitou = localStorage.getItem('aceitou_cookies');
      if (!aceitou) {
        setTimeout(() => { document.getElementById('cookieBanner').classList.add('show'); }, 1500);
      }
    }

    function aceitarCookies() {
      localStorage.setItem('aceitou_cookies', 'true');
      document.getElementById('cookieBanner').classList.remove('show');
    }

    function abrirPrivacidade() { document.getElementById('modalPrivacidade').classList.add('active'); }
    function fecharPrivacidade() { document.getElementById('modalPrivacidade').classList.remove('active'); }

    function salvarOnboardingTea() {
      const nomeCrianca = document.getElementById('tea-nome-crianca').value.trim();
      const email = document.getElementById('tea-email').value.trim();
      const senha = document.getElementById('tea-senha').value.trim();

      if (!email || !senha) {
        alert("Por favor, preencha o e-mail e crie a senha parental!");
        return;
      }

      localStorage.setItem('tea_nome_crianca', nomeCrianca || 'Amigo(a)');
      localStorage.setItem('tea_email_pais', email);
      localStorage.setItem('tea_senha_pais', senha);

      document.getElementById('tea-onboarding-box').style.display = 'none';
      document.getElementById('tea-conteudo-liberado').style.display = 'flex';
      carregarPersonagemDoDiaTEA();
      lerTexto("Espaço TEA configurado com sucesso! Aproveitem.");
    }

    function verificarStatusOnboardingTea() {
      const emailSalvo = localStorage.getItem('tea_email_pais');
      const nomeSalvo = localStorage.getItem('tea_nome_crianca') || 'Visitante';
      if (emailSalvo) {
        document.getElementById('tea-onboarding-box').style.display = 'none';
        document.getElementById('tea-conteudo-liberado').style.display = 'flex';
        const saudacaoEl = document.getElementById('saudacao-espaco-tea');
        if (saudacaoEl) saudacaoEl.innerText = `🌿 Olá, ${nomeSalvo}! Espaço Personalizado`;
      }
    }

    function tocarSomReal(urlMp3) {
      if (somAcalentoAtual) {
        somAcalentoAtual.pause();
        somAcalentoAtual.currentTime = 0;
        if (somAcalentoAtual.src === urlMp3) {
          somAcalentoAtual = null;
          lerTexto("Som pausado");
          return;
        }
      }
      somAcalentoAtual = new Audio(urlMp3);
      somAcalentoAtual.loop = true;
      somAcalentoAtual.play().then(() => {
        lerTexto("Reproduzindo som relaxante");
      }).catch(function(erro) {
        console.log("Áudio em manutenção:", erro);
        lerTexto("Este som relaxante estará disponível em breve!");
      });
    }

    let personagemEmocaoAtual = "Xexéu";

    function carregarPersonagemDoDiaTEA() {
      const dia = new Date().getDay(); 
      const nomesPorDia = ['Xexéu', 'Maya', 'Joca', 'Nina', 'Sam', 'Capilé', 'Iza'];
      const nomeSorteado = nomesPorDia[dia] || 'Xexéu';
      const p = TODOS_PERSONAGENS.find(x => x.nome === nomeSorteado) || TODOS_PERSONAGENS[0];
      
      personagemEmocaoAtual = p.nome;
      const nomeEl = document.getElementById('tea-emocao-nome');
      const imgEl = document.getElementById('tea-emocao-img');
      if (nomeEl) nomeEl.innerText = p.nome;
      if (imgEl) imgEl.src = p.img;
      
      const p1 = document.getElementById('emocoes-passo-1');
      const p2 = document.getElementById('emocoes-passo-2');
      if (p1) { p1.style.display = 'block'; p1.style.opacity = '1'; }
      if (p2) { p2.style.display = 'none'; p2.style.opacity = '0'; }
    }

    function toggleSensoryMode() {
      const isSensory = document.body.classList.toggle('sensory-mode');
      const btnHeader = document.getElementById('btnSensoryHeader');
      if (isSensory) {
        if(btnHeader) btnHeader.innerHTML = '🌿 Normal';
        if(somAcalentoAtual) { somAcalentoAtual.pause(); somAcalentoAtual = null; }
        lerTexto("Modo calmo ativado no site inteiro.");
      } else {
        if(btnHeader) btnHeader.innerHTML = '🌿 Modo Calmo';
        lerTexto("Modo padrão ativado.");
      }
    }
    
    function responderEmocao(emocao) {
      if (emocao === 'Feliz') {
        lerTexto(`Isso mesmo! O(a) ${personagemEmocaoAtual} está muito feliz! Agora, conta pra mim...`);
        const passo1 = document.getElementById('emocoes-passo-1');
        const passo2 = document.getElementById('emocoes-passo-2');
        if(passo1) passo1.classList.add('fade-out');
        setTimeout(() => {
          if(passo1) passo1.style.display = 'none';
          if(passo2) {
            passo2.style.display = 'block';
            void passo2.offsetWidth; 
            passo2.classList.remove('fade-out');
          }
          lerTexto("E você? Como está se sentindo agora?");
        }, 3500);
      } else {
        lerTexto(`Você acha que ele(a) está ${emocao}? Na verdade, o(a) ${personagemEmocaoAtual} está com um lindo sorriso Feliz!`);
      }
    }

    function responderMinhaEmocao(emocao) {
      if (emocao === 'Feliz') lerTexto("Que maravilha! Ficar feliz é muito gostoso!");
      else if (emocao === 'Calmo') lerTexto("Estar calmo é tão bom, não é verdade? Respire fundo e aproveite esse momento tranquilo.");
      else if (emocao === 'Triste') lerTexto("Está tudo bem se sentir triste às vezes. Que tal um abraço virtual bem apertado da Turminha?");
      else if (emocao === 'Bravo') lerTexto("Entendo que você está bravo. É normal. Vamos respirar fundo juntos? Puxa o ar... e solta...");
      
      setTimeout(() => {
        const passo1 = document.getElementById('emocoes-passo-1');
        const passo2 = document.getElementById('emocoes-passo-2');
        if(passo2) passo2.classList.add('fade-out');
        setTimeout(() => {
          if(passo2) passo2.style.display = 'none';
          if(passo1) {
            passo1.style.display = 'block';
            void passo1.offsetWidth;
            passo1.classList.remove('fade-out');
          }
        }, 800);
      }, 7000);
    }

    function atualizarBotoesTemporizadorGeral() {
      const container = document.getElementById('botoesTemporizadorGeral');
      if (!container) return;
      const isVip = localStorage.getItem('turminha_xexeu_vip_ativo') === 'true';
      
      if (isVip) {
        container.innerHTML = `
          <button class="timer-btn" onclick="iniciarTemporizador(1)">1 Min</button>
          <button class="timer-btn" onclick="iniciarTemporizador(3)">3 Min</button>
          <button class="timer-btn" onclick="iniciarTemporizador(5)">5 Min</button>
          <button class="timer-btn" onclick="iniciarTemporizador(10)">10 Min</button>
          <button class="timer-btn" onclick="iniciarTemporizador(15)">15 Min</button>
          <button class="timer-btn" onclick="iniciarTemporizador(30)">30 Min</button>
        `;
      } else {
        // Limitado estritamente a 2 min no modo grátis
        container.innerHTML = `
          <button class="timer-btn" onclick="iniciarTemporizador(1)">1 Min</button>
          <button class="timer-btn" onclick="iniciarTemporizador(2)">2 Min (Máx)</button>
        `;
      }
    }

    function iniciarTemporizador(minutos) {
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

    function tentarDesbloquearTela() {
      const digitada = document.getElementById('senhaDesbloqueio').value.trim();
      const senhaSalvaTea = localStorage.getItem('tea_senha_pais');
      const senhaSalvaVip = document.getElementById('cad-senha')?.value.trim();
      const senhaMestra = SENHA_MESTRA_CRIADORA;

      if (digitada === senhaSalvaTea || digitada === senhaSalvaVip || digitada === senhaMestra) {
        document.getElementById('modalBloqueioTempo').classList.remove('active');
        document.getElementById('senhaDesbloqueio').value = '';
        lerTexto("Tempo desbloqueado com sucesso!");
      } else {
        alert("❌ Senha incorreta! Digite a senha parental cadastrada.");
      }
    }

    function renderizarCaaVip() {
      const grid = document.getElementById('caaGridVip');
      if (!grid) return;
      grid.innerHTML = '';
      const padroes = [
        { emoji: '💧', texto: 'Água' },
        { emoji: '🍎', texto: 'Comer' },
        { emoji: '🚽', texto: 'Banheiro' }
      ];
      const todos = [...padroes, ...listaCaaVip];
      todos.forEach((item) => {
        const btn = document.createElement('div');
        btn.className = 'caa-btn';
        btn.innerHTML = `<span>${item.emoji}</span><p>${item.texto}</p>`;
        btn.onclick = () => lerTexto(`Eu quero ${item.texto.toLowerCase()}.`);
        grid.appendChild(btn);
      });
    }

    function adicionarBotaoCaaVip() {
      const emoji = document.getElementById('caaEmojiInput').value.trim() || '⭐';
      const texto = document.getElementById('caaTextoInput').value.trim();
      if (!texto) { alert("Digite a frase do botão!"); return; }

      listaCaaVip.push({ emoji: emoji, texto: texto });
      localStorage.setItem('turminha_caa_vip', JSON.stringify(listaCaaVip));
      document.getElementById('caaEmojiInput').value = '';
      document.getElementById('caaTextoInput').value = '';
      renderizarCaaVip();
      lerTexto("Novo botão adicionado com sucesso!");
    }

    function mudarPagina(pagina) {
      ['inicio', 'videos', 'jogos', 'tea', 'vip'].forEach(p => {
        document.getElementById('pagina-' + p).classList.remove('active-page');
        document.getElementById('btn-tab-' + p).classList.remove('active');
      });

      document.getElementById('pagina-' + pagina).classList.add('active-page');
      document.getElementById('btn-tab-' + pagina).classList.add('active');

      if (pagina === 'jogos') {
        setTimeout(redimensionarCanvas, 100);
        atualizarBotoesTemporizadorGeral();
      }
      if (pagina === 'tea') {
        verificarStatusOnboardingTea();
        lerTexto("Bem-vindo ao Espaço Inclusivo da Turminha.");
      }
      if (pagina === 'vip') {
        verificarStatusVip();
        criarSeletorAvatarPerfil();
        renderizarRotinasVip();
        renderizarCaaVip();
        carregarVozes();
      }
    }

    function mudarSubJogo(sub) {
      ['lousa', 'contar', 'letras', 'memoria', 'quiz', 'vip-historia', 'vip-cor'].forEach(s => {
        const el = document.getElementById('game-' + s);
        const subBtn = document.getElementById('subtab-' + s);
        if(el) el.classList.remove('active-game-page');
        if(subBtn) subBtn.classList.remove('active');
      });
      document.getElementById('game-' + sub).classList.add('active-game-page');
      document.getElementById('subtab-' + sub).classList.add('active');
      if(sub === 'lousa') setTimeout(redimensionarCanvas, 50);
    }

    function alternarAbaVip(aba) {
      document.getElementById('tab-vip-geral').classList.remove('active');
      document.getElementById('tab-vip-tea').classList.remove('active');
      document.getElementById('conteudo-vip-geral').classList.remove('active-area');
      document.getElementById('conteudo-vip-tea').classList.remove('active-area');

      document.getElementById(`tab-vip-${aba}`).classList.add('active');
      document.getElementById(`conteudo-vip-${aba}`).classList.add('active-area');

      if(aba === 'geral') lerTexto("Área de diversão ativada!");
      if(aba === 'tea') lerTexto("Área especial para os pais ativada!");
    }

    function gerarCertificado() {
      const nome = document.getElementById('nome-certificado').value.trim();
      if (!nome) { alert("Por favor, digite o nome da criança!"); return; }
      document.getElementById('exibir-nome-certificado').innerText = nome;
      document.getElementById('certificado-resultado').style.display = 'block';
      lerTexto(`Parabéns, ${nome}! Você agora é Super Fã oficial da Turminha do Xexéu!`);
    }

    function renderizarRotinasVip() {
      const container = document.getElementById('lista-rotinas-vip');
      if (!container) return;
      container.innerHTML = '';
      if (listaRotinasSuperForca.length === 0) {
        container.innerHTML = '<p style="text-align:center; font-size:12px; color:#94A3B8;">Nenhuma rotina adicionada ainda.</p>';
        return;
      }
      listaRotinasSuperForca.forEach((rotina, index) => {
        const item = document.createElement('div');
        item.className = `rotina-item ${rotina.concluido ? 'concluido' : ''}`;
        item.innerHTML = `
          <div style="display:flex; align-items:center; gap:10px;">
            <span style="font-size:24px;">${rotina.icone}</span>
            <span class="rotina-texto" style="font-weight:700; font-size:14px; color:#1E293B;">${rotina.texto}</span>
          </div>
          <div style="display:flex; gap:6px;">
            ${!rotina.concluido ? `<button class="btn-concluir-rotina" onclick="completarRotina(${index})">✔️ Pronto</button>` : `<span style="font-size:12px; font-weight:800; color:#166534;">Força Ativada! 🦸</span>`}
            <button class="btn-remover-rotina" onclick="removerRotina(${index})">🗑️</button>
          </div>
        `;
        container.appendChild(item);
      });
    }

    function adicionarRotinaVip() {
      const icone = document.getElementById('rotina-icone').value;
      const texto = document.getElementById('rotina-texto').value.trim();
      if (!texto) { alert("Digite o nome da rotina!"); return; }
      listaRotinasSuperForca.push({ icone: icone, texto: texto, concluido: false });
      localStorage.setItem('turminha_rotinas', JSON.stringify(listaRotinasSuperForca));
      document.getElementById('rotina-texto').value = '';
      renderizarRotinasVip();
      lerTexto("Rotina adicionada com sucesso!");
    }

    function completarRotina(index) {
      listaRotinasSuperForca[index].concluido = true;
      localStorage.setItem('turminha_rotinas', JSON.stringify(listaRotinasSuperForca));
      adicionarPontos(10);
      renderizarRotinasVip();
      lerTexto("Você ganhou 10 pontos de Super Força!");
    }

    function removerRotina(index) {
      listaRotinasSuperForca.splice(index, 1);
      localStorage.setItem('turminha_rotinas', JSON.stringify(listaRotinasSuperForca));
      renderizarRotinasVip();
    }

    function salvarECadastrar() {
      const email = document.getElementById('cad-email').value.trim();
      const senha = document.getElementById('cad-senha').value.trim();
      if (!email || !senha) { alert("Preencha e-mail e senha parental."); return; }
      const dados = { email: email, senha: senha, status: "Pendente", tipo: "NOVO_CLIENTE", assunto: "Cadastro Iniciado VIP" };
      fetch(URL_SCRIPT, { method: "POST", mode: "no-cors", headers: { "Content-Type": "application/json" }, body: JSON.stringify(dados) }).catch(e => console.log(e));
    }

    function fazerLogin() {
      const email = document.getElementById('log-email').value.trim();
      const senha = document.getElementById('log-senha').value.trim();
      if (!email || !senha) { alert("Preencha e-mail e senha."); return; }
      if (senha === SENHA_MESTRA_CRIADORA) {
        localStorage.setItem('turminha_xexeu_vip_ativo', 'true');
        verificarStatusVip();
        lerTexto("Acesso Mestre liberado!");
        return;
      }
      fetch(`${URL_SCRIPT}?email=${encodeURIComponent(email)}&senha=${encodeURIComponent(senha)}`)
        .then(response => response.json())
        .then(data => {
          if (data && data.liberado === true) {
            localStorage.setItem('turminha_xexeu_vip_ativo', 'true');
            verificarStatusVip();
            lerTexto("Bem-vindo ao Clube VIP!");
          } else { 
            localStorage.removeItem('turminha_xexeu_vip_ativo');
            alert("❌ Acesso Negado: Assinatura pendente ou senha incorreta.");
          }
        })
        .catch(() => { 
          localStorage.removeItem('turminha_xexeu_vip_ativo');
          alert("❌ Acesso Negado: Verifique seus dados.");
        });
    }

    // --- VERIFICAÇÃO DE STATUS VIP (LIBERA AMOSTRAS NA ABA DE JOGOS) ---
    function verificarStatusVip() {
      const isVip = localStorage.getItem('turminha_xexeu_vip_ativo') === 'true';
      const lockedView = document.getElementById('vip-locked-view');
      const unlockedView = document.getElementById('vip-unlocked-view');

      // Amostras na aba de Jogos
      const avisoHistoria = document.getElementById('avisoVipBlocoHistoria');
      const conteudoHistoria = document.getElementById('conteudoVipHistoriaReal');
      const avisoCor = document.getElementById('avisoVipBlocoCor');
      const conteudoCor = document.getElementById('conteudoVipCorReal');

      if (isVip) {
        if(lockedView) lockedView.style.display = 'none';
        if(unlockedView) unlockedView.classList.add('active-vip');
        
        if(avisoHistoria) avisoHistoria.style.display = 'none';
        if(conteudoHistoria) conteudoHistoria.style.display = 'block';
        if(avisoCor) avisoCor.style.display = 'none';
        if(conteudoCor) conteudoCor.style.display = 'block';

        carregarDesafioHistoriaVip(); 
        carregarJogoCorVip();
      } else {
        if(lockedView) lockedView.style.display = 'block';
        if(unlockedView) unlockedView.classList.remove('active-vip');
        
        if(avisoHistoria) avisoHistoria.style.display = 'block';
        if(conteudoHistoria) conteudoHistoria.style.display = 'none';
        if(avisoCor) avisoCor.style.display = 'block';
        if(conteudoCor) conteudoCor.style.display = 'none';
      }
      atualizarBotoesTemporizadorGeral();
    }

    function sairVIP() {
      localStorage.removeItem('turminha_xexeu_vip_ativo');
      verificarStatusVip();
      lerTexto("Você saiu da Área VIP.");
      location.reload();
    }

    function criarSeletorAvatarPerfil() {
      const grid = document.getElementById('avatarEscolhaGrid');
      if (!grid || grid.children.length > 0) return;
      grid.innerHTML = '';
      const avatarAtual = localStorage.getItem('turminha_avatar_escolhido') || TODOS_PERSONAGENS[0].img;
      TODOS_PERSONAGENS.forEach(p => {
        const imgBtn = document.createElement('img');
        imgBtn.src = p.img;
        imgBtn.className = 'avatar-escolha-btn' + (p.img === avatarAtual ? ' selecionado' : '');
        imgBtn.title = p.nome;
        imgBtn.onclick = () => {
          document.querySelectorAll('.avatar-escolha-btn').forEach(b => b.classList.remove('selecionado'));
          imgBtn.classList.add('selecionado');
          localStorage.setItem('turminha_avatar_escolhido', p.img);
          lerTexto(`${p.nome} escolhido!`);
        };
        grid.appendChild(imgBtn);
      });
    }

    function carregarDesafioHistoriaVip() {
      const txt = document.getElementById('vip-historia-txt');
      const opts = document.getElementById('vip-historia-options');
      if(!txt || !opts) return;
      txt.innerText = "Quem é o pássaro azul de boina amarela que é o mascote oficial?";
      opts.innerHTML = '';
      ["Xexéu", "Capilé", "Joca"].forEach(nome => {
        const b = document.createElement('button'); b.className = 'btn-choice'; b.innerText = nome;
        b.onclick = () => {
          if(nome === "Xexéu") {
            b.classList.add('acertou');
            lerTexto("Acertou a história!");
            adicionarPontos(10);
            setTimeout(() => b.classList.remove('acertou'), 800);
          } else {
            b.classList.add('errou');
            lerTexto("Tente de novo!");
            setTimeout(() => b.classList.remove('errou'), 500);
          }
        };
        opts.appendChild(b);
      });
    }

    function carregarJogoCorVip() {
      const txt = document.getElementById('vip-cor-txt');
      const img = document.getElementById('vip-cor-img');
      const opts = document.getElementById('vip-cor-options');
      if(!txt || !img || !opts) return;
      txt.innerText = "Qual a cor da boina do Xexéu?";
      img.src = "https://res.cloudinary.com/oactqmgs/image/upload/v1786902347/xexeu.png";
      opts.innerHTML = '';
      ["Amarela", "Verde", "Azul"].forEach(cor => {
        const b = document.createElement('button'); b.className = 'btn-choice'; b.innerText = cor;
        b.onclick = () => {
          if(cor === "Amarela") {
            b.classList.add('acertou');
            lerTexto("Cor correta!");
            adicionarPontos(10);
            setTimeout(() => b.classList.remove('acertou'), 800);
          } else {
            b.classList.add('errou');
            lerTexto("Tente de novo!");
            setTimeout(() => b.classList.remove('errou'), 500);
          }
        };
        opts.appendChild(b);
      });
    }

    // --- JOGOS COM LOUSA PROPORCIONAL CORRIGIDA ---
    const canvas = document.getElementById('paintCanvas');
    const ctx = canvas ? canvas.getContext('2d') : null;
    let desenhando = false, corAtual = '#3B82F6', modoLousa = 'free', imagemPintarCarregada = null, tamanhoPincel = 6, escalaZoomGuia = 0.85;

    function redimensionarCanvas() {
      if (!canvas || !canvas.parentElement) return;
      canvas.width = canvas.parentElement.clientWidth - 16;
      canvas.height = window.innerWidth >= 900 ? 380 : 280;
      if (modoLousa === 'color' && imagemPintarCarregada) desenharContornoNoCanvas(imagemPintarCarregada);
    }

    function setLousaMode(modo) {
      modoLousa = modo;
      document.getElementById('btn-mode-free').classList.remove('active');
      document.getElementById('btn-mode-color').classList.remove('active');
      document.getElementById('coloringSelectGrid').classList.remove('active');
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      if (modo === 'free') {
        document.getElementById('btn-mode-free').classList.add('active');
        imagemPintarCarregada = null;
      } else {
        document.getElementById('btn-mode-color').classList.add('active');
        document.getElementById('coloringSelectGrid').classList.add('active');
        carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786904227/12.png', 'Xexéu', null);
      }
    }

    function carregarContornoPintar(urlImg, nome, btnElemento) {
      document.querySelectorAll('.btn-color-draw').forEach(b => b.classList.remove('selected'));
      if (btnElemento) btnElemento.classList.add('selected');
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      const img = new Image(); img.crossOrigin = "Anonymous"; img.src = urlImg;
      img.onload = () => { imagemPintarCarregada = img; desenharContornoNoCanvas(img); lerTexto("Vamos pintar!"); };
    }

    function desenharContornoNoCanvas(img) {
      const ratio = Math.min(canvas.width / img.width, canvas.height / img.height) * escalaZoomGuia;
      const w = img.width * ratio;
      const h = img.height * ratio;
      const x = (canvas.width / 2) - (w / 2);
      const y = (canvas.height / 2) - (h / 2);

      ctx.clearRect(0, 0, canvas.width, canvas.height);
      ctx.globalAlpha = 0.35; 
      ctx.drawImage(img, x, y, w, h); 
      ctx.globalAlpha = 1.0;
    }

    function mudarCor(c) { corAtual = c; }
    function mudarTamanhoPincel(tam) { tamanhoPincel = tam; }
    function mudarZoomGuia(val) { 
      escalaZoomGuia = val / 100; 
      if (modoLousa === 'color' && imagemPintarCarregada) { 
        desenharContornoNoCanvas(imagemPintarCarregada); 
      } 
    }
    function limparCanvas() { 
      ctx.clearRect(0, 0, canvas.width, canvas.height); 
      if (modoLousa === 'color' && imagemPintarCarregada) desenharContornoNoCanvas(imagemPintarCarregada); 
    }
    
    function salvarFotoDesenho() {
      const tempCanvas = document.createElement('canvas'); tempCanvas.width = canvas.width; tempCanvas.height = canvas.height;
      const tempCtx = tempCanvas.getContext('2d'); tempCtx.fillStyle = '#FFFFFF'; tempCtx.fillRect(0, 0, tempCanvas.width, tempCanvas.height); tempCtx.drawImage(canvas, 0, 0);
      const link = document.createElement('a'); link.download = 'Meu-Desenho.png'; link.href = tempCanvas.toDataURL('image/png'); link.click();
      lerTexto("Desenho salvo com sucesso!");
    }
    
    function getPos(e) { const rect = canvas.getBoundingClientRect(); const clientX = e.touches ? e.touches[0].clientX : e.clientX; const clientY = e.touches ? e.touches[0].clientY : e.clientY; return { x: clientX - rect.left, y: clientY - rect.top }; }

    if (canvas) {
      canvas.addEventListener('mousedown', (e) => { desenhando = true; const p = getPos(e); ctx.beginPath(); ctx.moveTo(p.x, p.y); ctx.strokeStyle = corAtual; ctx.lineWidth = tamanhoPincel; ctx.lineCap = 'round'; });
      canvas.addEventListener('mousemove', (e) => { if(!desenhando) return; const p = getPos(e); ctx.lineTo(p.x, p.y); ctx.stroke(); });
      canvas.addEventListener('mouseup', () => desenhando = false);
      canvas.addEventListener('touchstart', (e) => { desenhando = true; const p = getPos(e); ctx.beginPath(); ctx.moveTo(p.x, p.y); ctx.strokeStyle = corAtual; ctx.lineWidth = tamanhoPincel; ctx.lineCap = 'round'; e.preventDefault(); });
      canvas.addEventListener('touchmove', (e) => { if(!desenhando) return; const p = getPos(e); ctx.lineTo(p.x, p.y); ctx.stroke(); e.preventDefault(); });
      canvas.addEventListener('touchend', () => desenhando = false);
    }
    window.addEventListener('resize', redimensionarCanvas);

    let qContar = 0;
    function carregarJogoContar() {
      qContar = Math.floor(Math.random() * 5) + 1;
      const charSorteado = TODOS_PERSONAGENS[Math.floor(Math.random() * TODOS_PERSONAGENS.length)];
      const display = document.getElementById('countDisplay'); if(!display) return; display.innerHTML = '';
      for (let i = 0; i < qContar; i++) {
        const img = document.createElement('img'); img.src = charSorteado.img; img.style.cssText = 'width:44px; height:44px; object-fit:contain;'; display.appendChild(img);
      }
      const opts = document.getElementById('countOptions'); opts.innerHTML = '';
      for (let n = 1; n <= 6; n++) {
        const btn = document.createElement('button'); btn.className = 'btn-choice'; btn.innerText = n;
        btn.onclick = () => {
          if (n === qContar) {
            btn.classList.add('acertou');
            lerTexto("Muito bem! Acertou!");
            adicionarPontos(5);
            setTimeout(() => { btn.classList.remove('acertou'); carregarJogoContar(); }, 800);
          } else {
            btn.classList.add('errou');
            lerTexto("Tente de novo!");
            setTimeout(() => btn.classList.remove('errou'), 500);
          }
        };
        opts.appendChild(btn);
      }
    }

    let pLetraAtual = null;
    function carregarJogoLetra() {
      pLetraAtual = TODOS_PERSONAGENS[Math.floor(Math.random() * TODOS_PERSONAGENS.length)];
      const nomeLetra = document.getElementById('nome-letra-personagem');
      if(nomeLetra) nomeLetra.innerText = pLetraAtual.nome;
      const imgEl = document.getElementById('img-letra-personagem');
      if(imgEl) { imgEl.src = pLetraAtual.img; }
      
      const container = document.getElementById('opcoes-letras'); if(!container) return; container.innerHTML = '';
      const alfabeto = ['A','B','C','D','E','F','G','H','I','J','L','M','N','P','Q','R','S','T','U','V','X'];
      let opcoes = [pLetraAtual.letra];
      while (opcoes.length < 3) { let l = alfabeto[Math.floor(Math.random() * alfabeto.length)]; if (!opcoes.includes(l)) opcoes.push(l); }
      opcoes.sort(() => Math.random() - 0.5).forEach(l => {
        const btn = document.createElement('button'); btn.className = 'btn-choice'; btn.innerText = l;
        btn.onclick = () => {
          if (l === pLetraAtual.letra) {
            btn.classList.add('acertou');
            lerTexto("Parabéns!");
            adicionarPontos(5);
            setTimeout(() => { btn.classList.remove('acertou'); carregarJogoLetra(); }, 800);
          } else {
            btn.classList.add('errou');
            lerTexto("Tente de novo!");
            setTimeout(() => btn.classList.remove('errou'), 500);
          }
        };
        container.appendChild(btn);
      });
    }

    let cMem = [], pCarta = null, travaMem = false, acertosMem = 0;
    function iniciarMemoria() {
      acertosMem = 0;
      const sorteados = [...TODOS_PERSONAGENS].sort(() => Math.random() - 0.5).slice(0, 4);
      const imgsMem = sorteados.map(p => p.img);
      cMem = [...imgsMem, ...imgsMem].sort(() => Math.random() - 0.5);
      const board = document.getElementById('memoryBoard'); if(!board) return; board.innerHTML = '';
      cMem.forEach(src => {
        const card = document.createElement('div'); card.className = 'memory-card'; card.dataset.img = src; card.innerText = '❓';
        card.onclick = () => {
          if (travaMem || card.classList.contains('flipped')) return;
          card.classList.add('flipped'); card.innerHTML = `<img src="${src}" alt="Carta">`;
          if (!pCarta) pCarta = card;
          else {
            if (pCarta.dataset.img === src) {
              acertosMem++; lerTexto("Encontrou o par!"); pCarta = null; adicionarPontos(3);
              if (acertosMem === 4) { adicionarPontos(10); setTimeout(iniciarMemoria, 1800); }
            } else {
              travaMem = true;
              setTimeout(() => { pCarta.classList.remove('flipped'); pCarta.innerText = '❓'; card.classList.remove('flipped'); card.innerText = '❓'; pCarta = null; travaMem = false; }, 900);
            }
          }
        };
        board.appendChild(card);
      });
    }

    let pQuizAtual = null;
    function carregarQuiz() {
      pQuizAtual = TODOS_PERSONAGENS[Math.floor(Math.random() * TODOS_PERSONAGENS.length)];
      const quizImg = document.getElementById('quiz-img');
      if(quizImg) { quizImg.src = pQuizAtual.img; }
      
      const container = document.getElementById('quiz-options'); if(!container) return; container.innerHTML = '';
      let opcoes = [pQuizAtual.nome];
      while (opcoes.length < 3) { let o = TODOS_PERSONAGENS[Math.floor(Math.random() * TODOS_PERSONAGENS.length)].nome; if (!opcoes.includes(o)) opcoes.push(o); }
      opcoes.sort(() => Math.random() - 0.5).forEach(o => {
        const btn = document.createElement('button'); btn.style.cssText = "padding:8px; border-radius:10px; border:2px solid #CBD5E1; background:#FFF; font-weight:800; cursor:pointer; font-size:12px;"; btn.innerText = o;
        btn.onclick = () => {
          if (o === pQuizAtual.nome) {
            btn.classList.add('acertou');
            lerTexto("Muito bem!");
            adicionarPontos(5);
            setTimeout(() => { btn.classList.remove('acertou'); carregarQuiz(); }, 800);
          } else {
            btn.classList.add('errou');
            lerTexto("Tente novamente!");
            setTimeout(() => btn.classList.remove('errou'), 500);
          }
        };
        container.appendChild(btn);
      });
    }

    function adicionarPontos(qtde) {
      pontosConquista += qtde;
      localStorage.setItem('turminha_pontos', pontosConquista);
      atualizarPlacarConquistas();
    }

    function atualizarPlacarConquistas() {
      const placa = document.getElementById('placar-pontos');
      const med = document.getElementById('medalha-status');
      if(placa) placa.innerText = pontosConquista;
      if(med) {
        if(pontosConquista >= 50) med.innerText = "🌟 Super Fã Mestre";
        else if(pontosConquista >= 20) med.innerText = "⭐ Explorador Experiente";
        else med.innerText = "⭐ Iniciante da Turminha";
      }
    }

    function enviarSuporteReclamacao() {
      const email = document.getElementById('suporteEmail').value.trim();
      const msg = document.getElementById('suporteMensagem').value.trim();
      if (!email || !msg) { alert("Preencha seu e-mail e a mensagem!"); return; }
      
      window.location.href = `mailto:turminhaxexeu@gmail.com?subject=Suporte/Sugestão Portal&body=${encodeURIComponent(msg)}%0D%0A%0D%0AContato: ${email}`;
      exibirAvisoVisual("Abrindo e-mail para envio...");
      document.getElementById('suporteEmail').value = '';
      document.getElementById('suporteMensagem').value = '';
    }

    window.onload = () => { 
      atualizarPlacarConquistas();
      carregarJogoContar();
      carregarJogoLetra();
      iniciarMemoria();
      carregarQuiz();
      verificarStatusVip();
      verificarCookies();
      verificarStatusOnboardingTea();
      carregarPersonagemDoDiaTEA();
      carregarVozes();
      atualizarBotoesTemporizadorGeral();
    };
  </script>
</body>
</html>
