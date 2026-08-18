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

    /* MODO CALMO SENSORIAL PROFUNDO */
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
      max-width: 1120px;
      background: rgba(255, 255, 255, 0.98);
      backdrop-filter: blur(10px);
      border-radius: var(--radius-xl);
      box-shadow: var(--shadow-lg);
      overflow: hidden;
      display: flex;
      flex-direction: column;
      gap: 18px;
      padding-bottom: 24px;
      border: 3px solid #FFFFFF;
    }

    /* CABEÇALHO LÚDICO */
    header {
      padding: 12px 18px;
      background: linear-gradient(135deg, #BAE6FD 0%, #E0F2FE 100%);
      display: flex;
      align-items: center;
      justify-content: space-between;
      border-radius: var(--radius-lg);
      margin: 12px 12px 0;
      box-shadow: var(--shadow-sm);
      gap: 8px;
      flex-wrap: wrap;
    }
    .logo-img { max-width: 130px; height: auto; object-fit: contain; }
    .header-actions { display: flex; align-items: center; gap: 6px; flex-wrap: wrap; }

    .action-btn-pill {
      background: #FFFFFF;
      border: 2px solid var(--primary);
      color: var(--primary-dark);
      font-weight: 800;
      font-size: 12px;
      padding: 8px 12px;
      border-radius: 50px;
      cursor: pointer;
      display: flex;
      align-items: center;
      gap: 5px;
      min-height: 42px;
      box-shadow: var(--shadow-sm);
    }
    .action-btn-pill.muted { background: #FEE2E2; border-color: #EF4444; color: #991B1B; }

    /* MENU DE NAVEGAÇÃO PRINCIPAL */
    .page-nav {
      display: flex;
      gap: 6px;
      background: #F0F9FF;
      padding: 6px;
      border-radius: var(--radius-lg);
      margin: 0 12px;
      border: 2px solid #BAE6FD;
      overflow-x: auto;
      scrollbar-width: none;
    }
    .page-nav::-webkit-scrollbar { display: none; }
    .nav-tab-btn {
      flex: 1;
      min-width: 75px;
      padding: 10px 8px;
      border: none;
      border-radius: var(--radius-md);
      font-weight: 800;
      font-size: 12.5px;
      cursor: pointer;
      background: transparent;
      color: var(--text-muted);
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 5px;
      min-height: 46px;
      white-space: nowrap;
      transition: all 0.2s ease;
    }
    .nav-tab-btn.active {
      background: var(--primary);
      color: #FFFFFF;
      box-shadow: 0 4px 12px rgba(59, 130, 246, 0.35);
    }
    .nav-tab-btn.tea-tab { background: #E0F2FE; color: var(--tea-blue); border: 2px solid #7DD3FC; }
    .nav-tab-btn.tea-tab.active { background: var(--tea-blue); color: #FFF; border-color: transparent; }
    .nav-tab-btn.vip-tab { background: #FEF3C7; color: #92400E; border: 2px solid #FCD34D; }
    .nav-tab-btn.vip-tab.active { background: linear-gradient(135deg, #F59E0B, #D97706); color: #FFF; border-color: transparent; }

    .top-vip-announcement {
      margin: 0 12px -6px;
      background: linear-gradient(135deg, #FEF3C7 0%, #FDE68A 100%);
      border: 2px dashed #F59E0B;
      border-radius: var(--radius-md);
      padding: 8px 12px;
      text-align: center;
      color: #92400E;
      font-size: 12px;
      font-weight: 800;
      cursor: pointer;
    }

    .page-content { display: none; flex-direction: column; gap: 20px; animation: fadeIn 0.25s ease; }
    .page-content.active-page { display: flex; }
    @keyframes fadeIn { from { opacity: 0; transform: translateY(4px); } to { opacity: 1; transform: translateY(0); } }

    /* SEÇÃO 1 & 2: INÍCIO E FAMÍLIAS */
    .banner-intro-grid { display: flex; flex-direction: column; gap: 14px; padding: 0 12px; }
    @media (min-width: 820px) { .banner-intro-grid { display: grid; grid-template-columns: 1fr 1.1fr; align-items: stretch; } }
    .banner-container { width: 100%; border-radius: var(--radius-lg); overflow: hidden; box-shadow: var(--shadow-sm); }
    .banner-img { width: 100%; height: 100%; min-height: 190px; display: block; object-fit: cover; }

    .intro-box {
      background: linear-gradient(135deg, #FEF3C7 0%, #FFFBEB 100%);
      border: 2.5px solid #FCD34D;
      border-radius: var(--radius-lg);
      padding: 16px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      gap: 6px;
    }
    .intro-box h2 { font-size: 17px; font-weight: 900; color: #92400E; display: flex; justify-content: space-between; align-items: center; }
    .intro-box p { font-size: 12.5px; color: #78350F; line-height: 1.5; font-weight: 600; }

    .btn-audio-mini {
      background: linear-gradient(135deg, #FBBF24, #F59E0B);
      border: none;
      border-radius: 50%;
      width: 36px;
      height: 36px;
      min-width: 36px;
      cursor: pointer;
      font-size: 15px;
      display: flex;
      align-items: center;
      justify-content: center;
      color: #FFF;
      box-shadow: 0 2px 6px rgba(245, 158, 11, 0.3);
    }

    .social-round-section { padding: 0 12px; display: flex; justify-content: center; align-items: center; gap: 8px; flex-wrap: wrap; }
    .social-round-btn {
      width: 42px;
      height: 42px;
      border-radius: 50%;
      background: #FFF;
      border: 2px solid #E2E8F0;
      display: flex;
      align-items: center;
      justify-content: center;
      text-decoration: none;
      box-shadow: var(--shadow-sm);
    }
    .social-round-btn img { width: 22px; height: 22px; object-fit: contain; }

    .section-family-container { padding: 0 12px; display: flex; flex-direction: column; gap: 18px; }
    .family-group-title { font-size: 16px; font-weight: 900; color: var(--primary-dark); margin-bottom: 8px; display: flex; align-items: center; justify-content: space-between; }
    
    .floating-cards-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 10px; }
    @media (min-width: 768px) { .floating-cards-grid { grid-template-columns: repeat(4, 1fr); } }
    
    .floating-char-card {
      background: #FFFFFF;
      border-radius: var(--radius-lg);
      padding: 12px 8px;
      text-align: center;
      border: 3px solid #E2E8F0;
      box-shadow: var(--shadow-sm);
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 5px;
      cursor: pointer;
      transition: transform 0.15s ease;
    }
    .floating-char-card:active { transform: scale(0.96); }
    .floating-char-img { width: 70px; height: 70px; object-fit: contain; border-radius: 50%; background: #F8FAFC; padding: 4px; }
    .floating-char-name { font-size: 14px; font-weight: 900; color: var(--text-main); }
    .floating-char-tag { font-size: 9.5px; font-weight: 800; padding: 2px 8px; border-radius: 20px; text-transform: uppercase; }
    .floating-char-desc { font-size: 11px; font-weight: 600; color: var(--text-muted); line-height: 1.35; display: -webkit-box; -webkit-line-clamp: 2; -webkit-box-orient: vertical; overflow: hidden; }

    .card-f1 { border-color: #F472B6; } .card-f1 .floating-char-tag { background: #FCE7F3; color: #DB2777; }
    .card-f2 { border-color: #60A5FA; } .card-f2 .floating-char-tag { background: #DBEAFE; color: #2563EB; }
    .card-avos { border-color: #FBBF24; } .card-avos .floating-char-tag { background: #FEF3C7; color: #D97706; }
    .card-especial { border-color: #A78BFA; } .card-especial .floating-char-tag { background: #EDE9FE; color: #7C3AED; }

    /* SEÇÃO 3: VÍDEOS, MÚSICAS & ACALENTO */
    .video-section { padding: 0 12px; display: flex; flex-direction: column; gap: 14px; }
    .video-card { background: #FFFFFF; border-radius: var(--radius-lg); padding: 14px; box-shadow: var(--shadow-sm); border: 2px solid #E2E8F0; text-align: center; }
    .video-wrapper { position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; border-radius: var(--radius-md); }
    .video-wrapper iframe { position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0; }

    .media-card-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(130px, 1fr)); gap: 10px; margin-top: 10px; }
    .media-item-box {
      background: #F8FAFC;
      border: 2px solid #CBD5E1;
      border-radius: var(--radius-md);
      padding: 12px 8px;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 6px;
      cursor: pointer;
      position: relative;
    }
    .media-item-box.locked { background: #FFFBEB; border-color: #FCD34D; }
    .media-badge-vip { position: absolute; top: 6px; right: 6px; background: #F59E0B; color: #FFF; font-size: 9px; font-weight: 800; padding: 2px 6px; border-radius: 8px; }

    /* SEÇÃO 4: JOGOS & SUB-ABAS */
    .age-group-section { margin: 0 12px; background: #FFFFFF; border-radius: var(--radius-lg); padding: 16px; border: 2px solid #E2E8F0; box-shadow: var(--shadow-sm); }
    .age-title { font-size: 17px; font-weight: 900; color: var(--primary-dark); margin-bottom: 12px; display: flex; align-items: center; justify-content: space-between; }
    
    .conquistas-box {
      background: linear-gradient(135deg, #FEF3C7 0%, #FFFBEB 100%);
      border: 2px solid #FCD34D;
      border-radius: var(--radius-md);
      padding: 10px 14px;
      margin-bottom: 12px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      font-weight: 800;
      color: #92400E;
      font-size: 13px;
    }

    .games-subnav { display: flex; gap: 6px; background: #E0F2FE; padding: 6px; border-radius: var(--radius-md); margin-bottom: 14px; overflow-x: auto; scrollbar-width: none; }
    .games-subnav::-webkit-scrollbar { display: none; }
    .subnav-btn {
      padding: 10px 12px;
      border: none;
      border-radius: 10px;
      font-weight: 800;
      font-size: 12px;
      cursor: pointer;
      background: #FFF;
      color: var(--primary-dark);
      min-height: 42px;
      white-space: nowrap;
    }
    .subnav-btn.active { background: var(--primary); color: #FFF; }

    .game-section-page { display: none; } 
    .game-section-page.active-game-page { display: block; }
    .interactive-card { background: #F8FAFC; border-radius: var(--radius-md); padding: 14px; text-align: center; border: 2px solid #E2E8F0; }

    /* LOUSA MÁGICA PROPORCIONAL COM CONTORNOS */
    .brush-size-selector { display: flex; gap: 6px; justify-content: center; align-items: center; margin-bottom: 10px; flex-wrap: wrap; }
    .btn-brush-size { background: #FFF; border: 2px solid #CBD5E1; border-radius: 10px; font-size: 11.5px; font-weight: 800; padding: 6px 10px; cursor: pointer; min-height: 38px; }
    .btn-brush-size.active { border-color: var(--primary); background: #E0F2FE; color: var(--primary-dark); }
    #paintCanvas { background: #FFF; border: 3px solid var(--primary); border-radius: var(--radius-lg); width: 100%; max-width: 560px; height: 260px; touch-action: none; cursor: crosshair; }
    .palette { display: flex; gap: 8px; justify-content: center; align-items: center; margin-top: 10px; flex-wrap: wrap; }
    .color-dot { width: 34px; height: 34px; border-radius: 50%; border: 3px solid #FFF; box-shadow: 0 2px 6px rgba(0,0,0,0.15); cursor: pointer; }

    .coloring-select-grid { display: flex; justify-content: center; gap: 6px; margin-bottom: 10px; flex-wrap: wrap; max-height: 140px; overflow-y: auto; padding-bottom: 5px; }
    .btn-color-draw { background: #FFF; border: 2px solid #CBD5E1; padding: 6px 10px; border-radius: 10px; font-weight: 700; font-size: 11px; cursor: pointer; display: flex; align-items: center; gap: 4px; }
    .btn-color-draw.selected { border-color: var(--primary); background: #E0F2FE; }
    .btn-color-draw img { width: 20px; height: 20px; object-fit: contain; }

    .game-btn-grid { display: flex; justify-content: center; gap: 8px; flex-wrap: wrap; margin-top: 12px; }
    .btn-choice {
      background: var(--purple);
      color: #FFF;
      border: none;
      padding: 12px 18px;
      font-weight: 800;
      font-size: 15px;
      border-radius: 12px;
      cursor: pointer;
      min-width: 50px;
      min-height: 46px;
      box-shadow: 0 3px 10px rgba(139, 92, 246, 0.25);
    }
    .btn-choice.acertou { background: #10B981 !important; }
    .btn-choice.errou { background: #EF4444 !important; }

    /* MEMÓRIA */
    .memory-board { display: grid; grid-template-columns: repeat(4, 1fr); gap: 8px; margin-top: 10px; max-width: 320px; margin-left: auto; margin-right: auto; }
    .memory-card { aspect-ratio: 1; background: var(--primary); border-radius: 12px; display: flex; align-items: center; justify-content: center; color: #FFF; font-weight: 900; font-size: 20px; cursor: pointer; min-height: 60px; }
    .memory-card.flipped { background: #FFF; border: 2.5px solid var(--primary); }
    .memory-card img { width: 80%; height: 80%; object-fit: contain; }

    /* SEÇÃO 6: ESPAÇO TEA */
    .tea-box { background: var(--tea-light); border: 2px solid #BAE6FD; border-radius: var(--radius-lg); padding: 14px; text-align: center; margin-bottom: 14px; }
    .tea-box h3 { color: var(--tea-blue); font-weight: 900; font-size: 16px; margin-bottom: 4px; }
    
    .emotion-card-grid { display: flex; gap: 8px; justify-content: center; flex-wrap: wrap; margin-top: 8px; }
    .emotion-card {
      background: #FFF;
      border: 2px solid #E2E8F0;
      border-radius: 14px;
      padding: 10px 8px;
      cursor: pointer;
      width: 85px;
      min-height: 85px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }
    .emotion-card span { font-size: 28px; margin-bottom: 2px; }
    .emotion-card p { font-size: 11px; font-weight: 800; }

    .caa-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 8px; margin-top: 10px; }
    .caa-btn {
      background: #FFF;
      border: 2px solid #BAE6FD;
      border-radius: 12px;
      padding: 10px 4px;
      text-align: center;
      cursor: pointer;
      min-height: 70px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }
    .caa-btn span { font-size: 24px; }
    .caa-btn p { font-size: 10.5px; font-weight: 800; color: var(--tea-blue); margin-top: 2px; }

    /* SEÇÃO 7 & 8: CONFIGURAÇÕES E PERFIL */
    .avatar-escolha-grid { display: flex; justify-content: center; gap: 8px; flex-wrap: wrap; margin-top: 8px; }
    .avatar-escolha-btn { width: 48px; height: 48px; border-radius: 50%; border: 2.5px solid #CBD5E1; cursor: pointer; object-fit: contain; background: #FFF; padding: 3px; }
    .avatar-escolha-btn.selecionado { border-color: #F59E0B; transform: scale(1.08); }

    /* SEÇÃO 9: ÁREA VIP */
    .vip-lock-container {
      background: linear-gradient(135deg, #FFFBEB 0%, #FEF3C7 100%);
      border: 3px solid #FCD34D;
      border-radius: var(--radius-lg);
      padding: 18px 14px;
      text-align: center;
    }
    .vip-price-tag { display: inline-block; background: #F59E0B; color: #FFF; font-weight: 900; font-size: 13.5px; padding: 6px 16px; border-radius: 30px; margin: 10px 0; }
    .vip-grid-forms { display: grid; grid-template-columns: 1fr; gap: 12px; max-width: 680px; margin: 12px auto 0; }
    @media (min-width: 640px) { .vip-grid-forms { grid-template-columns: 1fr 1fr; } }
    
    .vip-form-box { background: #FFF; padding: 14px; border-radius: var(--radius-md); border: 2px solid #FCD34D; text-align: left; }
    .vip-form-box h4 { font-size: 14px; color: #92400E; margin-bottom: 6px; font-weight: 900; }
    .vip-input { width: 100%; padding: 9px; font-size: 13px; border: 2px solid #E2E8F0; border-radius: 10px; margin-bottom: 8px; outline: none; }
    
    .btn-vip-checkout {
      background: linear-gradient(135deg, #F59E0B 0%, #D97706 100%);
      color: #FFF;
      font-weight: 800;
      font-size: 13.5px;
      padding: 11px 14px;
      border-radius: 12px;
      border: none;
      cursor: pointer;
      width: 100%;
      text-decoration: none;
      display: block;
      text-align: center;
      min-height: 44px;
    }

    /* SEÇÃO 10 & 11: ROTINA E SUPER FORÇA */
    .rotina-item { display: flex; justify-content: space-between; align-items: center; background: #FFF; border: 2px solid #E2E8F0; padding: 8px 12px; border-radius: 10px; margin-bottom: 6px; }
    .rotina-item.concluido { background: #DCFCE7; border-color: #86EFAC; opacity: 0.8; }
    .rotina-item.concluido .rotina-texto { text-decoration: line-through; color: #166534; }

    /* SEÇÃO 12: BIBLIOTECA */
    .book-card-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(130px, 1fr)); gap: 10px; margin-top: 10px; }
    .book-card { background: #FFF; border: 2px solid #E2E8F0; border-radius: var(--radius-md); padding: 12px; text-align: center; cursor: pointer; }

    /* MODAL DE PERSONAGEM (FICHA COMPLETA) */
    .char-modal {
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
      padding: 14px;
    }
    .char-modal.active { display: flex; }
    .char-modal-box {
      background: #FFF;
      border-radius: var(--radius-lg);
      padding: 20px;
      max-width: 380px;
      width: 100%;
      text-align: center;
      border: 3px solid var(--primary);
      position: relative;
    }
    .char-modal-close { position: absolute; top: 12px; right: 12px; background: #F1F5F9; border: none; width: 30px; height: 30px; border-radius: 50%; font-weight: bold; cursor: pointer; }

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
      padding: 20px;
      border-radius: var(--radius-lg);
      text-align: center;
      max-width: 350px;
      width: 100%;
      border: 3px solid #F59E0B;
    }

    #visualToast {
      position: fixed;
      bottom: 14px;
      left: 50%;
      transform: translateX(-50%) translateY(100px);
      background: #0F172A;
      color: #FFF;
      padding: 9px 16px;
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

    footer { text-align: center; padding: 14px 14px 6px; border-top: 1px solid #E2E8F0; font-size: 11px; color: var(--text-muted); font-weight: 600; }
  </style>
</head>
<body onclick="desbloquearAudioMobileOnce()">

  <div id="visualToast">Aviso do sistema</div>

  <!-- MODAL: FICHA DO PERSONAGEM -->
  <div id="modalFichaPersonagem" class="char-modal">
    <div class="char-modal-box">
      <button class="char-modal-close" onclick="fecharFichaPersonagem()">✕</button>
      <img id="ficha-img" src="" alt="Personagem" style="width: 80px; height: 80px; object-fit: contain; margin-bottom: 8px;">
      <h3 id="ficha-nome" style="color: var(--primary-dark); font-weight: 900; font-size: 18px;"></h3>
      <p id="ficha-apelido" style="color: var(--purple); font-weight: 800; font-size: 12px; margin-bottom: 10px;"></p>
      
      <button id="btnFichaOuvir" class="btn-choice" style="padding: 6px 14px; font-size: 12px; margin-bottom: 12px; background: #F59E0B;">🔊 Ouvir Apresentação</button>
      
      <div style="text-align: left; background: #F8FAFC; padding: 10px; border-radius: 10px; border: 1.5px solid #E2E8F0; font-size: 12px; display: flex; flex-direction: column; gap: 6px;">
        <p><strong>🌟 Quem sou eu?</strong> <span id="ficha-quem"></span></p>
        <p><strong>💖 O que eu gosto?</strong> <span id="ficha-gosto"></span></p>
        <p><strong>💬 Minha frase:</strong> <em>"<span id="ficha-frase"></span>"</em></p>
      </div>
    </div>
  </div>

  <!-- PARENTAL GATE (PROTEÇÃO PARA ÁREA DOS PAIS / VIP) -->
  <div id="modalParentalGate" class="parent-modal">
    <div class="parent-box">
      <h3 style="color: #92400E; font-size: 16px; margin-bottom: 4px; font-weight: 900;">🔒 Acesso dos Responsáveis</h3>
      <p style="font-size: 12px; color: #475569; margin-bottom: 10px;">Resolva a conta para entrar:</p>
      <div id="desafioMatematicoTexto" style="font-size: 20px; font-weight: 900; color: #1E293B; margin: 8px 0;">3 + 4 = ?</div>
      <input type="number" id="respostaDesafio" style="width: 80px; padding: 6px; font-size: 16px; text-align: center; border: 2px solid #CBD5E1; border-radius: 8px; margin-bottom: 10px; font-weight: 800;" placeholder="?">
      <div style="display: flex; gap: 8px; justify-content: center;">
        <button onclick="fecharParentalGate()" style="padding: 8px 12px; border: none; border-radius: 8px; background: #E2E8F0; font-weight: 800; cursor: pointer; font-size: 12px;">Voltar</button>
        <button onclick="verificarParentalGate()" style="padding: 8px 16px; border: none; border-radius: 8px; background: #F59E0B; color: #FFF; font-weight: 800; cursor: pointer; font-size: 12px;">Entrar ➔</button>
      </div>
    </div>
  </div>

  <div class="floating-vip-badge" onclick="abrirAreaProtegida('vip')">
    <span>⭐</span>
    <span>Área VIP (R$ 6,00)</span>
  </div>

  <div class="app-container">

    <!-- CABEÇALHO GERAL -->
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
        <button class="action-btn-pill" onclick="mudarPagina('config')">
          <span>⚙️</span>
        </button>
        <button class="action-btn-pill" onclick="mudarPagina('perfil')">
          <span>👤</span>
        </button>
      </div>
    </header>

    <!-- NAVEGAÇÃO PRINCIPAL -->
    <nav class="page-nav">
      <button id="btn-tab-inicio" class="nav-tab-btn active" onclick="mudarPagina('inicio')">🏠 Início</button>
      <button id="btn-tab-videos" class="nav-tab-btn" onclick="mudarPagina('videos')">🎬 Vídeos</button>
      <button id="btn-tab-jogos" class="nav-tab-btn" onclick="mudarPagina('jogos')">🎮 Jogos</button>
      <button id="btn-tab-tea" class="nav-tab-btn tea-tab" onclick="mudarPagina('tea')">🧩 Espaço TEA</button>
      <button id="btn-tab-livros" class="nav-tab-btn" onclick="mudarPagina('livros')">📚 Livros</button>
      <button id="btn-tab-rotina" class="nav-tab-btn" onclick="mudarPagina('rotina')">📅 Rotina</button>
      <button id="btn-tab-conquistas" class="nav-tab-btn" onclick="mudarPagina('conquistas')">🏆 Conquistas</button>
      <button id="btn-tab-vip" class="nav-tab-btn vip-tab" onclick="abrirAreaProtegida('vip')">⭐ Área VIP</button>
    </nav>

    <div class="top-vip-announcement" onclick="abrirAreaProtegida('vip')">
      <span>⭐ Desbloqueie todo o Drive Pedagógico e Ferramentas TEA por R$ 6,00/mês! 💖</span>
    </div>

    <!-- SEÇÃO 1 & 2: INÍCIO E CONHEÇA A TURMINHA -->
    <main id="pagina-inicio" class="page-content active-page">
      <section class="banner-intro-grid">
        <div class="banner-container">
          <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994339/BANNER_SITE_TURMINHA_DO_XEXEU.png" alt="Capa da Turminha do Xexéu" class="banner-img">
        </div>
        <div class="intro-box">
          <h2>
            <span>✨ Educando com Alegria e Amor</span>
            <button class="btn-audio-mini" onclick="lerTexto('Mais do que um nome divertido, a Turminha do Xexéu é o nosso jeito de honrar as raízes e a história da nossa família.')" title="Ouvir">🔊</button>
          </h2>
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
      </section>

      <section class="section-family-container">
        <div>
          <h3 class="family-group-title">
            <span>✨ Símbolo e Mascotes</span>
            <button class="btn-audio-mini" onclick="lerTexto('Toque nos personagens para abrir a ficha completa!')">🔊</button>
          </h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-especial" onclick="abrirFichaPersonagem('Xexéu')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_XEXEU.png" class="floating-char-img" alt="Xexéu">
              <span class="floating-char-name">Xexéu</span>
              <span class="floating-char-tag">Mascote Oficial</span>
              <p class="floating-char-desc">Pássaro azul de boina amarela e guardião da história.</p>
            </div>
            <div class="floating-char-card card-especial" onclick="abrirFichaPersonagem('Capilé')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994882/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_CAPILE.png" class="floating-char-img" alt="Capilé">
              <span class="floating-char-name">Capilé</span>
              <span class="floating-char-tag">O Companheiro</span>
              <p class="floating-char-desc">Cachorrinho fofo com coleira azul e osso dourado.</p>
            </div>
          </div>
        </div>

        <div>
          <h3 class="family-group-title">
            <span>💖 Casa da Maya e do Theo</span>
            <button class="btn-audio-mini" onclick="lerTexto('Casa da Maya e do Theo.')">🔊</button>
          </h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-f1" onclick="abrirFichaPersonagem('Maya')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994884/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_MAYA.png" class="floating-char-img" alt="Maya">
              <span class="floating-char-name">Maya</span>
              <span class="floating-char-tag">Mãe & Guia</span>
              <p class="floating-char-desc">Organizada, amorosa e porto seguro da família.</p>
            </div>
            <div class="floating-char-card card-f1" onclick="abrirFichaPersonagem('Theo')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_THEO.png" class="floating-char-img" alt="Theo">
              <span class="floating-char-name">Theo</span>
              <span class="floating-char-tag">Pai Protetor</span>
              <p class="floating-char-desc">Calmo, paciente e carinhoso com as filhas.</p>
            </div>
            <div class="floating-char-card card-f1" onclick="abrirFichaPersonagem('Nina')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_NINA.png" class="floating-char-img" alt="Nina">
              <span class="floating-char-name">Nina</span>
              <span class="floating-char-tag">Super Esperta</span>
              <p class="floating-char-desc">Cabelos cacheados e curiosidade sem fim.</p>
            </div>
            <div class="floating-char-card card-f1" onclick="abrirFichaPersonagem('Iza')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_IZA.png" class="floating-char-img" alt="Iza">
              <span class="floating-char-name">Iza</span>
              <span class="floating-char-tag">A Vaidosa</span>
              <p class="floating-char-desc">Vestido rosa e um coração muito doce.</p>
            </div>
          </div>
        </div>

        <div>
          <h3 class="family-group-title">
            <span>⚡ Casa do Sam e da Lia</span>
            <button class="btn-audio-mini" onclick="lerTexto('Casa do Sam e da Lia.')">🔊</button>
          </h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-f2" onclick="abrirFichaPersonagem('Sam')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_SAM.png" class="floating-char-img" alt="Sam">
              <span class="floating-char-name">Sam</span>
              <span class="floating-char-tag">Pai Inventor</span>
              <p class="floating-char-desc">Cria invenções e novas brincadeiras para os filhos.</p>
            </div>
            <div class="floating-char-card card-f2" onclick="abrirFichaPersonagem('Lia')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994884/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_LIA.png" class="floating-char-img" alt="Lia">
              <span class="floating-char-name">Lia</span>
              <span class="floating-char-tag">Mãe Alegria</span>
              <p class="floating-char-desc">Estilosa e cheia de energia positiva no dia a dia.</p>
            </div>
            <div class="floating-char-card card-f2" onclick="abrirFichaPersonagem('Joca')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_JOCA.png" class="floating-char-img" alt="Joca">
              <span class="floating-char-name">Joca</span>
              <span class="floating-char-tag">O Divertido</span>
              <p class="floating-char-desc">Garoto de camiseta verde, engraçado e leal.</p>
            </div>
            <div class="floating-char-card card-f2" onclick="abrirFichaPersonagem('Leo')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_LEO.png" class="floating-char-img" alt="Leo">
              <span class="floating-char-name">Leo</span>
              <span class="floating-char-tag">Explorador Focado</span>
              <p class="floating-char-desc">Observador detalhista e guia do Espaço TEA.</p>
            </div>
          </div>
        </div>

        <div>
          <h3 class="family-group-title">
            <span>👵👴 Os Avós</span>
            <button class="btn-audio-mini" onclick="lerTexto('Os queridos Avós da Turminha.')">🔊</button>
          </h3>
          <div class="floating-cards-grid">
            <div class="floating-char-card card-avos" onclick="abrirFichaPersonagem('Beto')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_VOVO_BETO.png" class="floating-char-img" alt="Vovô Beto">
              <span class="floating-char-name">Vovô Beto</span>
              <span class="floating-char-tag">Vovô Coruja</span>
              <p class="floating-char-desc">Óculos quadrados, risada solta e bom humor.</p>
            </div>
            <div class="floating-char-card card-avos" onclick="abrirFichaPersonagem('Hilda')">
              <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_VOVO_HILDA.png" class="floating-char-img" alt="Vovó Hilda">
              <span class="floating-char-name">Vovó Hilda</span>
              <span class="floating-char-tag">Vovó Acolhedora</span>
              <p class="floating-char-desc">Óculos redondos e abraços inesquecíveis.</p>
            </div>
          </div>
        </div>
      </section>
    </main>

    <!-- SEÇÃO 3: VÍDEOS, MÚSICAS & ACALENTO -->
    <main id="pagina-videos" class="page-content">
      <section class="video-section">
        <div class="video-card">
          <h3 style="font-size: 16px; font-weight: 900; color: var(--primary-dark); margin-bottom: 10px;">📺 Episódios em Destaque</h3>
          <div class="video-wrapper">
            <iframe src="https://www.youtube-nocookie.com/embed/videosseries?list=PLh42qmbnReoE_pM4lig3DpJaNGWqoT9uJ" allowfullscreen></iframe>
          </div>
        </div>

        <div class="interactive-card">
          <h4 style="font-size: 15px; font-weight: 900; color: var(--purple); margin-bottom: 6px;">🎵 Músicas da Turminha</h4>
          <div class="media-card-grid">
            <div class="media-item-box" onclick="lerTexto('Reproduzindo Música 1')">
              <span style="font-size:24px;">🎵</span>
              <strong style="font-size:12px;">Música 1</strong>
              <span style="font-size:10px; color: #16A34A; font-weight:800;">GRÁTIS</span>
            </div>
            <div class="media-item-box" onclick="lerTexto('Reproduzindo Música 2')">
              <span style="font-size:24px;">🎵</span>
              <strong style="font-size:12px;">Música 2</strong>
              <span style="font-size:10px; color: #16A34A; font-weight:800;">GRÁTIS</span>
            </div>
            <div class="media-item-box locked" onclick="abrirAreaProtegida('vip')">
              <span class="media-badge-vip">👑 VIP</span>
              <span style="font-size:24px;">🔒</span>
              <strong style="font-size:12px;">Música Especial</strong>
              <span style="font-size:10px; color: #D97706; font-weight:800;">Desbloquear</span>
            </div>
          </div>
        </div>

        <div class="interactive-card">
          <h4 style="font-size: 15px; font-weight: 900; color: var(--tea-blue); margin-bottom: 6px;">🌙 Sons & Acalento</h4>
          <div class="media-card-grid">
            <div class="media-item-box" onclick="tocarSomReal('https://cdn.freesound.org/previews/237/237729_4284968-lq.mp3')">
              <span style="font-size:24px;">🌧️</span>
              <strong style="font-size:12px;">Chuva Suave</strong>
              <span style="font-size:10px; color:#16A34A; font-weight:800;">GRÁTIS</span>
            </div>
            <div class="media-item-box" onclick="tocarSomReal('https://cdn.freesound.org/previews/322/322744_5121236-lq.mp3')">
              <span style="font-size:24px;">🐦</span>
              <strong style="font-size:12px;">Passarinhos</strong>
              <span style="font-size:10px; color:#16A34A; font-weight:800;">GRÁTIS</span>
            </div>
            <div class="media-item-box locked" onclick="abrirAreaProtegida('vip')">
              <span class="media-badge-vip">👑 VIP</span>
              <span style="font-size:24px;">🌊</span>
              <strong style="font-size:12px;">Ondas do Mar</strong>
              <span style="font-size:10px; color:#D97706; font-weight:800;">VIP</span>
            </div>
          </div>
          <div style="margin-top: 12px;">
            <a href="https://open.spotify.com/intl-pt/artist/6ykKQ3uP6Wl2REylKJAdJ6" target="_blank" style="display:inline-flex; align-items:center; gap:6px; background:#10B981; color:#FFF; padding:8px 16px; border-radius:20px; text-decoration:none; font-weight:800; font-size:12px;">
              <span>▶️</span> Ouvir Rádio no Spotify
            </a>
          </div>
        </div>
      </section>
    </main>

    <!-- SEÇÃO 4 & 5: JOGOS & LOUSA MÁGICA -->
    <main id="pagina-jogos" class="page-content">
      <div class="age-group-section">
        <h3 class="age-title">
          <span>🎮 Central de Jogos</span>
          <button class="btn-audio-mini" onclick="lerTexto('Bem-vindo aos jogos educativos da Turminha!')">🔊</button>
        </h3>

        <nav class="games-subnav">
          <button id="subtab-lousa" class="subnav-btn active" onclick="mudarSubJogo('lousa')">🎨 Lousa</button>
          <button id="subtab-contar" class="subnav-btn" onclick="mudarSubJogo('contar')">🔢 Contar</button>
          <button id="subtab-letras" class="subnav-btn" onclick="mudarSubJogo('letras')">🔤 Letras</button>
          <button id="subtab-memoria" class="subnav-btn" onclick="mudarSubJogo('memoria')">🧠 Memória</button>
          <button id="subtab-quiz" class="subnav-btn" onclick="mudarSubJogo('quiz')">❓ Quiz</button>
        </nav>

        <!-- 5. LOUSA MÁGICA COM 12 PERSONAGENS -->
        <div id="game-lousa" class="game-section-page active-game-page interactive-card">
          <h4 style="font-weight: 800; margin-bottom: 8px; font-size: 15px;">🎨 Lousa Mágica & Colorir</h4>
          <div class="coloring-select-grid">
            <button class="btn-color-draw selected" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786994876/DESENHOS_DA_LOUSA_XEXEU.png', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_XEXEU.png"> Xexéu</button>
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786994874/DESENHOS_DA_LOUSA_CAPILE.png', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994882/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_CAPILE.png"> Capilé</button>
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786994875/DESENHOS_DA_LOUSA_MAYA.png', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994884/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_MAYA.png"> Maya</button>
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786994877/DESENHOS_DA_LOUSA_THEO.png', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_THEO.png"> Theo</button>
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786994876/DESENHOS_DA_LOUSA_NINA.png', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_NINA.png"> Nina</button>
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786994873/DESENHOS_DA_LOUSA_IZA.png', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_IZA.png"> Iza</button>
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786994876/DESENHOS_DA_LOUSA_SAM.png', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_SAM.png"> Sam</button>
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786994875/DESENHOS_DA_LOUSA_LIA.png', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994884/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_LIA.png"> Lia</button>
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786994874/DESENHOS_DA_LOUSA_JOCA.png', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_JOCA.png"> Joca</button>
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786994875/DESENHOS_DA_LOUSA_LEO.png', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_LEO.png"> Leo</button>
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786994876/DESENHOS_DA_LOUSA_VOVO_BETO.png', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_VOVO_BETO.png"> Beto</button>
            <button class="btn-color-draw" onclick="carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786994877/DESENHOS_DA_LOUSA_VOVO_HILDA.png', this)"><img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_VOVO_HILDA.png"> Hilda</button>
          </div>
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
            <button onclick="limparCanvas()" style="padding: 6px 12px; font-weight: 800; border-radius: 8px; border: none; background: #FEE2E2; color: #DC2626; cursor: pointer; font-size: 11.5px;">Limpar 🗑️</button>
            <button onclick="salvarFotoDesenho()" style="padding: 6px 12px; font-weight: 800; border-radius: 8px; border: none; background: #D1FAE5; color: #065F46; cursor: pointer; font-size: 11.5px;">Salvar 📸</button>
          </div>
        </div>

        <!-- CONTAR -->
        <div id="game-contar" class="game-section-page interactive-card">
          <h4 style="font-weight: 800; font-size: 15px; margin-bottom: 4px;">🔢 Vamos Contar?</h4>
          <div id="countDisplay" style="display: flex; justify-content: center; align-items: center; gap: 8px; margin: 14px 0; min-height: 65px; flex-wrap: wrap;"></div>
          <div id="countOptions" class="game-btn-grid"></div>
        </div>

        <!-- LETRAS -->
        <div id="game-letras" class="game-section-page interactive-card">
          <h4 style="font-weight: 800; font-size: 15px; margin-bottom: 4px;">🔤 Qual é a Primeira Letra?</h4>
          <p style="font-size: 13px; font-weight: 700;">Nome: <strong id="nome-letra-personagem" style="color: var(--purple);">Xexéu</strong></p>
          <img id="img-letra-personagem" src="" alt="Personagem" style="width: 80px; height: 80px; object-fit: contain; margin: 8px 0;">
          <div id="opcoes-letras" class="game-btn-grid"></div>
        </div>

        <!-- MEMÓRIA -->
        <div id="game-memoria" class="game-section-page interactive-card">
          <h4 style="font-weight: 800; font-size: 15px; margin-bottom: 4px;">🧠 Jogo da Memória</h4>
          <div id="memoryBoard" class="memory-board"></div>
        </div>

        <!-- QUIZ -->
        <div id="game-quiz" class="game-section-page interactive-card">
          <h4 style="font-weight: 800; font-size: 15px; margin-bottom: 4px;">❓ Quem é este Personagem?</h4>
          <img id="quiz-img" src="" alt="Quiz" style="width: 75px; height: 75px; object-fit: contain; margin: 8px 0;">
          <div id="quiz-options" class="game-btn-grid"></div>
        </div>
      </div>
    </main>

    <!-- SEÇÃO 6: ESPAÇO TEA (GUIADO PELO LEO) -->
    <main id="pagina-tea" class="page-content">
      <div class="age-group-section">
        <div class="tea-box">
          <div style="display:flex; align-items:center; justify-content:center; gap:10px; margin-bottom:6px;">
            <img src="https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_LEO.png" alt="Leo" style="width:45px; height:45px; object-fit:contain;">
            <h3 style="margin:0;">🧩 Espaço TEA com o Leo</h3>
          </div>
          <p style="font-size: 12px; color: #475569; font-weight: 600;">"Oi! Eu sou o Leo. Vamos fazer tudo com calma?"</p>
        </div>

        <!-- CARTÕES DE COMUNICAÇÃO CAA -->
        <div class="interactive-card" style="border-color: #BAE6FD; margin-bottom: 14px;">
          <h4 style="color: var(--tea-blue); font-weight: 800; font-size: 14px; margin-bottom: 6px;">🗣️ Cartões de Fala (CAA)</h4>
          <div class="caa-grid">
            <div class="caa-btn" onclick="lerTexto('Eu quero água, por favor.')"><span>💧</span><p>Água</p></div>
            <div class="caa-btn" onclick="lerTexto('Estou com fome.')"><span>🍎</span><p>Comer</p></div>
            <div class="caa-btn" onclick="lerTexto('Preciso ir ao banheiro.')"><span>🚽</span><p>Banheiro</p></div>
            <div class="caa-btn" onclick="lerTexto('Quero brincar.')"><span>🧸</span><p>Brincar</p></div>
            <div class="caa-btn" onclick="lerTexto('Quero descansar.')"><span>💤</span><p>Descansar</p></div>
            <div class="caa-btn" onclick="lerTexto('Preciso de ajuda.')"><span>🤝</span><p>Ajuda</p></div>
          </div>
        </div>

        <!-- EMOÇÕES -->
        <div class="interactive-card" style="border-color: #BAE6FD;">
          <h4 style="color: var(--tea-blue); font-weight: 800; font-size: 14px; margin-bottom: 6px;">❤️ Como estou me sentindo?</h4>
          <div class="emotion-card-grid">
            <div class="emotion-card" onclick="responderMinhaEmocao('Feliz')"><span>😄</span><p style="color: #16A34A;">Feliz</p></div>
            <div class="emotion-card" onclick="responderMinhaEmocao('Calmo')"><span>😌</span><p style="color: var(--tea-blue);">Calmo</p></div>
            <div class="emotion-card" onclick="responderMinhaEmocao('Triste')"><span>😢</span><p style="color: #475569;">Triste</p></div>
            <div class="emotion-card" onclick="responderMinhaEmocao('Bravo')"><span>😤</span><p style="color: #DC2626;">Bravo</p></div>
          </div>
        </div>
      </div>
    </main>

    <!-- SEÇÃO 7 & 8: CONFIGURAÇÕES E PERFIL -->
    <main id="pagina-config" class="page-content">
      <div class="age-group-section">
        <h3 class="age-title">⚙️ Configurações & Acessibilidade</h3>
        <div class="interactive-card" style="text-align:left; display:flex; flex-direction:column; gap:10px;">
          <label style="font-size:13px; font-weight:800;">🔊 Volume e Voz:</label>
          <button class="action-btn-pill" onclick="alternarAudioGlobal()">Alternar Voz do Portal</button>
          
          <label style="font-size:13px; font-weight:800; margin-top:8px;">🌙 Modo Calmo Sensorial:</label>
          <button class="action-btn-pill" onclick="toggleSensoryMode()">Alternar Modo Calmo</button>
        </div>
      </div>
    </main>

    <main id="pagina-perfil" class="page-content">
      <div class="age-group-section">
        <h3 class="age-title">👤 Perfil da Criança</h3>
        <div class="interactive-card">
          <p style="font-size:12.5px; font-weight:700; margin-bottom:10px;">Escolha o avatar do seu amiguinho favorito:</p>
          <div id="avatarEscolhaGrid" class="avatar-escolha-grid"></div>
        </div>
      </div>
    </main>

    <!-- SEÇÃO 10 & 11: ROTINA / LEMBRETE DE CUIDADO -->
    <main id="pagina-rotina" class="page-content">
      <div class="age-group-section">
        <h3 class="age-title">📅 Rotina & Cuidados</h3>
        <div class="interactive-card" style="text-align:left; margin-bottom:12px;">
          <h4 style="color:#166534; font-size:14px; font-weight:900; margin-bottom:8px;">💊 Lembrete de Cuidado</h4>
          <p style="font-size:11.5px; color:#15803D; margin-bottom:8px;">Lembrete visual diário de alimentação ou cuidados.</p>
          <div class="rotina-item">
            <span class="rotina-texto">🍎 Hora do lanche saudável (15:00)</span>
            <button onclick="this.parentElement.classList.toggle('concluido')" style="background:#10B981; color:#FFF; border:none; padding:4px 8px; border-radius:6px; font-weight:800; cursor:pointer; font-size:11px;">✓ Feito</button>
          </div>
        </div>

        <div class="interactive-card" style="text-align:left;">
          <h4 style="font-size:14px; font-weight:900; margin-bottom:8px;">☀️ Minha Rotina Diária</h4>
          <div class="rotina-item"><span class="rotina-texto">☀️ Manhã: Escovar os dentes</span><button onclick="this.parentElement.classList.toggle('concluido')" style="background:#10B981; color:#FFF; border:none; padding:4px 8px; border-radius:6px; font-weight:800; cursor:pointer; font-size:11px;">✓ Feito</button></div>
          <div class="rotina-item"><span class="rotina-texto">🏫 Escola / Atividades</span><button onclick="this.parentElement.classList.toggle('concluido')" style="background:#10B981; color:#FFF; border:none; padding:4px 8px; border-radius:6px; font-weight:800; cursor:pointer; font-size:11px;">✓ Feito</button></div>
          <div class="rotina-item"><span class="rotina-texto">🌙 Sono tranquilo</span><button onclick="this.parentElement.classList.toggle('concluido')" style="background:#10B981; color:#FFF; border:none; padding:4px 8px; border-radius:6px; font-weight:800; cursor:pointer; font-size:11px;">✓ Feito</button></div>
        </div>
      </div>
    </main>

    <!-- SEÇÃO 12: LIVROS -->
    <main id="pagina-livros" class="page-content">
      <div class="age-group-section">
        <h3 class="age-title">📚 Biblioteca da Turminha</h3>
        <div class="book-card-grid">
          <div class="book-card" onclick="lerTexto('O Abraço de Algodão doce')">
            <span style="font-size:32px;">📖</span>
            <strong style="font-size:12px; display:block; margin:4px 0;">O Abraço Doce</strong>
            <span style="font-size:10px; color:#16A34A; font-weight:800;">GRÁTIS</span>
          </div>
          <div class="book-card" onclick="abrirAreaProtegida('vip')">
            <span style="font-size:32px;">👑</span>
            <strong style="font-size:12px; display:block; margin:4px 0;">Aventuras do Xexéu</strong>
            <span style="font-size:10px; color:#D97706; font-weight:800;">VIP</span>
          </div>
          <div class="book-card" style="border-style:dashed;">
            <span style="font-size:32px;">🚧</span>
            <strong style="font-size:12px; display:block; margin:4px 0;">Em Breve</strong>
            <span style="font-size:10px; color:#64748B;">Novas histórias</span>
          </div>
        </div>
      </div>
    </main>

    <!-- SEÇÃO 13: CONQUISTAS & CERTIFICADO -->
    <main id="pagina-conquistas" class="page-content">
      <div class="age-group-section">
        <h3 class="age-title">🏆 Minhas Conquistas</h3>
        <div class="conquistas-box">
          <span>⭐ Seus Pontos: <strong id="placar-pontos-2">0</strong></span>
          <span id="medalha-status-2">Iniciante</span>
        </div>

        <div class="interactive-card" style="border: 2.5px double #F59E0B; background: #FFFBEB;">
          <h4 style="color:#92400E; font-size:16px; font-weight:900; margin-bottom:6px;">🎓 Certificado de Super Fã</h4>
          <input type="text" id="nome-certificado-input" placeholder="Digite o nome da criança" style="padding:8px; border-radius:8px; border:2px solid #FCD34D; outline:none; margin-bottom:8px; width:80%; max-width:260px;">
          <br>
          <button onclick="gerarCertificadoGeral()" style="background:#D97706; color:#FFF; border:none; padding:8px 16px; border-radius:8px; font-weight:800; cursor:pointer;">Gerar Certificado ⭐</button>
          
          <div id="boxCertificadoResultado" style="display:none; margin-top:12px; padding:12px; background:#FFF; border-radius:10px; border:2px solid #FCD34D;">
            <h3 style="color:#1D4ED8; text-transform:uppercase;" id="txtNomeCertificado"></h3>
            <p style="font-weight:700; color:#B45309; font-size:12.5px;">É oficialmente Super Fã da Turminha do Xexéu! 🌟</p>
          </div>
        </div>
      </div>
    </main>

    <!-- SEÇÃO 9: ÁREA VIP (PAIS & ASSINANTES) -->
    <main id="pagina-vip" class="page-content">
      <div class="age-group-section">
        <div class="vip-lock-container">
          <h3>⭐ Clube VIP da Turminha do Xexéu</h3>
          <div class="vip-price-tag">Assinatura: R$ 6,00 / mês</div>
          
          <div style="background:#FFF; padding:12px; border-radius:12px; border:2px dashed #F59E0B; text-align:left; font-size:12px; margin:10px 0; color:#78350F;">
            <strong style="display:block; margin-bottom:4px;">👑 O VIP Desbloqueia para sua Família:</strong>
            <ul style="margin-left:18px; line-height:1.6;">
              <li>📁 <strong>Drive Pedagógico Completo:</strong> Materiais em PDF para imprimir.</li>
              <li>🧩 <strong>Espaço TEA Avançado:</strong> CAA editável e temporizador expandido.</li>
              <li>🎵 <strong>Músicas e Sons de Acalento:</strong> Acesso completo e sem travas.</li>
              <li>🏆 <strong>Certificados Personalizados:</strong> Vários modelos para imprimir.</li>
            </ul>
          </div>

          <div class="vip-grid-forms">
            <div class="vip-form-box">
              <h4>✨ Quero Assinar o VIP</h4>
              <input type="email" id="cad-email" class="vip-input" placeholder="Seu e-mail">
              <input type="password" id="cad-senha" class="vip-input" placeholder="Crie uma senha parental">
              <a href="https://pay.kiwify.com.br/avOqrEg" target="_blank" class="btn-vip-checkout" onclick="salvarECadastrar()">Quero Ser VIP por R$ 6,00 💳</a>
            </div>

            <div class="vip-form-box" style="border-color: #CBD5E1;">
              <h4 style="color: #1E293B;">🔑 Já sou Assinante</h4>
              <input type="email" id="log-email" class="vip-input" placeholder="E-mail cadastrado">
              <input type="password" id="log-senha" class="vip-input" placeholder="Sua senha">
              <button onclick="fazerLogin()" style="width:100%; padding: 11px; background: #3B82F6; color: #FFF; border: none; border-radius: 10px; font-weight: 800; cursor: pointer;">Entrar no Painel</button>
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
    let somAcalentoAtual = null;

    const SENHA_MESTRA = "65628467";

    /* TODOS OS PERSONAGENS ATUALIZADOS COM NOVOS LINKS DE AVATARES */
    const PERSONAGENS = [
      { 
        nome: 'Xexéu', 
        img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_XEXEU.png', 
        letra: 'X', 
        tag: 'Mascote Oficial',
        quem: 'O pássaro azul de boina amarela e guardião alegre da história!',
        gosto: 'De cantar, voar alto e contar histórias para os amigos.',
        frase: 'Educando com alegria, amor e imaginação!'
      },
      { 
        nome: 'Capilé', 
        img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994882/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_CAPILE.png', 
        letra: 'C', 
        tag: 'O Companheiro',
        quem: 'O cachorrinho fiel de orelhas grandes e coleira azul-celeste.',
        gosto: 'De correr pelo jardim e ganhar carinho na barriga.',
        frase: 'Au au! Sempre pronto para uma nova brincadeira!'
      },
      { 
        nome: 'Maya', 
        img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994884/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_MAYA.png', 
        letra: 'M', 
        tag: 'Mãe & Guia',
        quem: 'Mãe dedicada da Iza e da Nina, organizada e protetora.',
        gosto: 'De planejar passeios em família e ler histórias antes de dormir.',
        frase: 'O amor e o cuidado transformam tudo.'
      },
      { 
        nome: 'Theo', 
        img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_THEO.png', 
        letra: 'T', 
        tag: 'Pai Protetor',
        quem: 'Pai da Iza e da Nina, calmo, paciente e atencioso.',
        gosto: 'De ensinar coisas novas e dar abraços bem apertados.',
        frase: 'Com calma e paciência a gente aprende melhor.'
      },
      { 
        nome: 'Nina', 
        img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_NINA.png', 
        letra: 'N', 
        tag: 'Super Esperta',
        quem: 'Menina de cabelos cacheados cheia de perguntas inteligentes.',
        gosto: 'De resolver desafios, pintar e descobrir segredos da natureza.',
        frase: 'Aprender coisas novas é super divertido!'
      },
      { 
        nome: 'Iza', 
        img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_IZA.png', 
        letra: 'I', 
        tag: 'A Vaidosa',
        quem: 'Menina charmosa de vestidinho rosa e coração bondoso.',
        gosto: 'De laços, vestidos bonitos, cantar e espalhar sorrisos.',
        frase: 'Ser gentil é o acessório mais lindo do mundo!'
      },
      { 
        nome: 'Sam', 
        img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994885/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_SAM.png', 
        letra: 'S', 
        tag: 'Pai Inventor',
        quem: 'Pai ruivo do Joca e do Leo, apaixonado por invenções.',
        gosto: 'De montar brinquedos reciclados e imaginar máquinas voadoras.',
        frase: 'Toda ideia pode virar uma grande invenção!'
      },
      { 
        nome: 'Lia', 
        img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994884/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_LIA.png', 
        letra: 'L', 
        tag: 'Mãe Alegria',
        quem: 'Mãe do Joca e do Leo, cheia de ritmo e entusiasmo.',
        gosto: 'De dançar, cozinhar coisas gostosas e reunir os amigos.',
        frase: 'A alegria é o nosso superpoder!'
      },
      { 
        nome: 'Joca', 
        img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_JOCA.png', 
        letra: 'J', 
        tag: 'O Divertido',
        quem: 'Menino de camiseta verde que adora fazer todo mundo rir.',
        gosto: 'De piadas engraçadas, correr e jogar com a turma.',
        frase: 'O importante é se divertir e rir junto!'
      },
      { 
        nome: 'Leo', 
        img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994883/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_LEO.png', 
        letra: 'L', 
        tag: 'Explorador Focado',
        quem: 'Irmão do Joca, observador, detalhista e guia do Espaço TEA.',
        gosto: 'De organizar seus blocos, rotinas e fazer tudo no seu tempo.',
        frase: 'Vamos fazer tudo com calma e no nosso tempo!'
      },
      { 
        nome: 'Beto', 
        img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_VOVO_BETO.png', 
        letra: 'B', 
        tag: 'Vovô Coruja',
        quem: 'Vovô de óculos quadrados, inspirado em Pedro Mariano.',
        gosto: 'De contar histórias antigas e passear ao ar livre.',
        frase: 'O amor da família é nossa maior riqueza.'
      },
      { 
        nome: 'Hilda', 
        img: 'https://res.cloudinary.com/oactqmgs/image/upload/v1786994886/FOTO_DE_PERFIL_JOGOS_E_ECOLHAS_DE_ICONES_DE_PERFIL_ETC_-_VOVO_HILDA.png', 
        letra: 'H', 
        tag: 'Vovó Acolhedora',
        quem: 'Vovó de óculos redondos, inspirada em Astrogilda Grispym.',
        gosto: 'De fazer bolos quentinhos e dar abraços acolhedores.',
        frase: 'Um coração cheio de amor nunca envelhece.'
      }
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

    /* MODAL DE FICHA DO PERSONAGEM */
    function abrirFichaPersonagem(nome) {
      const p = PERSONAGENS.find(x => x.nome === nome);
      if (!p) return;
      document.getElementById('ficha-img').src = p.img;
      document.getElementById('ficha-nome').innerText = p.nome;
      document.getElementById('ficha-apelido').innerText = `"${p.tag}"`;
      document.getElementById('ficha-quem').innerText = p.quem;
      document.getElementById('ficha-gosto').innerText = p.gosto;
      document.getElementById('ficha-frase').innerText = p.frase;
      
      const btnOuvir = document.getElementById('btnFichaOuvir');
      btnOuvir.onclick = () => lerTexto(`Oi! Eu sou ${p.nome}, ${p.tag}. ${p.quem} ${p.frase}`);

      document.getElementById('modalFichaPersonagem').classList.add('active');
      lerTexto(`Conheça ${p.nome}!`);
    }

    function fecharFichaPersonagem() {
      document.getElementById('modalFichaPersonagem').classList.remove('active');
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
      if (somAcalentoAtual) { somAcalentoAtual.pause(); somAcalentoAtual = null; }
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
      const abas = ['inicio', 'videos', 'jogos', 'tea', 'livros', 'rotina', 'conquistas', 'vip', 'config', 'perfil'];
      abas.forEach(id => {
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
      if (p === 'perfil') criarSeletorAvatar();
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
      else if (e === 'Triste') lerTexto("Tudo bem ficar triste. A Turminha te acolhe.");
      else if (e === 'Bravo') lerTexto("Vamos respirar fundo e soltar o ar devagar.");
    }

    function tocarSomReal(url) {
      if (somAcalentoAtual) {
        somAcalentoAtual.pause();
        if (somAcalentoAtual.src === url) { somAcalentoAtual = null; lerTexto("Som pausado"); return; }
      }
      somAcalentoAtual = new Audio(url);
      somAcalentoAtual.play().catch(() => {});
      lerTexto("Tocando som relaxante.");
    }

    /* CANVAS / LOUSA MÁGICA */
    const canvas = document.getElementById('paintCanvas');
    const ctx = canvas ? canvas.getContext('2d') : null;
    let desenhando = false, corAtual = '#3B82F6', tamanhoPincel = 4, imgContornoAtual = null;

    function redimensionarCanvas() {
      if (!canvas || !canvas.parentElement) return;
      canvas.width = canvas.parentElement.clientWidth - 28;
      canvas.height = window.innerWidth > 600 ? 300 : 250;
      if (imgContornoAtual) desenharContorno(imgContornoAtual);
    }

    function definirTamanhoPincel(tam, btn) {
      tamanhoPincel = tam;
      document.querySelectorAll('.btn-brush-size').forEach(b => b.classList.remove('active'));
      if (btn) btn.classList.add('active');
    }

    function mudarCor(c) { corAtual = c; }
    function limparCanvas() { 
      if (ctx) ctx.clearRect(0, 0, canvas.width, canvas.height); 
      if (imgContornoAtual) desenharContorno(imgContornoAtual);
    }

    function carregarContornoPintar(url, btn) {
      document.querySelectorAll('.btn-color-draw').forEach(b => b.classList.remove('selected'));
      if (btn) btn.classList.add('selected');
      limparCanvas();
      const img = new Image();
      img.crossOrigin = "Anonymous";
      img.src = url;
      img.onload = () => { imgContornoAtual = img; desenharContorno(img); };
    }

    function desenharContorno(img) {
      const ratio = Math.min(canvas.width / img.width, canvas.height / img.height) * 0.85;
      const w = img.width * ratio;
      const h = img.height * ratio;
      const x = (canvas.width - w) / 2;
      const y = (canvas.height - h) / 2;
      ctx.globalAlpha = 0.35;
      ctx.drawImage(img, x, y, w, h);
      ctx.globalAlpha = 1.0;
    }

    function salvarFotoDesenho() {
      const link = document.createElement('a');
      link.download = 'desenho-turminha.png';
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

    /* JOGOS */
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
        img.style.cssText = 'width:44px; height:44px; object-fit:contain;';
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
            lerTexto("Parabéns! Acertou!");
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
        btn.style.fontSize = '13px';
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
      const placa1 = document.getElementById('placar-pontos');
      const placa2 = document.getElementById('placar-pontos-2');
      if (placa1) placa1.innerText = pontosConquista;
      if (placa2) placa2.innerText = pontosConquista;
      
      const tit = pontosConquista >= 50 ? "🌟 Super Fã Mestre" : pontosConquista >= 20 ? "⭐ Explorador" : "⭐ Iniciante";
      const med1 = document.getElementById('medalha-status');
      const med2 = document.getElementById('medalha-status-2');
      if (med1) med1.innerText = tit;
      if (med2) med2.innerText = tit;
    }

    function criarSeletorAvatar() {
      const grid = document.getElementById('avatarEscolhaGrid');
      if (!grid || grid.children.length > 0) return;
      grid.innerHTML = '';
      const avatarAtual = localStorage.getItem('turminha_avatar') || PERSONAGENS[0].img;
      PERSONAGENS.forEach(p => {
        const img = document.createElement('img');
        img.src = p.img;
        img.className = 'avatar-escolha-btn' + (p.img === avatarAtual ? ' selecionado' : '');
        img.onclick = () => {
          document.querySelectorAll('.avatar-escolha-btn').forEach(b => b.classList.remove('selecionado'));
          img.classList.add('selecionado');
          localStorage.setItem('turminha_avatar', p.img);
          lerTexto(`${p.nome} escolhido como avatar!`);
        };
        grid.appendChild(img);
      });
    }

    function gerarCertificadoGeral() {
      const nome = document.getElementById('nome-certificado-input').value.trim();
      if (!nome) { alert("Digite o nome da criança!"); return; }
      document.getElementById('txtNomeCertificado').innerText = nome;
      document.getElementById('boxCertificadoResultado').style.display = 'block';
      lerTexto(`Parabéns, ${nome}! Você é oficialmente Super Fã da Turminha do Xexéu!`);
    }

    function salvarECadastrar() {
      const email = document.getElementById('cad-email').value.trim();
      const senha = document.getElementById('cad-senha').value.trim();
      if (!email || !senha) alert("Preencha o e-mail e crie a senha parental!");
    }

    function fazerLogin() {
      const senha = document.getElementById('log-senha').value.trim();
      if (senha === SENHA_MESTRA) {
        alert("Acesso Mestre Liberado!");
        lerTexto("Bem-vindo de volta ao Painel VIP!");
      } else {
        alert("Senha incorreta ou assinatura pendente.");
      }
    }

    window.onload = () => {
      adicionarPontos(0);
      carregarJogoContar();
      carregarJogoLetra();
      iniciarMemoria();
      carregarQuiz();
      carregarContornoPintar('https://res.cloudinary.com/oactqmgs/image/upload/v1786994876/DESENHOS_DA_LOUSA_XEXEU.png', document.querySelector('.btn-color-draw'));
    };
    window.onresize = redimensionarCanvas;
  </script>
</body>
</html>
