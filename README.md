<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1180 610" width="100%" height="100%">
  <defs>
    <style>
      @import url('https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500;600;700&amp;family=Inter:wght@400;500;600;700;800&amp;display=swap');
      
      .text-sans { font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif; }
      .text-mono { font-family: 'Fira Code', monospace; }

      .border-glow {
        stroke: url(#accent-grad);
        stroke-dasharray: 200 800;
        animation: borderShimmer 8s linear infinite;
      }

      @keyframes borderShimmer {
        0% { stroke-dashoffset: 1000; }
        100% { stroke-dashoffset: 0; }
      }
      @keyframes floatAscii {
        0%, 100% { transform: translateY(0px); }
        50% { transform: translateY(-6px); }
      }
      @keyframes pulseGlow {
        0%, 100% { opacity: 0.5; filter: drop-shadow(0 0 12px rgba(124, 58, 237, 0.4)); }
        50% { opacity: 0.9; filter: drop-shadow(0 0 22px rgba(34, 211, 238, 0.7)); }
      }
      @keyframes scanline {
        0% { transform: translateY(-100%); }
        100% { transform: translateY(610px); }
      }

      .ascii-container { animation: floatAscii 6s ease-in-out infinite, pulseGlow 4s ease-in-out infinite; }
      .scanline-anim { animation: scanline 8s linear infinite; }

      .pill-group { transition: transform 0.2s ease; cursor: pointer; }
      .pill-group:hover { transform: translateY(-2px); }
      .pill-group:hover .pill-bg { fill: rgba(124, 58, 237, 0.25); stroke: rgba(34, 211, 238, 0.8); }
      .pill-group:hover .pill-text { fill: #FFFFFF; }
    </style>

    <linearGradient id="bg-grad" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" stop-color="#030712"/>
      <stop offset="50%" stop-color="#0B0F19"/>
      <stop offset="100%" stop-color="#030712"/>
    </linearGradient>

    <linearGradient id="panel-grad" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" stop-color="#0F172A" stop-opacity="0.8"/>
      <stop offset="100%" stop-color="#0B1120" stop-opacity="0.6"/>
    </linearGradient>

    <linearGradient id="accent-grad" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" stop-color="#7C3AED">
        <animate attributeName="stop-color" values="#7C3AED; #22D3EE; #10B981; #7C3AED" dur="10s" repeatCount="indefinite" />
      </stop>
      <stop offset="50%" stop-color="#22D3EE">
        <animate attributeName="stop-color" values="#22D3EE; #10B981; #7C3AED; #22D3EE" dur="10s" repeatCount="indefinite" />
      </stop>
      <stop offset="100%" stop-color="#10B981">
        <animate attributeName="stop-color" values="#10B981; #7C3AED; #22D3EE; #10B981" dur="10s" repeatCount="indefinite" />
      </stop>
    </linearGradient>

    <linearGradient id="ascii-grad" x1="0%" y1="0%" x2="0%" y2="100%">
      <stop offset="0%" stop-color="#22D3EE"/>
      <stop offset="50%" stop-color="#7C3AED"/>
      <stop offset="100%" stop-color="#10B981"/>
    </linearGradient>

    <radialGradient id="orb-purple" cx="20%" cy="20%" r="60%">
      <stop offset="0%" stop-color="#7C3AED" stop-opacity="0.2"/>
      <stop offset="100%" stop-color="#030712" stop-opacity="0"/>
    </radialGradient>

    <radialGradient id="orb-cyan" cx="80%" cy="80%" r="60%">
      <stop offset="0%" stop-color="#22D3EE" stop-opacity="0.18"/>
      <stop offset="100%" stop-color="#030712" stop-opacity="0"/>
    </radialGradient>

    <filter id="glow" x="-20%" y="-20%" width="140%" height="140%">
      <feGaussianBlur stdDeviation="6" result="blur" />
      <feComposite in="SourceGraphic" in2="blur" operator="over" />
    </filter>

    <clipPath id="card-clip">
      <rect x="0" y="0" width="1180" height="610" rx="24" ry="24" />
    </clipPath>
  </defs>

  <g clip-path="url(#card-clip)">
    <!-- Base Background -->
    <rect width="1180" height="610" fill="url(#bg-grad)"/>

    <!-- Ambient Orbs -->
    <circle cx="200" cy="150" r="350" fill="url(#orb-purple)"/>
    <circle cx="950" cy="450" r="400" fill="url(#orb-cyan)"/>

    <!-- Grid -->
    <g opacity="0.04" stroke="#FFFFFF" stroke-width="1">
      <pattern id="grid" width="40" height="40" patternUnits="userSpaceOnUse">
        <path d="M 40 0 L 0 0 0 40" fill="none"/>
      </pattern>
      <rect width="1180" height="610" fill="url(#grid)" />
    </g>

    <!-- Border Glow -->
    <rect x="2" y="2" width="1176" height="606" rx="23" ry="23" fill="none" stroke="rgba(255,255,255,0.08)" stroke-width="1.5"/>
    <rect x="2" y="2" width="1176" height="606" rx="23" ry="23" fill="none" class="border-glow" stroke-width="2"/>

    <!-- LEFT PANEL: Cyber ASCII Hero -->
    <g transform="translate(40, 40)">
      <rect width="410" height="530" rx="16" fill="url(#panel-grad)" stroke="rgba(255,255,255,0.08)" stroke-width="1"/>

      <!-- Controls -->
      <circle cx="24" cy="24" r="5" fill="#EF4444" opacity="0.8"/>
      <circle cx="40" cy="24" r="5" fill="#F59E0B" opacity="0.8"/>
      <circle cx="56" cy="24" r="5" fill="#10B981" opacity="0.8"/>
      <text x="390" y="28" fill="#64748B" font-size="11" class="text-mono" text-anchor="end">ascii_avatar.sh</text>
      <line x1="0" y1="44" x2="410" y2="44" stroke="rgba(255,255,255,0.05)" stroke-width="1"/>

      <g class="ascii-container" transform="translate(25, 65)">
        <text fill="url(#ascii-grad)" class="text-mono" font-size="9.5" font-weight="700" letter-spacing="1" xml:space="preserve">
          <tspan x="0" dy="0">██████╗  █████╗  ██████╗██╗  ██╗██╗████████╗</tspan>
          <tspan x="0" dy="12">██╔══██╗██╔══██╗██╔════╝██║  ██║██║╚══██╔══╝</tspan>
          <tspan x="0" dy="12">██████╔╝███████║██║     ███████║██║   ██║   </tspan>
          <tspan x="0" dy="12">██╔══██╗██╔══██║██║     ██╔══██║██║   ██║   </tspan>
          <tspan x="0" dy="12">██║  ██║██║  ██║╚██████╗██║  ██║██║   ██║   </tspan>
          <tspan x="0" dy="12">╚═╝  ╚═╝╚═╝  ╚═╝ ╚═════╝╚═╝  ╚═╝╚═╝   ╚═╝   </tspan>
          <tspan x="0" dy="20">███╗   ██╗███████╗████████╗                 </tspan>
          <tspan x="0" dy="12">████╗  ██║██╔════╝╚══██╔══╝                 </tspan>
          <tspan x="0" dy="12">██╔██╗ ██║█████╗     ██║                    </tspan>
          <tspan x="0" dy="12">██║╚██╗██║██╔══╝     ██║                    </tspan>
          <tspan x="0" dy="12">██║ ╚████║███████╗   ██║                    </tspan>
          <tspan x="0" dy="12">╚═╝  ╚═══╝╚══════╝   ╚═╝                    </tspan>
        </text>

        <!-- Hologram Graphic Core -->
        <g transform="translate(20, 190)">
          <rect width="320" height="230" rx="12" fill="rgba(15,23,42,0.6)" stroke="rgba(34,211,238,0.25)" stroke-width="1"/>
          
          <circle cx="160" cy="115" r="55" fill="none" stroke="url(#accent-grad)" stroke-width="1.5" stroke-dasharray="4 4">
            <animateTransform attributeName="transform" type="rotate" from="0 160 115" to="360 160 115" dur="20s" repeatCount="indefinite"/>
          </circle>
          <circle cx="160" cy="115" r="38" fill="none" stroke="#22D3EE" stroke-width="1" stroke-dasharray="8 8">
            <animateTransform attributeName="transform" type="rotate" from="360 160 115" to="0 160 115" dur="10s" repeatCount="indefinite"/>
          </circle>
          <polygon points="160,75 190,135 130,135" fill="none" stroke="#7C3AED" stroke-width="1.5">
            <animateTransform attributeName="transform" type="rotate" from="0 160 115" to="360 160 115" dur="14s" repeatCount="indefinite"/>
          </polygon>
          <circle cx="160" cy="115" r="5" fill="#10B981" filter="url(#glow)"/>

          <text x="15" y="25" fill="#22D3EE" class="text-mono" font-size="10" font-weight="600">&gt; SYSTEM: ONLINE</text>
          <text x="15" y="42" fill="#94A3B8" class="text-mono" font-size="9">&gt; LOC: 21.1702° N, 72.8311° E</text>
          <text x="15" y="212" fill="#10B981" class="text-mono" font-size="9">&gt; STATUS: BUILDING THE FUTURE</text>
        </g>
      </g>
    </g>

    <!-- RIGHT PANEL: Main Content Terminal -->
    <g transform="translate(475, 40)">
      <rect width="665" height="530" rx="16" fill="url(#panel-grad)" stroke="rgba(255,255,255,0.08)" stroke-width="1"/>

      <!-- Header Bar -->
      <path d="M0,16 Q0,0 16,0 L649,0 Q665,0 665,16 L665,44 L0,44 Z" fill="rgba(255,255,255,0.02)"/>
      <circle cx="24" cy="22" r="5" fill="#EF4444" opacity="0.8"/>
      <circle cx="40" cy="22" r="5" fill="#F59E0B" opacity="0.8"/>
      <circle cx="56" cy="22" r="5" fill="#10B981" opacity="0.8"/>
      <text x="332" y="26" fill="#64748B" font-size="12" class="text-mono" text-anchor="middle">rachit@developer:~</text>
      <line x1="0" y1="44" x2="665" y2="44" stroke="rgba(255,255,255,0.05)" stroke-width="1"/>

      <!-- Properly Spaced Content Area -->
      <g transform="translate(35, 65)">
        
        <!-- Row 1: Greeting -->
        <text x="0" y="20" fill="#22D3EE" class="text-mono" font-size="14" font-weight="600">Hi 👋, I'm</text>
        
        <!-- Row 2: Large Title -->
        <text x="0" y="62" fill="#F8FAFC" class="text-sans" font-size="32" font-weight="800" letter-spacing="-0.5">Rachit Makwana</text>

        <!-- Row 3: Subtitle / Dynamic Role -->
        <g transform="translate(0, 95)">
          <text x="0" y="0" fill="#94A3B8" class="text-mono" font-size="14">
            <tspan fill="#7C3AED" font-weight="700">&gt;</tspan> 
            <tspan fill="#F8FAFC" font-weight="500">Software Developer</tspan>
            <tspan fill="#64748B"> | </tspan>
            <tspan fill="#22D3EE">Python &amp; Web Development</tspan>
          </text>
          
          <rect x="382" y="-11" width="8" height="16" fill="#22D3EE">
            <animate attributeName="opacity" values="1;0;1" dur="0.8s" repeatCount="indefinite"/>
          </rect>
        </g>

        <!-- Row 4: Information Columns -->
        <g transform="translate(0, 130)">
          <line x1="0" y1="0" x2="595" y2="0" stroke="rgba(255,255,255,0.06)" stroke-width="1"/>
          
          <g transform="translate(0, 20)">
            <text x="0" y="0" fill="#64748B" class="text-mono" font-size="10" letter-spacing="0.5">LOCATION</text>
            <text x="0" y="18" fill="#CBD5E1" class="text-sans" font-size="13" font-weight="500">🇮🇳 India</text>
          </g>
          
          <g transform="translate(160, 20)">
            <text x="0" y="0" fill="#64748B" class="text-mono" font-size="10" letter-spacing="0.5">DEGREE</text>
            <text x="0" y="18" fill="#CBD5E1" class="text-sans" font-size="13" font-weight="500">B.Tech (2027)</text>
          </g>
          
          <g transform="translate(320, 20)">
            <text x="0" y="0" fill="#64748B" class="text-mono" font-size="10" letter-spacing="0.5">CURRENT FOCUS</text>
            <text x="0" y="18" fill="#22D3EE" class="text-sans" font-size="13" font-weight="600">Open Source &amp; Backend</text>
          </g>

          <line x1="0" y1="50" x2="595" y2="50" stroke="rgba(255,255,255,0.06)" stroke-width="1"/>
        </g>

        <!-- Row 5: Skills Grid -->
        <g transform="translate(0, 215)">
          <text x="0" y="0" fill="#64748B" class="text-mono" font-size="10" letter-spacing="1">SKILLS &amp; TECHNOLOGIES</text>
          
          <g transform="translate(0, 12)">
            <!-- Python -->
            <g class="pill-group" transform="translate(0,0)">
              <rect class="pill-bg" width="75" height="26" rx="13" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.1)" stroke-width="1"/>
              <text class="pill-text" x="37.5" y="17" fill="#E2E8F0" class="text-sans" font-size="11" font-weight="500" text-anchor="middle">Python</text>
            </g>
            <!-- React -->
            <g class="pill-group" transform="translate(83,0)">
              <rect class="pill-bg" width="70" height="26" rx="13" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.1)" stroke-width="1"/>
              <text class="pill-text" x="35" y="17" fill="#E2E8F0" class="text-sans" font-size="11" font-weight="500" text-anchor="middle">React</text>
            </g>
            <!-- Next.js -->
            <g class="pill-group" transform="translate(161,0)">
              <rect class="pill-bg" width="75" height="26" rx="13" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.1)" stroke-width="1"/>
              <text class="pill-text" x="37.5" y="17" fill="#E2E8F0" class="text-sans" font-size="11" font-weight="500" text-anchor="middle">Next.js</text>
            </g>
            <!-- Node.js -->
            <g class="pill-group" transform="translate(244,0)">
              <rect class="pill-bg" width="75" height="26" rx="13" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.1)" stroke-width="1"/>
              <text class="pill-text" x="37.5" y="17" fill="#E2E8F0" class="text-sans" font-size="11" font-weight="500" text-anchor="middle">Node.js</text>
            </g>
            <!-- TypeScript -->
            <g class="pill-group" transform="translate(327,0)">
              <rect class="pill-bg" width="90" height="26" rx="13" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.1)" stroke-width="1"/>
              <text class="pill-text" x="45" y="17" fill="#E2E8F0" class="text-sans" font-size="11" font-weight="500" text-anchor="middle">TypeScript</text>
            </g>
            <!-- Tailwind -->
            <g class="pill-group" transform="translate(425,0)">
              <rect class="pill-bg" width="80" height="26" rx="13" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.1)" stroke-width="1"/>
              <text class="pill-text" x="40" y="17" fill="#E2E8F0" class="text-sans" font-size="11" font-weight="500" text-anchor="middle">Tailwind</text>
            </g>
          </g>

          <g transform="translate(0, 46)">
            <!-- Docker -->
            <g class="pill-group" transform="translate(0,0)">
              <rect class="pill-bg" width="75" height="26" rx="13" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.1)" stroke-width="1"/>
              <text class="pill-text" x="37.5" y="17" fill="#E2E8F0" class="text-sans" font-size="11" font-weight="500" text-anchor="middle">Docker</text>
            </g>
            <!-- Postgres -->
            <g class="pill-group" transform="translate(83,0)">
              <rect class="pill-bg" width="88" height="26" rx="13" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.1)" stroke-width="1"/>
              <text class="pill-text" x="44" y="17" fill="#E2E8F0" class="text-sans" font-size="11" font-weight="500" text-anchor="middle">PostgreSQL</text>
            </g>
            <!-- AWS -->
            <g class="pill-group" transform="translate(179,0)">
              <rect class="pill-bg" width="60" height="26" rx="13" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.1)" stroke-width="1"/>
              <text class="pill-text" x="30" y="17" fill="#E2E8F0" class="text-sans" font-size="11" font-weight="500" text-anchor="middle">AWS</text>
            </g>
            <!-- Git -->
            <g class="pill-group" transform="translate(247,0)">
              <rect class="pill-bg" width="55" height="26" rx="13" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.1)" stroke-width="1"/>
              <text class="pill-text" x="27.5" y="17" fill="#E2E8F0" class="text-sans" font-size="11" font-weight="500" text-anchor="middle">Git</text>
            </g>
            <!-- Figma -->
            <g class="pill-group" transform="translate(310,0)">
              <rect class="pill-bg" width="65" height="26" rx="13" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.1)" stroke-width="1"/>
              <text class="pill-text" x="32.5" y="17" fill="#E2E8F0" class="text-sans" font-size="11" font-weight="500" text-anchor="middle">Figma</text>
            </g>
          </g>
        </g>

        <!-- Row 6: Links / Actions -->
        <g transform="translate(0, 320)">
          <line x1="0" y1="0" x2="595" y2="0" stroke="rgba(255,255,255,0.06)" stroke-width="1"/>
          
          <g transform="translate(0, 18)">
            <!-- GitHub -->
            <a href="https://github.com/Rachit7168" target="_blank">
              <g class="pill-group" transform="translate(0,0)">
                <rect class="pill-bg" width="38" height="38" rx="10" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.1)" stroke-width="1"/>
                <path d="M19 10C14.03 10 10 14.03 10 19C10 22.98 12.58 26.35 16.15 27.54C16.6 27.62 16.77 27.35 16.77 27.11C16.77 26.9 16.76 26.2 16.76 25.44C14.28 25.98 13.76 24.52 13.58 24.01C13.48 23.75 13.02 22.91 12.61 22.68C12.28 22.5 11.79 22.05 12.6 22.04C13.35 22.03 13.89 22.73 14.07 23.02C14.93 24.47 16.3 24.06 16.85 23.81C16.94 23.22 17.17 22.82 17.43 22.6C15.52 22.38 13.52 21.64 13.52 18.35C13.52 17.41 13.85 16.64 14.4 16.03C14.31 15.81 14.02 14.93 14.49 13.74C14.49 13.74 15.21 13.51 16.86 14.63C17.55 14.44 18.28 14.34 19 14.34C19.72 14.34 20.45 14.44 21.14 14.63C22.79 13.5 23.51 13.74 23.51 13.74C23.98 14.93 23.69 15.81 23.6 16.03C24.15 16.64 24.48 17.4 24.48 18.35C24.48 21.65 22.47 22.38 20.56 22.6C20.89 22.88 21.18 23.43 21.18 24.28C21.18 25.5 21.17 26.49 21.17 26.8C21.17 27.04 21.34 27.33 21.79 27.24C25.35 26.05 27.93 22.67 27.93 17.71C27.93 12.75 23.9 8.71 18.93 8.71" fill="#CBD5E1"/>
              </g>
            </a>

            <!-- LinkedIn -->
            <a href="https://www.linkedin.com/in/rachit-makwana-py-dev/" target="_blank">
              <g class="pill-group" transform="translate(48,0)">
                <rect class="pill-bg" width="38" height="38" rx="10" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.1)" stroke-width="1"/>
                <path d="M13.5 12C12.67 12 12 12.67 12 13.5C12 14.33 12.67 15 13.5 15C14.33 15 15 14.33 15 13.5C15 12.67 14.33 12 13.5 12Z" fill="#CBD5E1"/>
                <path d="M12.2 16.8H14.8V25H12.2V16.8Z" fill="#CBD5E1"/>
                <path d="M17.2 16.8H19.8V17.9C20.2 17.3 21.1 16.6 22.5 16.6C25.1 16.6 25.5 18.1 25.5 20.7V25H22.9V21.2C22.9 20 22.5 19.1 21.3 19.1C20.3 19.1 19.8 19.9 19.8 21V25H17.2V16.8Z" fill="#CBD5E1"/>
              </g>
            </a>

            <!-- Portfolio Link Button -->
            <a href="https://clam-african-port.vercel.app/" target="_blank">
              <g class="pill-group" transform="translate(96,0)">
                <rect class="pill-bg" width="150" height="38" rx="10" fill="rgba(124,58,237,0.18)" stroke="rgba(34,211,238,0.4)" stroke-width="1"/>
                <text x="75" y="23" fill="#22D3EE" class="text-sans" font-size="12" font-weight="600" text-anchor="middle">🌐 Portfolio Website</text>
              </g>
            </a>

            <!-- Direct Email Link Button -->
            <a href="mailto:rachitmakwana15@gmail.com">
              <g class="pill-group" transform="translate(256,0)">
                <rect class="pill-bg" width="120" height="38" rx="10" fill="rgba(255,255,255,0.04)" stroke="rgba(255,255,255,0.1)" stroke-width="1"/>
                <text x="60" y="23" fill="#E2E8F0" class="text-sans" font-size="12" font-weight="500" text-anchor="middle">✉️ Get in Touch</text>
              </g>
            </a>
          </g>
        </g>

      </g>
    </g>

    <!-- Scanline Sweep -->
    <rect x="0" y="0" width="1180" height="6" fill="url(#accent-grad)" opacity="0.2" class="scanline-anim"/>
  </g>
</svg>
