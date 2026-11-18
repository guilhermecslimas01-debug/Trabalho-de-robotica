<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Kainonia — Comunhão, propósito e conexão humana. Unimos pessoas e ideias para transformar comunidades.">
  <title>Kainonia | Comunhão, Propósito e Conexão Humana</title>

  <!-- Google Fonts: Lora (Serifa elegante) & Plus Jakarta Sans (Sans-serif limpa) -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,400;0,500;0,600;0,700;1,400&family=Plus+Jakarta+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">

  <style>
    /* ==========================================================================
       1. VARIÁVEIS CSS & DESIGN TOKENS (PALETA TERROSA & ACOLHEDORA)
       ========================================================================== */
    :root {
      /* Cores Principais */
      --color-cream: #FBF9F5;         /* Fundo principal suave */
      --color-sand: #F2ECE1;          /* Fundo secundário / cards */
      --color-sand-dark: #E5DDD0;     /* Bordas sutis e divisores */
      --color-terracotta: #C26D4F;    /* Destaque quente e acolhedor */
      --color-terracotta-dark: #A6563A;
      --color-olive: #2D3B32;         /* Verde-oliva profundo (autoridade e raiz) */
      --color-olive-light: #44574B;
      
      /* Cores de Texto */
      --text-primary: #262421;        /* Carvão quente */
      --text-secondary: #5C5750;      /* Marrom acinzentado */
      --text-light: #FBF9F5;

      /* Tipografia */
      --font-serif: 'Lora', Georgia, serif;
      --font-sans: 'Plus Jakarta Sans', -apple-system, BlinkMacSystemFont, sans-serif;

      /* Espaçamentos & Layout */
      --container-max: 1180px;
      --section-padding: clamp(4.5rem, 8vw, 7.5rem);
      --radius-sm: 8px;
      --radius-md: 16px;
      --radius-lg: 28px;
      --radius-pill: 999px;

      /* Sombras e Transições */
      --shadow-soft: 0 12px 32px -8px rgba(45, 59, 50, 0.08);
      --shadow-hover: 0 20px 40px -10px rgba(45, 59, 50, 0.14);
      --transition: all 0.35s cubic-bezier(0.25, 0.8, 0.25, 1);
    }

    /* ==========================================================================
       2. RESET & BASE STYLES
       ========================================================================== */
    *, *::before, *::after {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
      font-size: 16px;
    }

    body {
      font-family: var(--font-sans);
      background-color: var(--color-cream);
      color: var(--text-primary);
      line-height: 1.7;
      -webkit-font-smoothing: antialiased;
      overflow-x: hidden;
    }

    img {
      max-width: 100%;
      display: block;
    }

    a {
      text-decoration: none;
      color: inherit;
      transition: var(--transition);
    }

    ul {
      list-style: none;
    }

    /* Utilitários de Layout */
    .container {
      width: 100%;
      max-width: var(--container-max);
      margin: 0 auto;
      padding: 0 1.5rem;
    }

    .section {
      padding: var(--section-padding) 0;
    }

    .eyebrow {
      display: inline-block;
      font-size: 0.8125rem;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 0.14em;
      color: var(--color-terracotta);
      margin-bottom: 0.85rem;
    }

    .section-title {
      font-family: var(--font-serif);
      font-size: clamp(2rem, 4vw, 3rem);
      font-weight: 600;
      line-height: 1.2;
      color: var(--color-olive);
      margin-bottom: 1.25rem;
    }

    .section-subtitle {
      font-size: 1.125rem;
      color: var(--text-secondary);
      max-width: 640px;
      line-height: 1.75;
    }

    /* Botões */
    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 0.6rem;
      padding: 0.95rem 2rem;
      border-radius: var(--radius-pill);
      font-weight: 600;
      font-size: 0.95rem;
      cursor: pointer;
      border: 1.5px solid transparent;
      transition: var(--transition);
    }

    .btn-primary {
      background-color: var(--color-terracotta);
      color: var(--text-light);
      box-shadow: 0 8px 20px -6px rgba(194, 109, 79, 0.45);
    }

    .btn-primary:hover {
      background-color: var(--color-terracotta-dark);
      transform: translateY(-2px);
      box-shadow: 0 12px 24px -6px rgba(194, 109, 79, 0.55);
    }

    .btn-outline {
      background-color: transparent;
      border-color: var(--color-olive);
      color: var(--color-olive);
    }

    .btn-outline:hover {
      background-color: var(--color-olive);
      color: var(--text-light);
      transform: translateY(-2px);
    }

    /* ==========================================================================
       3. CABEÇALHO & NAVEGAÇÃO RESPONSIVA (CSS PURO COM CHECKBOX HACK)
       ========================================================================== */
    .header {
      position: sticky;
      top: 0;
      z-index: 1000;
      background-color: rgba(251, 249, 245, 0.92);
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--color-sand-dark);
    }

    .header-inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      height: 82px;
    }

    /* Logotipo Tipográfico & Símbolo */
    .logo {
      display: flex;
      align-items: center;
      gap: 0.7rem;
      font-family: var(--font-serif);
      font-size: 1.65rem;
      font-weight: 600;
      color: var(--color-olive);
      letter-spacing: -0.02em;
    }

    .logo-mark {
      width: 34px;
      height: 34px;
      display: flex;
      align-items: center;
      justify-content: center;
      background-color: var(--color-sand);
      border-radius: 50%;
      color: var(--color-terracotta);
    }

    /* Menu Desktop */
    .nav-list {
      display: flex;
      align-items: center;
      gap: 2.25rem;
    }

    .nav-link {
      font-size: 0.95rem;
      font-weight: 500;
      color: var(--text-secondary);
      position: relative;
      padding: 0.25rem 0;
    }

    .nav-link::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 0;
      width: 0;
      height: 2px;
      background-color: var(--color-terracotta);
      transition: var(--transition);
    }

    .nav-link:hover {
      color: var(--color-olive);
    }

    .nav-link:hover::after {
      width: 100%;
    }

    .nav-cta {
      padding: 0.65rem 1.5rem;
      font-size: 0.9rem;
    }

    /* Controle Mobile */
    .nav-toggle {
      display: none;
    }

    .nav-toggle-label {
      display: none;
      cursor: pointer;
      width: 40px;
      height: 40px;
      align-items: center;
      justify-content: center;
      border-radius: var(--radius-sm);
      color: var(--color-olive);
    }

    /* ==========================================================================
       4. SEÇÃO HERO
       ========================================================================== */
    .hero {
      padding: clamp(3.5rem, 7vw, 6.5rem) 0;
      position: relative;
      overflow: hidden;
    }

    /* Elemento orgânico sutil de fundo */
    .hero::before {
      content: '';
      position: absolute;
      top: -15%;
      right: -8%;
      width: 520px;
      height: 520px;
      background: radial-gradient(circle, rgba(194, 109, 79, 0.09) 0%, rgba(251, 249, 245, 0) 70%);
      border-radius: 50%;
      z-index: -1;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.15fr 0.85fr;
      align-items: center;
      gap: 4rem;
    }

    .hero-badge {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      background-color: var(--color-sand);
      padding: 0.45rem 1rem;
      border-radius: var(--radius-pill);
      font-size: 0.85rem;
      font-weight: 600;
      color: var(--color-olive);
      margin-bottom: 1.5rem;
      border: 1px solid var(--color-sand-dark);
    }

    .hero-badge-dot {
      width: 8px;
      height: 8px;
      border-radius: 50%;
      background-color: var(--color-terracotta);
    }

    .hero-title {
      font-family: var(--font-serif);
      font-size: clamp(2.5rem, 5vw, 4rem);
      font-weight: 600;
      line-height: 1.14;
      color: var(--color-olive);
      margin-bottom: 1.5rem;
      letter-spacing: -0.02em;
    }

    .hero-title em {
      font-style: italic;
      color: var(--color-terracotta);
      font-weight: 500;
    }

    .hero-description {
      font-size: 1.15rem;
      color: var(--text-secondary);
      margin-bottom: 2.25rem;
      max-width: 540px;
      line-height: 1.75;
    }

    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
    }

    /* Composição Visual do Hero */
    .hero-visual {
      position: relative;
    }

    .hero-image-frame {
      border-radius: var(--radius-lg) var(--radius-lg) var(--radius-lg) 90px;
      overflow: hidden;
      box-shadow: var(--shadow-soft);
      background-color: var(--color-sand);
      aspect-ratio: 4 / 4.6;
      position: relative;
    }

    .hero-image-frame img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .hero-floating-card {
      position: absolute;
      bottom: -24px;
      left: -28px;
      background-color: var(--color-cream);
      padding: 1.35rem 1.65rem;
      border-radius: var(--radius-md);
      box-shadow: var(--shadow-hover);
      border: 1px solid var(--color-sand-dark);
      max-width: 260px;
    }

    .hero-floating-card strong {
      display: block;
      font-family: var(--font-serif);
      font-size: 1.15rem;
      color: var(--color-olive);
      margin-bottom: 0.25rem;
    }

    .hero-floating-card span {
      font-size: 0.875rem;
      color: var(--text-secondary);
      line-height: 1.45;
      display: block;
    }

    /* ==========================================================================
       5. SEÇÃO SOBRE NÓS / ESSÊNCIA
       ========================================================================== */
    .essence {
      background-color: var(--color-sand);
      border-top: 1px solid var(--color-sand-dark);
      border-bottom: 1px solid var(--color-sand-dark);
    }

    .essence-grid {
      display: grid;
      grid-template-columns: 0.95fr 1.05fr;
      align-items: center;
      gap: 4.5rem;
    }

    .essence-quote-box {
      background-color: var(--color-olive);
      color: var(--text-light);
      padding: clamp(2.5rem, 5vw, 3.75rem);
      border-radius: var(--radius-lg);
      position: relative;
      box-shadow: var(--shadow-soft);
    }

    .essence-word {
      font-family: var(--font-serif);
      font-size: 2.35rem;
      font-style: italic;
      color: #E8A890;
      margin-bottom: 0.35rem;
    }

    .essence-phonetic {
      font-size: 0.9rem;
      letter-spacing: 0.08em;
      opacity: 0.75;
      margin-bottom: 1.75rem;
      display: block;
    }

    .essence-quote-box p {
      font-size: 1.08rem;
      line-height: 1.8;
      color: rgba(251, 249, 245, 0.92);
      margin-bottom: 1.75rem;
    }

    .essence-divider {
      width: 48px;
      height: 2px;
      background-color: var(--color-terracotta);
    }

    .essence-content p {
      color: var(--text-secondary);
      font-size: 1.0625rem;
      margin-bottom: 1.35rem;
    }

    .essence-highlights {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1.5rem;
      margin-top: 2rem;
      padding-top: 2rem;
      border-top: 1px solid var(--color-sand-dark);
    }

    .highlight-item strong {
      display: block;
      font-family: var(--font-serif);
      font-size: 1.85rem;
      color: var(--color-terracotta);
      line-height: 1.2;
      margin-bottom: 0.25rem;
    }

    .highlight-item span {
      font-size: 0.925rem;
      color: var(--text-secondary);
    }

    /* ==========================================================================
       6. SEÇÃO PILARES / VALORES
       ========================================================================== */
    .pillars-header {
      text-align: center;
      max-width: 680px;
      margin: 0 auto 4rem;
    }

    .pillars-header .section-subtitle {
      margin: 0 auto;
    }

    .pillars-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 2rem;
    }

    .pillar-card {
      background-color: #FFFFFF;
      border: 1px solid var(--color-sand-dark);
      border-radius: var(--radius-md);
      padding: 2.75rem 2.25rem;
      transition: var(--transition);
      display: flex;
      flex-direction: column;
    }

    .pillar-card:hover {
      transform: translateY(-6px);
      box-shadow: var(--shadow-hover);
      border-color: var(--color-terracotta);
    }

    .pillar-icon {
      width: 56px;
      height: 56px;
      border-radius: 14px;
      background-color: var(--color-sand);
      color: var(--color-terracotta);
      display: flex;
      align-items: center;
      justify-content: center;
      margin-bottom: 1.75rem;
      transition: var(--transition);
    }

    .pillar-card:hover .pillar-icon {
      background-color: var(--color-terracotta);
      color: var(--text-light);
    }

    .pillar-card h3 {
      font-family: var(--font-serif);
      font-size: 1.5rem;
      color: var(--color-olive);
      margin-bottom: 1rem;
    }

    .pillar-card p {
      color: var(--text-secondary);
      font-size: 0.985rem;
      line-height: 1.75;
    }

    /* ==========================================================================
       7. SEÇÃO O QUE FAZEMOS / INICIATIVAS
       ========================================================================== */
    .initiatives {
      background-color: var(--color-sand);
      border-top: 1px solid var(--color-sand-dark);
    }

    .initiatives-top {
      display: flex;
      justify-content: space-between;
      align-items: flex-end;
      flex-wrap: wrap;
      gap: 2rem;
      margin-bottom: 3.5rem;
    }

    .initiatives-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 2rem;
    }

    .initiative-card {
      background-color: var(--color-cream);
      border-radius: var(--radius-md);
      overflow: hidden;
      border: 1px solid var(--color-sand-dark);
      transition: var(--transition);
      display: flex;
      flex-direction: column;
    }

    .initiative-card:hover {
      transform: translateY(-5px);
      box-shadow: var(--shadow-hover);
    }

    .initiative-img {
      height: 220px;
      overflow: hidden;
      background-color: var(--color-sand-dark);
    }

    .initiative-img img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: transform 0.6s ease;
    }

    .initiative-card:hover .initiative-img img {
      transform: scale(1.05);
    }

    .initiative-body {
      padding: 2rem;
      flex: 1;
      display: flex;
      flex-direction: column;
    }

    .initiative-tag {
      font-size: 0.78rem;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 0.1em;
      color: var(--color-olive-light);
      margin-bottom: 0.6rem;
    }

    .initiative-body h3 {
      font-family: var(--font-serif);
      font-size: 1.35rem;
      color: var(--color-olive);
      margin-bottom: 0.85rem;
    }

    .initiative-body p {
      color: var(--text-secondary);
      font-size: 0.95rem;
      margin-bottom: 1.5rem;
      flex: 1;
    }

    .initiative-link {
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
      font-weight: 600;
      font-size: 0.925rem;
      color: var(--color-terracotta);
    }

    .initiative-link:hover {
      color: var(--color-terracotta-dark);
      gap: 0.7rem;
    }

    /* ==========================================================================
       8. SEÇÃO DEPOIMENTO / DESTAQUE INSPIRADOR
       ========================================================================== */
    .testimonial-section {
      background-color: var(--color-olive);
      color: var(--text-light);
      text-align: center;
      position: relative;
    }

    .testimonial-inner {
      max-width: 820px;
      margin: 0 auto;
    }

    .quote-icon {
      color: var(--color-terracotta);
      margin: 0 auto 1.75rem;
      opacity: 0.9;
    }

    .testimonial-quote {
      font-family: var(--font-serif);
      font-size: clamp(1.5rem, 3vw, 2.2rem);
      font-weight: 400;
      font-style: italic;
      line-height: 1.55;
      color: var(--color-cream);
      margin-bottom: 2.25rem;
    }

    .testimonial-author {
      display: inline-flex;
      align-items: center;
      gap: 1rem;
      text-align: left;
    }

    .author-avatar {
      width: 52px;
      height: 52px;
      border-radius: 50%;
      background-color: var(--color-terracotta);
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: var(--font-serif);
      font-weight: 600;
      font-size: 1.2rem;
      color: var(--text-light);
    }

    .author-info strong {
      display: block;
      font-size: 1rem;
      color: var(--text-light);
    }

    .author-info span {
      font-size: 0.875rem;
      color: rgba(251, 249, 245, 0.72);
    }

    /* ==========================================================================
       9. SEÇÃO CONTATO
       ========================================================================== */
    .contact-grid {
      display: grid;
      grid-template-columns: 0.9fr 1.1fr;
      gap: 4rem;
      align-items: start;
    }

    .contact-details {
      margin-top: 2.25rem;
      display: flex;
      flex-direction: column;
      gap: 1.5rem;
    }

    .contact-item {
      display: flex;
      align-items: flex-start;
      gap: 1rem;
    }

    .contact-item-icon {
      width: 44px;
      height: 44px;
      border-radius: 50%;
      background-color: var(--color-sand);
      color: var(--color-terracotta);
      display: flex;
      align-items: center;
      justify-content: center;
      flex-shrink: 0;
    }

    .contact-item strong {
      display: block;
      color: var(--color-olive);
      font-size: 0.95rem;
      margin-bottom: 0.15rem;
    }

    .contact-item span {
      color: var(--text-secondary);
      font-size: 0.925rem;
    }

    /* Formulário */
    .contact-form-card {
      background-color: #FFFFFF;
      padding: clamp(2rem, 4vw, 3rem);
      border-radius: var(--radius-lg);
      border: 1px solid var(--color-sand-dark);
      box-shadow: var(--shadow-soft);
    }

    .form-row {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1.25rem;
    }

    .form-group {
      margin-bottom: 1.35rem;
    }

    .form-label {
      display: block;
      font-size: 0.875rem;
      font-weight: 600;
      color: var(--color-olive);
      margin-bottom: 0.5rem;
    }

    .form-control {
      width: 100%;
      padding: 0.85rem 1.1rem;
      border-radius: var(--radius-sm);
      border: 1.5px solid var(--color-sand-dark);
      background-color: var(--color-cream);
      font-family: var(--font-sans);
      font-size: 0.95rem;
      color: var(--text-primary);
      transition: var(--transition);
    }

    .form-control::placeholder {
      color: #9A938A;
    }

    .form-control:focus {
      outline: none;
      border-color: var(--color-terracotta);
      background-color: #FFFFFF;
      box-shadow: 0 0 0 4px rgba(194, 109, 79, 0.12);
    }

    textarea.form-control {
      min-height: 130px;
      resize: vertical;
    }

    .form-submit {
      width: 100%;
      margin-top: 0.5rem;
    }

    /* Feedback visual de envio via :target (100% CSS puro) */
    .form-feedback {
      display: none;
      margin-top: 1.25rem;
      padding: 1rem 1.25rem;
      border-radius: var(--radius-sm);
      background-color: #EDF5F0;
      border: 1px solid #B7D4C2;
      color: var(--color-olive);
      font-size: 0.925rem;
      font-weight: 500;
    }

    #mensagem-enviada:target {
      display: block;
      animation: fadeIn 0.4s ease;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(6px); }
      to { opacity: 1; transform: translateY(0); }
    }

    /* ==========================================================================
       10. RODAPÉ COMPLETO
       ========================================================================== */
    .footer {
      background-color: #212C25;
      color: rgba(251, 249, 245, 0.78);
      padding-top: 4.5rem;
    }

    .footer-grid {
      display: grid;
      grid-template-columns: 1.5fr 1fr 1fr 1.2fr;
      gap: 3rem;
      padding-bottom: 3.5rem;
      border-bottom: 1px solid rgba(251, 249, 245, 0.12);
    }

    .footer-brand .logo {
      color: var(--text-light);
      margin-bottom: 1rem;
    }

    .footer-brand .logo-mark {
      background-color: rgba(251, 249, 245, 0.1);
      color: #E8A890;
    }

    .footer-brand p {
      font-size: 0.925rem;
      line-height: 1.7;
      max-width: 300px;
      margin-bottom: 1.5rem;
    }

    .social-links {
      display: flex;
      gap: 0.75rem;
    }

    .social-link {
      width: 38px;
      height: 38px;
      border-radius: 50%;
      background-color: rgba(251, 249, 245, 0.08);
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--text-light);
    }

    .social-link:hover {
      background-color: var(--color-terracotta);
      transform: translateY(-2px);
    }

    .footer h4 {
      font-family: var(--font-serif);
      color: var(--text-light);
      font-size: 1.1rem;
      margin-bottom: 1.25rem;
    }

    .footer-links li {
      margin-bottom: 0.7rem;
    }

    .footer-links a {
      font-size: 0.925rem;
      color: rgba(251, 249, 245, 0.72);
    }

    .footer-links a:hover {
      color: #E8A890;
      padding-left: 4px;
    }

    .footer-bottom {
      padding: 1.75rem 0;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 1rem;
      font-size: 0.85rem;
      color: rgba(251, 249, 245, 0.55);
    }

    /* ==========================================================================
       11. RESPONSIVIDADE (TABLET & MOBILE)
       ========================================================================== */
    @media (max-width: 992px) {
      .hero-grid,
      .essence-grid,
      .contact-grid {
        grid-template-columns: 1fr;
        gap: 3rem;
      }

      .hero-visual {
        max-width: 540px;
        margin: 0 auto;
      }

      .hero-floating-card {
        left: 16px;
        bottom: -20px;
      }

      .pillars-grid,
      .initiatives-grid {
        grid-template-columns: repeat(2, 1fr);
      }

      .footer-grid {
        grid-template-columns: 1fr 1fr;
      }
    }

    @media (max-width: 768px) {
      /* Menu Mobile Hambúrguer em CSS puro */
      .nav-toggle-label {
        display: flex;
      }

      .nav-menu {
        position: absolute;
        top: 82px;
        left: 0;
        width: 100%;
        background-color: var(--color-cream);
        border-bottom: 1px solid var(--color-sand-dark);
        padding: 0 1.5rem;
        max-height: 0;
        overflow: hidden;
        transition: max-height 0.4s ease, padding 0.4s ease;
        box-shadow: 0 16px 32px rgba(0,0,0,0.06);
      }

      .nav-toggle:checked ~ .nav-menu {
        max-height: 420px;
        padding: 1.5rem;
      }

      .nav-list {
        flex-direction: column;
        align-items: flex-start;
        gap: 1.25rem;
      }

      .nav-cta {
        width: 100%;
        text-align: center;
      }

      .pillars-grid,
      .initiatives-grid,
      .form-row {
        grid-template-columns: 1fr;
      }

      .footer-grid {
        grid-template-columns: 1fr;
        gap: 2.25rem;
      }

      .footer-bottom {
        flex-direction: column;
        text-align: center;
      }
    }
  </style>
