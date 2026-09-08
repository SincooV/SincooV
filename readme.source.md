<!--
  ATENCAO: este README e GERADO. Nao edite este arquivo.
  Edite readme.source.md e rode: npx readme-aura build -g elcinco55
  Qualquer alteracao feita aqui e perdida no proximo build.
-->

```aura width=860 height=200 link="https://github.com/elcinco55"
(function () {
  var W = 860;
  var H = 200;

  var COL = 44;
  var ROW = 40;

  var TAGS = ['POWERBIZZ.AI', 'PUC CAMPINAS', 'CYBERSECURITY'];

  return (
    <div style={{
      width: '100%', height: '100%', display: 'flex', flexDirection: 'column',
      fontFamily: 'Inter', background: '#0a0a08', position: 'relative',
      overflow: 'hidden', boxSizing: 'border-box', borderRadius: 4,
      border: '1px solid rgba(223,218,92,0.20)',
    }}>

      <style>{`
        @keyframes float-slow {
          0%, 100% { transform: translateX(0px); opacity: 0.85; }
          50% { transform: translateX(120px); opacity: 1; }
        }
        @keyframes float-medium {
          0%, 100% { transform: translateX(0px); opacity: 0.7; }
          50% { transform: translateX(-90px); opacity: 1; }
        }
        @keyframes led {
          0%, 44% { opacity: 1; }
          45%, 100% { opacity: 0.18; }
        }
        @keyframes sweep {
          0% { transform: translateX(0px); }
          100% { transform: translateX(940px); }
        }
        #glow-1 { animation: float-slow 11s ease-in-out infinite; }
        #glow-2 { animation: float-medium 14s ease-in-out infinite; }
        #led-ident { animation: led 2.4s steps(1, end) infinite; }
        #scan { animation: sweep 9s linear infinite; }
      `}</style>

      <svg width={W} height={H} style={{ position: 'absolute', top: 0, left: 0 }}>
        <defs>
          <radialGradient id="g1" cx="50%" cy="50%" r="50%">
            <stop offset="0%" stopColor="rgba(223,218,92,0.42)" />
            <stop offset="45%" stopColor="rgba(172,166,66,0.18)" />
            <stop offset="70%" stopColor="rgba(172,166,66,0)" />
          </radialGradient>
          <radialGradient id="g2" cx="50%" cy="50%" r="50%">
            <stop offset="0%" stopColor="rgba(172,166,66,0.34)" />
            <stop offset="50%" stopColor="rgba(140,136,52,0.14)" />
            <stop offset="70%" stopColor="rgba(140,136,52,0)" />
          </radialGradient>
          <radialGradient id="g3" cx="50%" cy="50%" r="50%">
            <stop offset="0%" stopColor="rgba(206,201,74,0.22)" />
            <stop offset="55%" stopColor="rgba(160,155,58,0)" />
          </radialGradient>
          <linearGradient id="sheen" x1="0" y1="0" x2="1" y2="1">
            <stop offset="0%" stopColor="rgba(255,255,255,0.045)" />
            <stop offset="45%" stopColor="rgba(255,255,255,0.010)" />
            <stop offset="100%" stopColor="rgba(0,0,0,0.32)" />
          </linearGradient>
          <filter id="grain" x="0" y="0" width="100%" height="100%">
            <feTurbulence type="fractalNoise" baseFrequency="0.9" numOctaves="2" stitchTiles="stitch" result="noise" />
            <feColorMatrix type="saturate" values="0" />
          </filter>
          <linearGradient id="beam" x1="0" y1="0" x2="1" y2="0">
            <stop offset="0%" stopColor="rgba(223,218,92,0)" />
            <stop offset="100%" stopColor="rgba(223,218,92,0.10)" />
          </linearGradient>
        </defs>

        <ellipse id="glow-1" cx="150" cy="205" rx="250" ry="150" fill="url(#g1)" />
        <ellipse id="glow-2" cx="360" cy="215" rx="220" ry="140" fill="url(#g2)" />
        <ellipse id="glow-3" cx="560" cy="200" rx="180" ry="120" fill="url(#g3)" />

        {Array.from({ length: Math.ceil(W / COL) }).map(function (_, i) {
          return <rect key={'v' + i} x={i * COL} y="0" width="1" height={H} fill="rgba(223,218,92,0.055)" />;
        })}
        {Array.from({ length: Math.ceil(H / ROW) - 1 }).map(function (_, i) {
          return <rect key={'h' + i} x="0" y={(i + 1) * ROW} width={W} height="1" fill="rgba(223,218,92,0.045)" />;
        })}

        <g id="scan">
          <rect x="-70" y="0" width="64" height={H} fill="url(#beam)" />
          <rect x="-6" y="0" width="1" height={H} fill="rgba(223,218,92,0.38)" />
        </g>

        <rect x="0" y="0" width={W} height={H} fill="url(#sheen)" />
        <rect x="0" y="0" width={W} height={H} filter="url(#grain)" opacity="0.11" />

        <rect x="12" y="38" width="10" height="1" fill="rgba(223,218,92,0.6)" />
        <rect x="12" y="38" width="1" height="10" fill="rgba(223,218,92,0.6)" />
        <rect x={W - 22} y="38" width="10" height="1" fill="rgba(223,218,92,0.6)" />
        <rect x={W - 13} y="38" width="1" height="10" fill="rgba(223,218,92,0.6)" />
        <rect x="12" y={H - 13} width="10" height="1" fill="rgba(223,218,92,0.6)" />
        <rect x="12" y={H - 22} width="1" height="10" fill="rgba(223,218,92,0.6)" />
        <rect x={W - 22} y={H - 13} width="10" height="1" fill="rgba(223,218,92,0.6)" />
        <rect x={W - 13} y={H - 22} width="1" height="10" fill="rgba(223,218,92,0.6)" />
      </svg>

      <div style={{
        display: 'flex', flexDirection: 'row', alignItems: 'center',
        justifyContent: 'space-between', height: 26, flexShrink: 0,
        padding: '0 12px', borderBottom: '1px solid rgba(223,218,92,0.18)',
      }}>
        <div style={{ display: 'flex', flexDirection: 'row', alignItems: 'center', gap: 8 }}>
          <div id="led-ident" style={{ display: 'flex', width: 5, height: 5, borderRadius: 1, background: '#DFDA5C' }} />
          <div style={{ display: 'flex', fontSize: 9, fontWeight: 700, letterSpacing: '2.4px', color: 'rgba(223,218,92,0.62)' }}>
            IDENT
          </div>
        </div>
        <div style={{ display: 'flex', fontSize: 9, fontWeight: 700, letterSpacing: '2.4px', color: 'rgba(196,190,130,0.42)' }}>
          GITHUB.COM/ELCINCO55
        </div>
      </div>

      <div style={{ display: 'flex', flexDirection: 'row', flexGrow: 1 }}>

        <div style={{
          display: 'flex', flexDirection: 'column', width: 46, flexShrink: 0,
          alignItems: 'center', justifyContent: 'center', gap: 6,
          borderRight: '1px solid rgba(223,218,92,0.16)',
        }}>
          {Array.from({ length: 7 }).map(function (_, i) {
            var long = i % 3 === 0;
            return <div key={'t' + i} style={{
              display: 'flex', width: long ? 14 : 7, height: 1,
              background: long ? 'rgba(223,218,92,0.45)' : 'rgba(223,218,92,0.20)',
            }} />;
          })}
        </div>

        <div style={{
          display: 'flex', flexDirection: 'column', flexGrow: 1,
          justifyContent: 'center', padding: '0 22px',
        }}>
          <div style={{ display: 'flex', flexDirection: 'row', alignItems: 'center', gap: 9 }}>
            <div style={{ display: 'flex', width: 16, height: 1, background: '#DFDA5C' }} />
            <div style={{ display: 'flex', fontSize: 9.5, fontWeight: 700, letterSpacing: '2.4px', color: 'rgba(223,218,92,0.92)' }}>
              INFORMATION SECURITY ANALYST
            </div>
            <div style={{ display: 'flex', flexGrow: 1, height: 1, background: 'rgba(223,218,92,0.18)' }} />
          </div>

          <div style={{ display: 'flex', flexDirection: 'column', marginTop: 12 }}>
            <div style={{ display: 'flex', fontSize: 42, fontWeight: 700, letterSpacing: '-1.4px', lineHeight: 1, color: '#ffffff' }}>
              VITOR
            </div>
            <div style={{ display: 'flex', fontSize: 42, fontWeight: 700, letterSpacing: '-1.4px', lineHeight: 1, color: 'rgba(233,229,175,0.32)' }}>
              TAVARES
            </div>
          </div>

          <div style={{ display: 'flex', flexDirection: 'row', alignItems: 'center', gap: 9, marginTop: 14 }}>
            {TAGS.map(function (item, i) {
              return (
                <div key={item} style={{ display: 'flex', flexDirection: 'row', alignItems: 'center', gap: 9 }}>
                  {i > 0 ? <div style={{ display: 'flex', width: 1, height: 9, background: 'rgba(223,218,92,0.30)' }} /> : null}
                  <div style={{ display: 'flex', fontSize: 10, fontWeight: 700, letterSpacing: '1.6px', color: 'rgba(233,229,175,0.72)' }}>
                    {item}
                  </div>
                </div>
              );
            })}
            <div style={{ display: 'flex', flexGrow: 1, height: 1, marginLeft: 9, background: 'rgba(223,218,92,0.18)' }} />
          </div>
        </div>

        <div style={{
          display: 'flex', width: 150, flexShrink: 0, alignItems: 'center',
          justifyContent: 'center', borderLeft: '1px solid rgba(223,218,92,0.16)',
        }}>
          <div style={{ display: 'flex', position: 'relative', width: 118, height: 118, alignItems: 'center', justifyContent: 'center' }}>
            <div style={{
              display: 'flex', width: 104, height: 104, borderRadius: 52,
              background: 'linear-gradient(135deg, #DFDA5C, #ACA642)',
              alignItems: 'center', justifyContent: 'center',
            }}>
              <img src=".github/img/avatar.png" width={96} height={96} style={{ borderRadius: 48 }} />
            </div>
            <div style={{ display: 'flex', position: 'absolute', top: 0, left: 0, width: 10, height: 10, borderTop: '1px solid rgba(223,218,92,0.65)', borderLeft: '1px solid rgba(223,218,92,0.65)' }} />
            <div style={{ display: 'flex', position: 'absolute', top: 0, right: 0, width: 10, height: 10, borderTop: '1px solid rgba(223,218,92,0.65)', borderRight: '1px solid rgba(223,218,92,0.65)' }} />
            <div style={{ display: 'flex', position: 'absolute', bottom: 0, left: 0, width: 10, height: 10, borderBottom: '1px solid rgba(223,218,92,0.65)', borderLeft: '1px solid rgba(223,218,92,0.65)' }} />
            <div style={{ display: 'flex', position: 'absolute', bottom: 0, right: 0, width: 10, height: 10, borderBottom: '1px solid rgba(223,218,92,0.65)', borderRight: '1px solid rgba(223,218,92,0.65)' }} />
          </div>
        </div>
      </div>
    </div>
  );
})()
```

