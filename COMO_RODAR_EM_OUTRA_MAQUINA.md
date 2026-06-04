# Como Rodar o Sistema em Outra Máquina (Online e Offline)

Este sistema foi construído como um **PWA (Progressive Web App)** com suporte completo a funcionamento offline através de um **Service Worker** e armazenamento local via **LocalStorage**.

Para rodá-lo em outro computador, siga um dos métodos abaixo.

---

## Método 1: Hospedagem em Servidor Web com HTTPS (Recomendado e Mais Fácil)

Como o sistema é um PWA, os navegadores modernos exigem conexões seguras (**HTTPS** ou **localhost**) para ativar o Service Worker (modo offline).

1. Faça o upload da pasta `dist/` (gerada após o build) para qualquer serviço de hospedagem estática gratuita (ex: **GitHub Pages**, **Vercel** ou **Netlify**).
2. Acesse o endereço HTTPS gerado a partir do computador de destino **com internet pela primeira vez**.
3. Na barra de endereços do navegador (Chrome ou Edge), clique no ícone de computador com uma seta para baixo (ou nos três pontinhos e em **Instalar Aplicativo / Instalar Batalhão Leste**).
4. **Pronto!** O sistema criará um atalho na Área de Trabalho do computador. A partir deste momento, você pode abrir o atalho e usar o sistema **completamente sem internet** (offline) ou com internet (online). Ele carregará instantaneamente.

---

## Método 2: Execução Local na Máquina de Destino (via Localhost)

Se preferir não hospedar na internet, copie a pasta `dist/` para a outra máquina. Por restrições de segurança do navegador, você não pode simplesmente dar duplo clique no arquivo `index.html` (abrir via `file://` bloqueia o PWA). Você precisa iniciar um servidor local simplificado:

### Opção A: Se a máquina de destino tiver Node.js instalado
1. Abra o Terminal/Prompt de Comando na pasta `dist/`.
2. Execute o comando:
   ```bash
   npx serve -s
   ```
3. Acesse no navegador o link indicado (normalmente `http://localhost:3000`).
4. Clique para instalar o aplicativo PWA no navegador.

### Opção B: Se a máquina de destino tiver Python instalado
1. Abra o Terminal na pasta `dist/`.
2. Execute o comando:
   ```bash
   python -m http.server 8080
   ```
3. Acesse `http://localhost:8080` no navegador e faça a instalação do PWA.
