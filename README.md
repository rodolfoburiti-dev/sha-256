📡 Monitor de Alterações de Página (HTML + CSS + JavaScript) – SHA-256

Este projeto é uma ferramenta em HTML + CSS + JavaScript puro, capaz de monitorar qualquer página da web e detectar automaticamente alterações em seu HTML, usando hashing SHA-256 via Web Crypto API.

Ideal para:
Monitorar editais e concursos
Acompanhar páginas que podem sofrer mudanças sem aviso
Observar alterações discretas em sites de terceiros
Detectar atualizações em portais públicos ou documentos online
Tudo funciona localmente, em um único arquivo .html, sem backend.

✨ Recursos Disponíveis

✅ Monitoramento automático do HTML da página indicada
✅ Cálculo de hash SHA-256 do conteúdo baixado
✅ Três hashes exibidas:

Hash da primeira leitura (baseline inicial)
Hash de referência (última leitura estável antes da mudança)
Hash atual (conteúdo do momento)

✅ Intervalo configurável de verificação (ex.: 30s, 1min, 5min)
✅ Campo de URL totalmente editável
✅ Botão “Verificar agora”
✅ Log completo de eventos e verificações
✅ Alerta instantâneo ao detectar qualquer alteração
✅ Interface bonita, responsiva, organizada e feita com Bootstrap 5
✅ Zero dependências externas além do Bootstrap (CDN)

⚠️ Importante sobre CORS (Limitação do Navegador)

Este monitor roda no navegador, portanto está sujeito às políticas de segurança de CORS (Cross-Origin Resource Sharing).

Isso significa:
🛑 Se a página que você está tentando monitorar não permitir requisições externas via fetch(), o navegador irá bloquear o acesso.
O bloqueio acontece por motivos de segurança — navegadores não permitem que páginas locais acessem livremente conteúdo HTML de outros domínios.

Exemplos
Tipo de página	Vai funcionar?
Seu próprio domínio	✅ Sim
Sites com CORS liberado	✅ Sim
Sites com CORS restrito (a maioria)	❌ Bloqueado pelo navegador
Soluções se o CORS bloquear:

Usar a versão com PHP (backend) – recomendada
Ativar extensão “Allow CORS” (para testes)
Utilizar proxy próprio (Cloudflare Worker / Node / PHP simples)
Monitorar apenas páginas do mesmo domínio que hospedar este HTML

🧪 Funcionamento do Algoritmo

A cada verificação, o monitor:
Baixa o HTML da URL
Gera um hash SHA-256

Compara com:
a hash da primeira leitura
a hash da última leitura estável
a hash imediatamente anterior

Se houver diferença, dispara:
alerta visual
alert() sonoro
atualização do log
atualização da hash de referência

📁 Estrutura do Arquivo
O projeto consiste em 1 arquivo:
monitor_pagina.html

Contendo:
Interface (Bootstrap 5)
Hash visualizador
Log de eventos
Web Crypto API (SHA-256)
Monitor periódico com setInterval()
Comparação de hashes inteligente

🚀 Como usar
Baixe o arquivo monitor_pagina.html
Abra no seu navegador (Chrome, Firefox, Edge)
Insira uma URL
Clique em Aplicar URL
Aguarde a primeira leitura
O monitor começa automaticamente

🛠 Tecnologias Utilizadas
HTML 5
CSS 3
Bootstrap 5.3
JavaScript ES6
Web Crypto API (SHA-256)
Nenhum backend. Nenhuma instalação. Apenas navegador.

📸 Captura Interna do Processo
Hash	Descrição
Primeira leitura	Hash inicial da página
Referência	Hash da última leitura estável antes de qualquer mudança
Atual	Hash do HTML coletado agora

O mecanismo evita falsos positivos porque:
Só troca a hash de referência quando uma alteração real acontece
Mantém histórico e log das leituras
Compara sempre com a leitura imediatamente anterior

🧩 Arquivo Completo (Código)
O arquivo completo com o monitor HTML+CSS+JS está disponível no repositório ou pode ser copiado da documentação acima que gerei para você.

Se quiser, posso gerar versões:
✔ com backend PHP
✔ com Node.js
✔ com Cloudflare Worker (proxy com CORS liberado)
✔ com salvamento de históricos em LocalStorage

✔ com visualizador de “diff” (diferença do HTML antigo vs novo)

📝 Licença

Este projeto é livre para uso pessoal e profissional.
Modifique conforme desejar. Nenhuma atribuição obrigatória.