> Go is my main language, but I use whatever gets the job done.

```aura width=860 height=220
(function () {
  var W = 860;
  var H = 220;

  var COL = 44;

  var GROUPS = [
    { label: 'LANGUAGES',  items: ['Go', 'C', 'Lua'] },
    { label: 'FRAMEWORKS', items: ['Gin'] },
    { label: 'DATABASES',  items: ['PostgreSQL', 'MySQL', 'SQLite'] },
    { label: 'INFRA',      items: ['Docker', 'Kubernetes', 'AWS'] },
    { label: 'PENTESTING', items: ['Web', 'Cloud'] },
    { label: 'TOOLS',      items: ['Nmap', 'Burp Suite', 'Wireshark', 'Metasploit', 'BlackArch'] },
  ];

  // Todo numero visivel no card sai daqui: nenhuma contagem escrita na mao.
  function pad(n) {
    return n < 10 ? '0' + n : String(n);
  }

  var entries = GROUPS.reduce(function (sum, group) {
    return sum + group.items.length;
  }, 0);

  return (
    <div style={{
      width: '100%', height: '100%', display: 'flex', flexDirection: 'column',
      fontFamily: 'Inter', background: '#0a0a08', position: 'relative',
      overflow: 'hidden', boxSizing: 'border-box', borderRadius: 4,
      border: '1px solid rgba(223,218,92,0.20)',
    }}>

      <style>{`
        @keyframes led {
          0%, 44% { opacity: 1; }
          45%, 100% { opacity: 0.18; }
        }
        #led-stack { animation: led 2.4s steps(1, end) infinite; }
      `}</style>

      <svg width={W} height={H} style={{ position: 'absolute', top: 0, left: 0 }}>
        <defs>
          <filter id="grain-stack" x="0" y="0" width="100%" height="100%">
            <feTurbulence type="fractalNoise" baseFrequency="0.9" numOctaves="2" stitchTiles="stitch" result="noise" />
            <feColorMatrix type="saturate" values="0" />
          </filter>
        </defs>

        {Array.from({ length: Math.ceil(W / COL) }).map(function (_, i) {
          return <rect key={'v' + i} x={i * COL} y="0" width="1" height={H} fill="rgba(223,218,92,0.045)" />;
        })}

        <rect x="0" y="0" width={W} height={H} filter="url(#grain-stack)" opacity="0.09" />
      </svg>

      <div style={{
        display: 'flex', flexDirection: 'row', alignItems: 'center',
        justifyContent: 'space-between', height: 26, flexShrink: 0,
        padding: '0 12px', borderBottom: '1px solid rgba(223,218,92,0.18)',
      }}>
        <div style={{ display: 'flex', flexDirection: 'row', alignItems: 'center', gap: 8 }}>
          <div id="led-stack" style={{ display: 'flex', width: 5, height: 5, borderRadius: 1, background: '#DFDA5C' }} />
          <div style={{ display: 'flex', fontSize: 9, fontWeight: 700, letterSpacing: '2.4px', color: 'rgba(223,218,92,0.62)' }}>
            STACK
          </div>
        </div>
        <div style={{ display: 'flex', fontSize: 9, fontWeight: 700, letterSpacing: '2.4px', color: 'rgba(196,190,130,0.42)' }}>
          {pad(entries) + ' ENTRIES'}
        </div>
      </div>

      {GROUPS.map(function (group, g) {
        var last = g === GROUPS.length - 1;
        return (
          <div key={group.label} style={{
            display: 'flex', flexDirection: 'row', alignItems: 'center', flexGrow: 1,
            padding: '0 16px',
            borderBottom: last ? '1px solid rgba(0,0,0,0)' : '1px solid rgba(223,218,92,0.12)',
          }}>
            <div style={{ display: 'flex', width: 116, flexShrink: 0, fontSize: 9.5, fontWeight: 700, letterSpacing: '2.4px', color: 'rgba(196,190,130,0.75)' }}>
              {group.label}
            </div>
            <div style={{ display: 'flex', flexDirection: 'row', alignItems: 'center', flexShrink: 0 }}>
              {group.items.map(function (item, i) {
                return (
                  <div key={item} style={{ display: 'flex', flexDirection: 'row', alignItems: 'center' }}>
                    {i > 0 ? <div style={{ display: 'flex', padding: '0 8px', fontSize: 11, color: 'rgba(223,218,92,0.28)' }}>/</div> : null}
                    {item === 'Go' ? (
                      <div style={{
                        display: 'flex', padding: '2px 9px', borderRadius: 3,
                        background: '#DFDA5C', color: '#0a0a08', fontSize: 12.5, fontWeight: 700,
                      }}>{item}</div>
                    ) : (
                      <div style={{ display: 'flex', fontSize: 12.5, color: 'rgba(242,239,214,0.92)' }}>{item}</div>
                    )}
                  </div>
                );
              })}
            </div>
            <div style={{ display: 'flex', flexGrow: 1, height: 1, marginLeft: 16, background: 'rgba(223,218,92,0.14)' }} />
          </div>
        );
      })}
    </div>
  );
})()
```

