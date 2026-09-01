# 🎬 ClipMaker - Crie Clipes Virais com IA

O **ClipMaker** é uma aplicação web de página única desenvolvida para identificar e extrair automaticamente os momentos mais impactantes e virais de um vídeo utilizando Inteligência Artificial; projeto que é parte da trilha 1 do nlw-operator 2026, da Rocketseat.

---

## 🚀 Como Funciona a Aplicação

1. 🔑 **Chave de API**: O usuário insere sua chave pessoal de API da Google Gemini diretamente na interface.
2. 📤 **Upload de Vídeo**: O usuário seleciona um vídeo através do widget integrado do Cloudinary.
3. 📜 **Busca de Transcrição**: Após o upload, a aplicação aguarda a disponibilidade do arquivo de transcrição gerado pelo Cloudinary.
4. 🤖 **Análise Inteligente**: A transcrição do vídeo é enviada para a API do Gemini com instruções para localizar o trecho mais impactante (com duração entre 30 e 60 segundos).
5. 🎬 **Exibição do Clipe**: A aplicação monta o link de corte com base nos tempos calculados pela IA (`so_<inicio>,eo_<fim>`) e exibe o clipe viral pronto no player.

---

## 🔌 Destaque: Integração com APIs

### 1. ☁️ Cloudinary Upload Widget
- **Upload Direct**: Interface para upload de vídeos a partir do dispositivo local, câmera ou URL.
- **Transcrição e Edição**: Fornece o arquivo `.transcript` do vídeo enviado e realiza o corte dinâmico através de parâmetros de transformação de mídia na URL (`so_...`, `eo_...`).

### 2. 🧠 Google Gemini API (`gemini-2.5-flash`)
- **Requisição HTTP**: A aplicação realiza requisições `POST` diretamente para o endpoint `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash:generateContent`.
- **Autenticação**: Autenticado via cabeçalho HTTP `x-goog-api-key`.
- **Engenharia de Prompt**: Instruções estruturadas para analisar o texto da transcrição e retornar estritamente os marcadores de início e fim no formato esperado pelo Cloudinary (exemplo: `so_10,eo_40`).

---

## 🛠️ Tecnologias Utilizadas

- **HTML5 & JavaScript (Vanilla)**: Estrutura e lógica principal da aplicação.
- **Tailwind CSS**: Estilização responsiva e moderna via CDN.
- **GSAP (GreenSock)**: Animações de entrada de elementos e transição para a exibição do vídeo.
- **Lucide Icons**: Ícones da interface.
- **Cloudinary SDK / Widget**: Gerenciamento de mídias.
- **Google Gemini API**: Processamento e análise de linguagem natural.
