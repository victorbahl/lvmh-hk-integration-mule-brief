# Architecture — The Backend Systems

<span class="section-tag">Starting Point</span>

```mermaid {theme: 'base', themeVariables: {primaryColor: '#F5F0EB', primaryTextColor: '#1A1A1A', lineColor: '#B8B2AA', primaryBorderColor: '#B8B2AA'}, scale: 0.85}
graph LR
  OA["🛒&nbsp;Order API"] ~~~ PX["🔒&nbsp;API Proxy<br/><i style='font-size:0.8em'>(with Policy)</i>"] ~~~ BR["🌉&nbsp;MCP Bridge"]
  FA["📦&nbsp;Fulfillment API"] ~~~ PH2[ ] ~~~ BR
  DB[("🗄️&nbsp;Products DB")] ~~~ PH3[ ] ~~~ MS["🛠️&nbsp;MCP Server"]
  BR ~~~ AG["🤖&nbsp;AI Agent<br/><i style='font-size:0.8em'>(e.g. Claude Desktop)</i>"]
  MS ~~~ AG
  OA --> PX
  PX --> BR
  OA --> BR
  FA --> BR
  DB --> MS
  BR --> AG
  MS --> AG

  style OA fill:#F5F0EB,color:#1A1A1A,stroke:#B8B2AA,stroke-width:2px
  style FA fill:#F5F0EB,color:#1A1A1A,stroke:#B8B2AA,stroke-width:2px
  style DB fill:#F5F0EB,color:#1A1A1A,stroke:#B8B2AA,stroke-width:2px
  style PX fill:none,stroke:none,color:transparent
  style PH2 fill:none,stroke:none,color:transparent
  style PH3 fill:none,stroke:none,color:transparent
  style BR fill:none,stroke:none,color:transparent
  style MS fill:none,stroke:none,color:transparent
  style AG fill:none,stroke:none,color:transparent
  linkStyle 8,9,10,11,12,13,14 stroke:none
```

---
transition: none
---

# Architecture — Step 1: MCP Bridge

<span class="section-tag">Connect the APIs</span>

```mermaid {theme: 'base', themeVariables: {primaryColor: '#F5F0EB', primaryTextColor: '#1A1A1A', lineColor: '#B8B2AA'}, scale: 0.85}
graph LR
  OA["🛒&nbsp;Order API"] ~~~ PX["🔒&nbsp;API Proxy<br/><i style='font-size:0.8em'>(with Policy)</i>"] ~~~ BR["🌉&nbsp;MCP Bridge"]
  FA["📦&nbsp;Fulfillment API"] ~~~ PH2[ ] ~~~ BR
  DB[("🗄️&nbsp;Products DB")] ~~~ PH3[ ] ~~~ MS["🛠️&nbsp;MCP Server"]
  BR ~~~ AG["🤖&nbsp;AI Agent<br/><i style='font-size:0.8em'>(e.g. Claude Desktop)</i>"]
  MS ~~~ AG
  OA --> PX
  PX --> BR
  OA --> BR
  FA --> BR
  DB --> MS
  BR --> AG
  MS --> AG

  style OA fill:#F5F0EB,color:#1A1A1A,stroke:#B8B2AA,stroke-width:2px
  style FA fill:#F5F0EB,color:#1A1A1A,stroke:#B8B2AA,stroke-width:2px
  style DB fill:#F5F0EB,color:#1A1A1A,stroke:#B8B2AA,stroke-width:2px
  style BR fill:#00A1DF,color:#fff,stroke:none
  style PX fill:none,stroke:none,color:transparent
  style PH2 fill:none,stroke:none,color:transparent
  style PH3 fill:none,stroke:none,color:transparent
  style MS fill:none,stroke:none,color:transparent
  style AG fill:none,stroke:none,color:transparent
  linkStyle 8,9,12,13,14 stroke:none
```

---

# Architecture — Step 2: MCP Server

<span class="section-tag">Connect the Database</span>

