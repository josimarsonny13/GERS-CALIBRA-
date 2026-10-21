# GERS CALIBRA

Aplicativo web instalável (PWA) de calibração de barras pulverizadoras, com identidade visual G.E.R.S. FLORESTAL. Funciona no Android pelo Chrome e pode operar offline após o primeiro acesso online.

## Entradas
- Volume de aplicação em L/ha
- Velocidade em km/h
- Quantidade de bicos
- Faixa efetiva em metros (sem exigir espaçamento entre bicos)

## Resultados
Vazão total em L/min, vazão individual em mL/min, coleta em 30 segundos, capacidade operacional teórica em ha/h e tempo teórico por hectare. Histórico salvo localmente no aparelho.

## Publicar no GitHub Pages
1. Entre em https://github.com/new e crie um repositório chamado `GERS-CALIBRA` com visibilidade **Public** (ou escolha Private caso seu plano suporte Pages privado).
2. No repositório, escolha **Add file → Upload files** e envie **os arquivos e a pasta `.github` deste pacote, mantendo `index.html` na raiz**. A interface do GitHub pode ocultar arquivos iniciados por ponto; nesse caso, use GitHub Desktop ou Git para enviar o projeto completo.
3. Confirme o envio na branch `main`.
4. Em **Settings → Pages → Build and deployment → Source**, selecione **GitHub Actions**.
5. Em **Actions**, acompanhe o fluxo `Publicar GERS CALIBRA no GitHub Pages`. Após o deploy, abra `https://SEU_USUARIO.github.io/GERS-CALIBRA/`.
6. No Chrome Android, abra o endereço publicado e escolha **⋮ → Adicionar à tela inicial** ou **Instalar app**, se disponível.

### Alternativa sem usar o workflow
Em **Settings → Pages**, selecione **Deploy from a branch**, branch `main`, pasta `/(root)` e salve. O GitHub Pages servirá o `index.html` diretamente.

## Fórmulas
- `vazao_total_l_min = (volume_l_ha * velocidade_km_h * largura_m) / 600`
- `vazao_por_bico_ml_min = (vazao_total_l_min / numero_bicos) * 1000`
- `capacidade_ha_h = (velocidade_km_h * largura_m) / 10`

**Atenção:** cálculos teóricos, supondo largura efetiva informada e distribuição uniforme. Calibre com água limpa, confira cada bico e siga bula e fabricante.

## Limitações
Este projeto é um **PWA**, não um APK nativo. GitHub Pages publica um site instalável pelo navegador, mas não gera APK automaticamente. O histórico fica no armazenamento do navegador, não é sincronizado entre dispositivos.