```aura width=268 height=44 link="https://www.linkedin.com/in/vitor-leite-398481331/" inline align=center
<div style={{
  width: '100%', height: '100%', display: 'flex', flexDirection: 'row',
  alignItems: 'center', justifyContent: 'space-between', fontFamily: 'Inter',
  background: '#0a0a08', boxSizing: 'border-box', padding: '0 14px',
  border: '1px solid rgba(223,218,92,0.38)',
  borderTopLeftRadius: 4, borderBottomLeftRadius: 4,
}}>
  <div style={{ display: 'flex', flexDirection: 'row', alignItems: 'center', gap: 8 }}>
    <div style={{ display: 'flex', width: 5, height: 5, borderRadius: 1, background: 'rgba(223,218,92,0.50)' }} />
    <div style={{ display: 'flex', fontSize: 9, fontWeight: 700, letterSpacing: '1.8px', color: 'rgba(223,218,92,0.8)' }}>01</div>
    <div style={{ display: 'flex', fontSize: 10.5, fontWeight: 700, letterSpacing: '2.4px', color: '#f4f1d8' }}>LINKEDIN</div>
  </div>
  <div style={{ display: 'flex', fontSize: 10, letterSpacing: '0.3px', color: 'rgba(233,229,175,0.52)' }}>vitor-leite</div>
</div>
```