```mermaid {theme: 'base', themeVariables: {primaryColor: '#F5F0EB', primaryTextColor: '#1A1A1A', lineColor: '#B8B2AA'}, scale: 0.85}
graph LR
  OA["🛒&nbsp;Order API"] ~~~ PX["🔒&nbsp;API Proxy<br/><i style='font-size:0.8em'>(with Policy)</i>"] ~~~ BR["🌉&nbsp;MCP Bridge"]
  FA["📦&nbsp;Fulfillment API"] ~~~ PH2[ ] ~~~ BR
  DB[("🗄️&nbsp;Products DB")] ~~~ PH3[ ] ~~~ MS["🛠️&nbsp;MCP Server"]
  BR ~~~ AG["🤖&nbsp;AI Agent<br/><i style='font-size:0.8em'>(e.g. Claude Desktop)</i>"]
  MS ~~~ AG
  OA --> PX
  PX --> BR
  OA --> BR
  FA --> BR
  DB --> MS
  BR --> AG
  MS --> AG

  style OA fill:#F5F0EB,color:#1A1A1A,stroke:#B8B2AA,stroke-width:2px
  style FA fill:#F5F0EB,color:#1A1A1A,stroke:#B8B2AA,stroke-width:2px
  style DB fill:#F5F0EB,color:#1A1A1A,stroke:#B8B2AA,stroke-width:2px
  style BR fill:#00A1DF,color:#fff,stroke:none
  style MS fill:#D97757,color:#fff,stroke:none
  style PX fill:none,stroke:none,color:transparent
  style PH2 fill:none,stroke:none,color:transparent
  style PH3 fill:none,stroke:none,color:transparent
  style AG fill:none,stroke:none,color:transparent
  linkStyle 8,9,13,14 stroke:none
```

---

# Architecture — Steps 3 & 4: Deploy & Test

<span class="section-tag">The Agent orchestrates everything</span>

```mermaid {theme: 'base', themeVariables: {primaryColor: '#F5F0EB', primaryTextColor: '#1A1A1A', lineColor: '#B8B2AA'}, scale: 0.85}
graph LR
  OA["🛒&nbsp;Order API"] ~~~ PX["🔒&nbsp;API Proxy<br/><i style='font-size:0.8em'>(with Policy)</i>"] ~~~ BR["🌉&nbsp;MCP Bridge"]
  FA["📦&nbsp;Fulfillment API"] ~~~ PH2[ ] ~~~ BR
  DB[("🗄️&nbsp;Products DB")] ~~~ PH3[ ] ~~~ MS["🛠️&nbsp;MCP Server"]
  BR ~~~ AG["🤖&nbsp;AI Agent<br/><i style='font-size:0.8em'>(e.g. Claude Desktop)</i>"]
  MS ~~~ AG
  OA --> PX
  PX --> BR
  OA --> BR
  FA --> BR
  DB --> MS
  BR --> AG
  MS --> AG

  style OA fill:#F5F0EB,color:#1A1A1A,stroke:#B8B2AA,stroke-width:2px
  style FA fill:#F5F0EB,color:#1A1A1A,stroke:#B8B2AA,stroke-width:2px
  style DB fill:#F5F0EB,color:#1A1A1A,stroke:#B8B2AA,stroke-width:2px
  style BR fill:#00A1DF,color:#fff,stroke:none
  style MS fill:#D97757,color:#fff,stroke:none
  style AG fill:#0A0A0A,color:#FAF8F5,stroke:#C4A265,stroke-width:2px
  style PX fill:none,stroke:none,color:transparent
  style PH2 fill:none,stroke:none,color:transparent
  style PH3 fill:none,stroke:none,color:transparent
  linkStyle 8,9 stroke:none
```

---

# Architecture — Bonus A: API Proxy + Policy

<span class="section-tag">Data masking</span>

```mermaid {theme: 'base', themeVariables: {primaryColor: '#F5F0EB', primaryTextColor: '#1A1A1A', lineColor: '#B8B2AA'}, scale: 0.85}
graph LR
  OA["🛒&nbsp;Order API"] ~~~ PX["🔒&nbsp;API Proxy<br/><i style='font-size:0.8em'>(with Policy)</i>"] ~~~ BR["🌉&nbsp;MCP Bridge"]
  FA["📦&nbsp;Fulfillment API"] ~~~ PH2[ ] ~~~ BR
  DB[("🗄️&nbsp;Products DB")] ~~~ PH3[ ] ~~~ MS["🛠️&nbsp;MCP Server"]
  BR ~~~ AG["🤖&nbsp;AI Agent<br/><i style='font-size:0.8em'>(e.g. Claude Desktop)</i>"]
  MS ~~~ AG
  OA -.-> PX
  PX --> BR
  OA --> BR
  FA --> BR
  DB --> MS
  BR --> AG
  MS --> AG

  style OA fill:#F5F0EB,color:#1A1A1A,stroke:#B8B2AA,stroke-width:2px
  style FA fill:#F5F0EB,color:#1A1A1A,stroke:#B8B2AA,stroke-width:2px
  style DB fill:#F5F0EB,color:#1A1A1A,stroke:#B8B2AA,stroke-width:2px
  style BR fill:#00A1DF,color:#fff,stroke:none
  style MS fill:#D97757,color:#fff,stroke:none
  style AG fill:#0A0A0A,color:#FAF8F5,stroke:#C4A265,stroke-width:2px
  style PX fill:#C4A265,color:#fff,stroke:none
  style PH2 fill:none,stroke:none,color:transparent
  style PH3 fill:none,stroke:none,color:transparent
  linkStyle 10 stroke:none
```