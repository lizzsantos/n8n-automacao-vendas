# Automação de Processo de Vendas com n8n

Automação de um processo de vendas em 3 fluxos integrados, feita no n8n com Google Sheets, Gmail e Gemini.

## Fluxos

### 1. Envio do pedido
Formulário de pedido grava uma linha no Google Sheets, envia um e-mail de aviso ao cliente e chama o fluxo de confirmação de entrega (sub-workflow).

### 2. Confirmação de entrega
Envia um e-mail de confirmação que aguarda a resposta e, em seguida, dispara o e-mail com a pesquisa de satisfação.

### 3. Pesquisa de satisfação
Quando uma resposta entra na planilha, um nó de decisão verifica se o cliente está insatisfeito. Se estiver, o Gemini classifica o motivo (qualidade, prazo, defeito, preço ou atendimento) e o Gmail envia [o que o e-mail faz: ex. uma resposta ao cliente].

## Como os fluxos se conectam
Pedido → Confirmação de entrega → Pesquisa de satisfação.

## Ferramentas
n8n | Google Sheets | Gmail | Gemini (Google AI)

## Estrutura do repositório
- `workflows/`: arquivos JSON dos 3 fluxos
- `prints/`: imagens dos fluxos no n8n
- `docs/`: fluxograma do processo de vendas (modelado antes da automação)

## Como importar
No n8n, crie um novo fluxo e use **Import from file** com o JSON da pasta `workflows/`. Será preciso conectar suas próprias credenciais (Google e Gemini).

## Autora
Eliza Pinheiro | www.linkedin.com/in/elizasantospinheiro
