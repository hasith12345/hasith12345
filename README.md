<!-- paste into a webpage (index.html or component) -->
<style>
  :root{
    --bg: #07121a;
    --card: #071a22;
    --accent: #63d1ff;
    --accent-2: #3fb0ff;
    --muted: #9aa7b1;
    --glass: rgba(255,255,255,0.03);
  }

  body {
    background: linear-gradient(180deg,#041018 0%, #07121a 100%);
    color: #e6f2f8;
    font-family: Inter, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    padding: 36px;
  }

  .profile {
    max-width: 900px;
  }

  /* animated name */
  .name {
    font-size: 48px;
    margin: 0 0 8px 0;
    font-weight: 700;
    letter-spacing: -0.5px;
    line-height: 1;
    display: inline-block;
    /* gradient text */
    background: linear-gradient(90deg, #b7f0ff, var(--accent), #b4e0ff 70%);
    background-size: 200% 100%;
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
    animation: shine 3.2s linear infinite;
    position: relative;
    /* gentle vertical float */
    transform-origin: center;
    animation-name: shine, floaty;
    animation-duration: 3.2s, 4.8s;
    animation-timing-function: linear, ease-in-out;
    animation-iteration-count: infinite, infinite;
  }

  @keyframes shine {
    0% { background-position: 0% 50% }
    50% { background-position: 100% 50% }
    100% { background-position: 0% 50% }
  }
  @keyframes floaty {
    0% { transform: translateY(0px) }
    50% { transform: translateY(-6px) }
    100% { transform: translateY(0px) }
  }

  .desc {
    color: var(--muted);
    margin: 6px 0 20px 0;
    max-width: 700px;
    line-height: 1.45;
  }

  /* contact bar */
  .contact-bar {
    display: flex;
    gap: 12px;
    background: linear-gradient(90deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
    padding: 10px;
    border-radius: 10px;
    align-items: center;
    width: fit-content;
    box-shadow: 0 6px 18px rgba(5,10,14,0.6);
  }

  .contact-item {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 92px;            /* like in screenshot - adjust */
    height: 46px;
    border-radius: 8px;
    background: linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.00));
    position: relative;
    text-decoration: none;
    color: #cfeffb;
    transition: transform .18s ease, box-shadow .18s ease;
    padding: 6px;
  }

  .contact-item:hover{
    transform: translateY(-4px);
    box-shadow: 0 8px 28px rgba(63,176,255,0.08);
  }

  .contact-item svg {
    width: 26px;
    height: 26px;
    display:block;
    filter: drop-shadow(0 1px 0 rgba(0,0,0,0.2));
  }

  /* small blue segment under each icon */
  .contact-item .accent-seg {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    bottom: -6px;
    width: 20px;
    height: 4px;
    border-radius: 4px;
    background: linear-gradient(90deg, var(--accent), var(--accent-2));
    box-shadow: 0 4px 10px rgba(63,176,255,0.14), 0 0 10px rgba(99,209,255,0.06);
    opacity: 0.95;
    animation: pulseSeg 1.8s infinite;
  }

  @keyframes pulseSeg{
    0% { transform: translateX(-50%) scaleX(.85); opacity:.6; }
    50% { transform: translateX(-50%) scaleX(1.1); opacity:1; }
    100% { transform: translateX(-50%) scaleX(.85); opacity:.6; }
  }

  /* small micro-dots that appear between items (optional) */
  .contact-bar::after{
    content:'';
    position:absolute;
    pointer-events:none;
  }

  /* responsive */
  @media (max-width:520px){
    .name { font-size: 34px }
    .contact-item { width: 72px; height: 40px; }
    .contact-item svg { width:22px; height:22px;}
  }
</style>

<div class="profile">
  <h1 class="name">Hasith Gamlath</h1>

  <p class="desc">
    B.Sc. (Hons.) IT & Management undergraduate<br/>
    Passionate about full-stack web development and building user-friendly applications using modern web technologies.
  </p>

  <div class="contact-bar" role="navigation" aria-label="contact links">
    <!-- Instagram -->
    <a class="contact-item" href="https://instagram.com/hasiya_21" target="_blank" aria-label="Instagram">
      <!-- simple inline Instagram svg -->
      <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
        <rect x="2" y="2" width="20" height="20" rx="5" fill="transparent" stroke="currentColor" stroke-opacity="0.08" />
        <path d="M7.75 2.75h8.5A4.5 4.5 0 0 1 21.5 7.25v9.5a4.5 4.5 0 0 1-4.25 4.25h-8.5A4.5 4.5 0 0 1 4.5 16.75v-9.5A4.5 4.5 0 0 1 7.75 2.75z" fill="none" stroke="currentColor" stroke-opacity="0.12"/>
        <circle cx="12" cy="12" r="3.3" stroke="currentColor" stroke-opacity="0.9" fill="none"/>
        <circle cx="18.2" cy="5.8" r="0.6" fill="currentColor" fill-opacity="0.95"/>
      </svg>
      <span class="accent-seg"></span>
    </a>

    <!-- Email (Gmail) -->
    <a class="contact-item" href="mailto:hasithgamlath327@gmail.com" aria-label="Email">
      <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
        <rect x="1.5" y="3.5" width="21" height="17" rx="3" fill="none" stroke="currentColor" stroke-opacity="0.06"/>
        <path d="M3 6.5l8.8 6.2a2 2 0 0 0 2.4 0L22 6.5" stroke="currentColor" stroke-opacity="0.9" fill="none"/>
      </svg>
      <span class="accent-seg"></span>
    </a>

    <!-- LinkedIn -->
    <a class="contact-item" href="https://www.linkedin.com/in/hasith-gamlath-18b957274" target="_blank" aria-label="LinkedIn">
      <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
        <rect x="2" y="2" width="20" height="20" rx="3" fill="none" stroke="currentColor" stroke-opacity="0.06"/>
        <path d="M6.3 9.8v7.7" stroke="currentColor" stroke-opacity="0.95" stroke-linecap="round"/>
        <circle cx="6.3" cy="6.9" r="0.9" fill="currentColor" fill-opacity="0.95"/>
        <path d="M11.1 12.5v4.9M11.1 9.5v.2" stroke="currentColor" stroke-opacity="0.95" stroke-linecap="round"/>
        <path d="M16.0 12.5v4.9" stroke="currentColor" stroke-opacity="0.95" stroke-linecap="round"/>
      </svg>
      <span class="accent-seg"></span>
    </a>

    <!-- Portfolio (you can replace with a globe icon) -->
    <a class="contact-item" href="https://hasithgamlath.vercel.app" target="_blank" aria-label="Portfolio">
      <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
        <circle cx="12" cy="12" r="9.2" fill="none" stroke="currentColor" stroke-opacity="0.08"/>
        <path d="M2 12h20M12 2c2.6 3.8 2.6 3.8 0 20" stroke="currentColor" stroke-opacity="0.9"/>
      </svg>
      <span class="accent-seg"></span>
    </a>
  </div>
</div>