</head>
<body>

  <!-- ========================================================================
       CABEÇALHO RESPONSIVO
       ======================================================================== -->
  <header class="header">
    <div class="container header-inner">
      <a href="#" class="logo" aria-label="Kainonia Página Inicial">
        <span class="logo-mark" aria-hidden="true">
          <!-- Ícone geométrico de elos entrelaçados (Comunhão) -->
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round">
            <circle cx="9" cy="12" r="5"></circle>
            <circle cx="15" cy="12" r="5"></circle>
          </svg>
        </span>
        Kainonia
      </a>

      <!-- Controle do Menu Mobile -->
      <input type="checkbox" id="nav-toggle" class="nav-toggle" aria-label="Abrir menu de navegação">
      <label for="nav-toggle" class="nav-toggle-label" aria-hidden="true">
        <svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round">
          <line x1="3" y1="6" x2="21" y2="6"></line>
          <line x1="3" y1="12" x2="21" y2="12"></line>
          <line x1="3" y1="18" x2="21" y2="18"></line>
        </svg>
      </label>

      <nav class="nav-menu" aria-label="Navegação Principal">
        <ul class="nav-list">
          <li><a href="#essencia" class="nav-link">Nossa Essência</a></li>
          <li><a href="#pilares" class="nav-link">Pilares</a></li>
          <li><a href="#iniciativas" class="nav-link">Iniciativas</a></li>
          <li><a href="#depoimento" class="nav-link">Histórias</a></li>
          <li><a href="#contato" class="btn btn-primary nav-cta">Fazer Parte</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <main>
    <!-- ======================================================================
         SEÇÃO HERO
         ====================================================================== -->
    <section class="hero">
      <div class="container hero-grid">
        <div class="hero-content">
          <div class="hero-badge">
            <span class="hero-badge-dot"></span>
            Comunhão • Propósito • Parceria
          </div>
          <h1 class="hero-title">
            Onde pessoas e propósitos se encontram em <em>verdadeira comunhão.</em>
          </h1>
          <p class="hero-description">
            Acreditamos que nenhuma transformação duradoura acontece de forma isolada. A Kainonia cultiva pontes humanas, projetos colaborativos e redes de apoio que florescem quando caminhamos juntos.
          </p>
          <div class="hero-actions">
            <a href="#iniciativas" class="btn btn-primary">
              Conhecer Iniciativas
              <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round">
                <line x1="5" y1="12" x2="19" y2="12"></line>
                <polyline points="12 5 19 12 12 19"></polyline>
              </svg>
            </a>
            <a href="#essencia" class="btn btn-outline">Nossa História</a>
          </div>
        </div>

        <div class="hero-visual">
          <div class="hero-image-frame">
            <img 
              src="https://images.unsplash.com/photo-1529156069898-49953e39b3ac?auto=format&fit=crop&w=900&q=80" 
              alt="Pessoas sorrindo e conversando em comunidade ao ar livre"
              onerror="this.src='https://placehold.co/800x920/E5DDD0/2D3B32?text=Comunidade+Kainonia'"
            >
          </div>
          <div class="hero-floating-card">
            <strong>+4.200 vidas conectadas</strong>
            <span>Construindo vínculos genuínos e redes de impacto social em todo o Brasil.</span>
          </div>
        </div>
      </div>
    </section>

    <!-- ======================================================================
         SEÇÃO SOBRE NÓS / ESSÊNCIA
         ====================================================================== -->
    <section id="essencia" class="section essence">
      <div class="container essence-grid">
        <div class="essence-quote-box">
          <div class="essence-word">Koinōnía</div>
          <span class="essence-phonetic">/koi.no.ní.a/ • substantivo feminino</span>
          <p>
            Do grego antigo, expressa mais do que simples convivência: significa participação mútua, partilha generosa, vínculo profundo e parceria ativa em prol de um bem comum.
          </p>
          <div class="essence-divider"></div>
        </div>

        <div class="essence-content">
          <span class="eyebrow">Nossa Essência</span>
          <h2 class="section-title">Unir histórias para multiplicar impacto humano.</h2>
          <p>
            Nascemos da convicção de que a resposta para os desafios do nosso tempo está no resgate do senso de pertencimento. Em um mundo cada vez mais acelerado e fragmentado, criamos espaços seguros de escuta, troca e construção coletiva.
          </p>
          <p>
            Na Kainonia, cada pessoa traz uma habilidade, uma vivência e um olhar único. Quando colocamos esses dons em mesa compartilhada, ideias ganham vida e comunidades se fortalecem.
          </p>

          <div class="essence-highlights">
            <div class="highlight-item">
              <strong>18 Comunidades</strong>
              <span>Núcleos ativos de diálogo e colaboração local.</span>
            </div>
            <div class="highlight-item">
              <strong>100% Colaborativo</strong>
              <span>Projetos co-criados por membros e parceiros.</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- ======================================================================
         SEÇÃO PILARES / VALORES
         ====================================================================== -->
    <section id="pilares" class="section">
      <div class="container">
        <div class="pillars-header">
          <span class="eyebrow">O que nos sustenta</span>
          <h2 class="section-title">Os três pilares da Kainonia</h2>
          <p class="section-subtitle">
            Nossos valores orientam cada encontro, parceria e projeto que colocamos no mundo.
          </p>
        </div>

        <div class="pillars-grid">
          <!-- Pilar 1: Comunhão -->
          <article class="pillar-card">
            <div class="pillar-icon" aria-hidden="true">
              <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round">
                <path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"></path>
                <circle cx="9" cy="7" r="4"></circle>
                <path d="M23 21v-2a4 4 0 0 0-3-3.87"></path>
                <path d="M16 3.13a4 4 0 0 1 0 7.75"></path>
              </svg>
            </div>
            <h3>Comunhão</h3>
            <p>
              Cultivamos ambientes acolhedores onde cada voz tem valor. Acreditamos na mesa aberta, na hospitalidade genuína e na partilha que transforma desconhecidos em família.
            </p>
          </article>

          <!-- Pilar 2: Propósito -->
          <article class="pillar-card">
            <div class="pillar-icon" aria-hidden="true">
              <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round">
                <circle cx="12" cy="12" r="10"></circle>
                <polygon points="16.24 7.76 14.12 14.12 7.76 16.24 9.88 9.88 16.24 7.76"></polygon>
              </svg>
            </div>
            <h3>Propósito</h3>
            <p>
              Alinhamos talentos individuais a causas maiores que nós mesmos. Cada iniciativa busca gerar significado real, dignidade e florescimento integral para as pessoas.
            </p>
          </article>

          <!-- Pilar 3: Conexão -->
          <article class="pillar-card">
            <div class="pillar-icon" aria-hidden="true">
              <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round">
                <path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path>
                <path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path>
              </svg>
            </div>
            <h3>Conexão</h3>
            <p>
              Construímos pontes entre gerações, saberes e territórios. Conectamos quem deseja servir a quem precisa de apoio, criando redes vivas de parceria e confiança mútua.
            </p>
          </article>
        </div>
      </div>
    </section>

    <!-- ======================================================================
         SEÇÃO O QUE FAZEMOS / INICIATIVAS
         ====================================================================== -->
    <section id="iniciativas" class="section initiatives">
      <div class="container">
        <div class="initiatives-top">
          <div>
            <span class="eyebrow">O que fazemos</span>
            <h2 class="section-title">Iniciativas que geram pertencimento</h2>
          </div>
          <p class="section-subtitle">
            Atuamos em frentes práticas que aproximam pessoas, desenvolvem lideranças humanas e fortalecem comunidades locais.
          </p>
        </div>

        <div class="initiatives-grid">
          <!-- Iniciativa 1 -->
          <article class="initiative-card">
            <div class="initiative-img">
              <img 
                src="https://images.unsplash.com/photo-1511632765486-a01980e01a18?auto=format&fit=crop&w=800&q=80" 
                alt="Roda de conversa em encontro comunitário"
                onerror="this.src='https://placehold.co/800x500/E5DDD0/2D3B32?text=Mesas+de+Dialogo'"
              >
            </div>
            <div class="initiative-body">
              <span class="initiative-tag">Encontros Presenciais</span>
              <h3>Mesas de Diálogo & Escuta</h3>
              <p>
                Rodas mensais de conversa profunda sobre cultura, bem-estar emocional e convivência, criando laços reais fora das telas.
              </p>
              <a href="#contato" class="initiative-link">
                Participar de um encontro →
              </a>
            </div>
          </article>

          <!-- Iniciativa 2 -->
          <article class="initiative-card">
            <div class="initiative-img">
              <img 
                src="https://images.unsplash.com/photo-1522202176988-66273c2fd55f?auto=format&fit=crop&w=800&q=80" 
                alt="Equipe colaborando em projeto criativo"
                onerror="this.src='https://placehold.co/800x500/E5DDD0/2D3B32?text=Redes+de+Parceria'"
              >
            </div>
            <div class="initiative-body">
              <span class="initiative-tag">Mentoria & Vocação</span>
              <h3>Laboratório de Propósito</h3>
              <p>
                Programas de mentoria coletiva que ajudam profissionais e empreendedores sociais a alinharem carreira, ética e impacto comunitário.
              </p>
              <a href="#contato" class="initiative-link">
                Conhecer o programa →
              </a>
            </div>
          </article>

          <!-- Iniciativa 3 -->
          <article class="initiative-card">
            <div class="initiative-img">
              <img 
                src="https://images.unsplash.com/photo-1593113598332-cd288d649433?auto=format&fit=crop&w=800&q=80" 
                alt="Ação solidária comunitária com voluntários"
                onerror="this.src='https://placehold.co/800x500/E5DDD0/2D3B32?text=Acao+Solidaria'"
              >
            </div>
            <div class="initiative-body">
              <span class="initiative-tag">Impacto Local</span>
              <h3>Alianças Solidárias</h3>
              <p>
                Articulação de voluntários, organizações locais e apoiadores para sustentar projetos educativos e de cuidado familiar em bairros vulneráveis.
              </p>
              <a href="#contato" class="initiative-link">
                Apoiar uma aliança →
              </a>
            </div>
          </article>
        </div>
      </div>
    </section>

    <!-- ======================================================================
         SEÇÃO DEPOIMENTO / DESTAQUE INSPIRADOR
         ====================================================================== -->
    <section id="depoimento" class="section testimonial-section">
      <div class="container testimonial-inner">
        <div class="quote-icon" aria-hidden="true">
          <svg width="44" height="44" viewBox="0 0 24 24" fill="currentColor">
            <path d="M14.017 21v-7.391c0-5.704 3.731-9.57 8.983-10.609l.995 2.151c-2.432.917-3.995 3.638-3.995 5.849h4v10h-9.983zm-14.017 0v-7.391c0-5.704 3.748-9.57 9-10.609l.996 2.151c-2.433.917-3.996 3.638-3.996 5.849h3.983v10h-9.983z"/>
          </svg>
        </div>

        <blockquote class="testimonial-quote">
          “Cheguei à Kainonia buscando apenas um espaço para trocar ideias sobre projetos sociais, mas encontrei uma verdadeira comunidade de vida. Aqui aprendi que caminhar acompanhado torna qualquer propósito mais leve e possível.”
        </blockquote>

        <div class="testimonial-author">
          <div class="author-avatar" aria-hidden="true">CM</div>
          <div class="author-info">
            <strong>Clara Mendes</strong>
            <span>Educadora Social & Membro da Comunidade desde 2023</span>
          </div>
        </div>
      </div>
    </section>

    <!-- ======================================================================
         SEÇÃO CONTATO
         ====================================================================== -->
    <section id="contato" class="section">
      <div class="container contact-grid">
        <div>
          <span class="eyebrow">Vamos conversar</span>
          <h2 class="section-title">A porta está sempre aberta para você.</h2>
          <p class="section-subtitle">
            Quer participar de um encontro, propor uma parceria institucional ou saber como contribuir com nossas iniciativas? Envie sua mensagem.
          </p>

          <div class="contact-details">
            <div class="contact-item">
              <div class="contact-item-icon" aria-hidden="true">
                <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path>
                  <polyline points="22,6 12,13 2,6"></polyline>
                </svg>
              </div>
              <div>
                <strong>E-mail Institucional</strong>
                <span>contato@kainonia.org.br</span>
              </div>
            </div>

            <div class="contact-item">
              <div class="contact-item-icon" aria-hidden="true">
                <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path>
                  <circle cx="12" cy="10" r="3"></circle>
                </svg>
              </div>
              <div>
                <strong>Casa Kainonia</strong>
                <span>Rua das Acácias, 412 — Jardim Botânico, Rio de Janeiro - RJ</span>
              </div>
            </div>

            <div class="contact-item">
              <div class="contact-item-icon" aria-hidden="true">
                <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <circle cx="12" cy="12" r="10"></circle>
                  <polyline points="12 6 12 12 16 14"></polyline>
                </svg>
              </div>
              <div>
                <strong>Horário de Acolhimento</strong>
                <span>Segunda a Sexta, das 9h às 18h</span>
              </div>
            </div>
          </div>
        </div>

        <div class="contact-form-card">
          <form action="#mensagem-enviada" method="get">
            <div class="form-row">
              <div class="form-group">
                <label for="nome" class="form-label">Nome completo</label>
                <input type="text" id="nome" name="nome" class="form-control" placeholder="Como gostaria de ser chamado?" required>
              </div>
              <div class="form-group">
                <label for="email" class="form-label">E-mail</label>
                <input type="email" id="email" name="email" class="form-control" placeholder="voce@exemplo.com.br" required>
              </div>
            </div>

            <div class="form-group">
              <label for="interesse" class="form-label">Como deseja se conectar?</label>
              <select id="interesse" name="interesse" class="form-control">
                <option value="participar">Participar das Mesas de Diálogo</option>
                <option value="parceria">Propor uma Parceria Institucional</option>
                <option value="voluntariado">Ser Voluntário ou Mentor</option>
                <option value="outro">Outros assuntos</option>
              </select>
            </div>

            <div class="form-group">
              <label for="mensagem" class="form-label">Sua mensagem</label>
              <textarea id="mensagem" name="mensagem" class="form-control" placeholder="Conte um pouco sobre você ou sua ideia..." required></textarea>
            </div>

            <button type="submit" class="btn btn-primary form-submit">
              Enviar Mensagem
            </button>

            <!-- Alerta visual de confirmação em CSS puro -->
            <div id="mensagem-enviada" class="form-feedback" role="status">
              Obrigado pelo contato! Recebemos sua mensagem com carinho e nossa equipe responderá em breve.
            </div>
          </form>
        </div>
      </div>
    </section>
  </main>

  <!-- ========================================================================
       RODAPÉ COMPLETO
       ======================================================================== -->
  <footer class="footer">
    <div class="container">
      <div class="footer-grid">
        <div class="footer-brand">
          <a href="#" class="logo">
            <span class="logo-mark" aria-hidden="true">
              <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2">
                <circle cx="9" cy="12" r="5"></circle>
                <circle cx="15" cy="12" r="5"></circle>
              </svg>
            </span>
            Kainonia
          </a>
          <p>
            Cultivando comunhão, propósito e parcerias humanas que transformam pessoas e comunidades.
          </p>
          <div class="social-links">
            <a href="#contato" class="social-link" aria-label="Instagram da Kainonia">
              <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect>
                <path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path>
                <line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line>
              </svg>
            </a>
            <a href="#contato" class="social-link" aria-label="LinkedIn da Kainonia">
              <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path>
                <rect x="2" y="9" width="4" height="12"></rect>
                <circle cx="4" cy="4" r="2"></circle>
              </svg>
            </a>
            <a href="#contato" class="social-link" aria-label="YouTube da Kainonia">
              <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M22.54 6.42a2.78 2.78 0 0 0-1.94-2C18.88 4 12 4 12 4s-6.88 0-8.6.46a2.78 2.78 0 0 0-1.94 2A29 29 0 0 0 1 11.75a29 29 0 0 0 .46 5.33A2.78 2.78 0 0 0 3.4 19c1.72.46 8.6.46 8.6.46s6.88 0 8.6-.46a2.78 2.78 0 0 0 1.94-2 29 29 0 0 0 .46-5.25 29 29 0 0 0-.46-5.33z"></path>
                <polygon points="9.75 15.02 15.5 11.75 9.75 8.48 9.75 15.02"></polygon>
              </svg>
            </a>
          </div>
        </div>

        <div>
          <h4>Navegação</h4>
          <ul class="footer-links">
            <li><a href="#essencia">Nossa Essência</a></li>
            <li><a href="#pilares">Pilares & Valores</a></li>
            <li><a href="#iniciativas">Iniciativas</a></li>
            <li><a href="#depoimento">Histórias Reais</a></li>
          </ul>
        </div>

        <div>
          <h4>Iniciativas</h4>
          <ul class="footer-links">
            <li><a href="#iniciativas">Mesas de Diálogo</a></li>
            <li><a href="#iniciativas">Laboratório de Propósito</a></li>
            <li><a href="#iniciativas">Alianças Solidárias</a></li>
            <li><a href="#contato">Seja um Parceiro</a></li>
          </ul>
        </div>

        <div>
          <h4>Transparência</h4>
          <ul class="footer-links">
            <li><a href="#contato">Relatório Anual de Impacto</a></li>
            <li><a href="#contato">Manifesto Kainonia</a></li>
            <li><a href="#contato">Política de Privacidade</a></li>
          </ul>
        </div>
      </div>

      <div class="footer-bottom">
        <span>© 2026 Kainonia — Todos os direitos reservados.</span>
        <span>Feito com propósito e espírito de comunidade.</span>
      </div>
    </div>
  </footer>

</body>
</html>