```aura width=324 height=44 link="mailto:vitor.tavares.leite@gmail.com" inline align=center
<div style={{
  width: '100%', height: '100%', display: 'flex', flexDirection: 'row',
  alignItems: 'center', justifyContent: 'space-between', fontFamily: 'Inter',
  background: '#0a0a08', boxSizing: 'border-box', padding: '0 14px',
  border: '1px solid rgba(223,218,92,0.38)',
}}>
  <div style={{ display: 'flex', flexDirection: 'row', alignItems: 'center', gap: 8 }}>
    <div style={{ display: 'flex', width: 5, height: 5, borderRadius: 1, background: 'rgba(223,218,92,0.50)' }} />
    <div style={{ display: 'flex', fontSize: 9, fontWeight: 700, letterSpacing: '1.8px', color: 'rgba(223,218,92,0.8)' }}>02</div>
    <div style={{ display: 'flex', fontSize: 10.5, fontWeight: 700, letterSpacing: '2.4px', color: '#f4f1d8' }}>E-MAIL</div>
  </div>
  <div style={{ display: 'flex', fontSize: 10, letterSpacing: '0.3px', color: 'rgba(233,229,175,0.52)' }}>vitor.tavares.leite@gmail.com</div>
</div>
```

```aura width=268 height=44 inline align=center
<div style={{
  width: '100%', height: '100%', display: 'flex', flexDirection: 'row',
  alignItems: 'center', justifyContent: 'space-between', fontFamily: 'Inter',
  background: '#0a0a08', boxSizing: 'border-box', padding: '0 14px',
  border: '1px solid rgba(223,218,92,0.38)',
  borderTopRightRadius: 4, borderBottomRightRadius: 4,
}}>
  <div style={{ display: 'flex', flexDirection: 'row', alignItems: 'center', gap: 8 }}>
    <div style={{ display: 'flex', width: 5, height: 5, borderRadius: 1, background: 'rgba(223,218,92,0.50)' }} />
    <div style={{ display: 'flex', fontSize: 9, fontWeight: 700, letterSpacing: '1.8px', color: 'rgba(223,218,92,0.8)' }}>03</div>
    <div style={{ display: 'flex', fontSize: 10.5, fontWeight: 700, letterSpacing: '2.4px', color: '#f4f1d8' }}>DISCORD</div>
  </div>
  <div style={{ display: 'flex', fontSize: 10, letterSpacing: '0.3px', color: 'rgba(233,229,175,0.52)' }}>cincao_</div>
</div>
```
