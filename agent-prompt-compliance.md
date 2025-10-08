# Prompt do Agente – Correção de Conformidade (Google Ads)

Você é um **agente de conformidade técnica e copywriting**. Corrija este projeto de landing page para ficar **100% compatível com as políticas do Google Ads**, mantendo:
1) **Pixel(s)** (Google/Meta/TikTok) instalados e funcionando;
2) **Checkout** da **Logzz** acessado **somente por clique** (sem redirecionamento automático);
3) **Copy** informativa e verificável (usar o arquivo “Landing – Textos Revisados”).

## Tarefas

### 1) Auditoria e correção de redirecionamentos
- Remova **qualquer** `<meta http-equiv="refresh">`, `window.location*`, `location.href*`, `history.pushState` ou `setTimeout` que redirecione para fora do domínio sem clique.
- O botão deve conter **href direto** para a URL de checkout da Logzz e abrir com `target="_blank" rel="noopener"`.

### 2) Substituição de textos
- Substitua os textos existentes pelos do arquivo **“Landing – Textos Revisados (Compatíveis com Google Ads)”**.
- Ajuste títulos, subtítulos, benefícios, ingredientes, políticas, FAQ e rodapé conforme o arquivo.
- Mantenha a estrutura visual (classes CSS, hierarquia de headings). Onde necessário, apenas adapte estilos para evitar quebras.

### 3) Imagens e vídeos
- Em cada imagem/vídeo:
  - Adicione `alt` descritivo sem promessas absolutas.
  - Se for IA/ilustrativa, inclua legenda “Imagem ilustrativa”.
  - Adicione a observação padrão: “*Os resultados podem variar de acordo com o tipo de cabelo.*” na seção de resultados.
- Remova elementos de prova social artificiais (ex.: “X pessoas comprando agora”, contadores falsos).

### 4) Páginas legais
- Garanta a existência e link no rodapé de:
  - `/politica-de-privacidade.html`
  - `/termos-de-uso.html`
  - `/contato.html` (opcional, se houver seção de contato na própria página)
- Se não existirem, crie versões estáticas simples e responsivas com conteúdo padrão de e-commerce físico.

### 5) Pixel(s) e rastreamento
- **Não remover** os pixels existentes.
- Certificar que estão implementados **conforme documentação oficial** (gtag.js, fbq etc.), sem obfuscação ou condicionais por IP/UA.
- Se houver captura de `gclid`, não reescrever/manipular seu valor.

### 6) Acessibilidade e performance
- Assegure apenas **um** `<h1>` por página; subtítulos como `<h2>/<h3>`.
- Garanta `aria-label` em botões/links principais.
- Adicione `loading="lazy"` em imagens fora de viewport; use `defer` em scripts não críticos (não alterar a ordem dos pixels).

### 7) Marcação do checkout
- Imediatamente acima do CTA principal, inclua o **disclosure**:
  > O pagamento e a logística de entrega são processados com segurança pela plataforma Logzz.

### 8) Relatório final (gerar `COMPLIANCE_REPORT.md`)
- Liste:
  - Redirecionamentos removidos/ajustados;
  - Textos alterados (seções impactadas);
  - Imagens/vídeos que receberam observações/alt/legendas;
  - Páginas legais criadas/atualizadas;
  - Verificação de pixels;
  - Checklist de conformidade preenchido.

**Checklist**
- [ ] Sem redirecionamento automático;
- [ ] Checkout Logzz apenas via clique com disclosure visível;
- [ ] Textos revisados e neutros;
- [ ] Páginas legais presentes e linkadas;
- [ ] Pixel(s) mantidos e em conformidade;
- [ ] Imagens/claims com aviso “resultados podem variar”;
- [ ] Acessibilidade básica OK;
- [ ] Sem contadores/urgência falsa.

## Saída
- Código atualizado;
- `COMPLIANCE_REPORT.md` com diffs resumidos;
- Confirmação de que os CTAs levam ao checkout correto da Logzz sem automação.
