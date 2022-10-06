<div align="center">
  <img src="https://media.giphy.com/media/dWesBcTLavkZuG35MI/giphy.gif" width="600" height="300"/>
</div>

---

# Desafio API Builders

O objetivo do desafio é testar 3 apis de pix. O contexto da aplicação é realizar pagamento via PIX a partir de dados coletados do QR Code.

## :pushpin: Requisitos

- **Account**
    - Deve ser possível obter os dados da conta a partir do ***id da conta***
- **PIX**
    - **Codes**
        - O ***QR Code*** deve ser enviado convertido em base64
        - A Aplicação deve validar se é um ***QR Code*** válido
        - A aplicação deve validar se o ***QR Code*** existe
        - Em caso de erro, a aplicação deve devolver o motivo no response
        - A aplicação deve devolver os dados para realizar um pagamento via PIX
    - **Payment**
        - Receber os dados de pagamento de acordo com os dados obtidos em ***Account*** e ***Pix/Codes***


## :wrench: Stack utilizada

**Escrita:** https://app.qase.io/

**Execução:** 
  - Postman (versão desktop) - https://www.postman.com/
  - JMeter (performance) - https://jmeter.apache.org/


## :shipit:  Técnica de Teste

**Escrita:** Utilizado padrão BDD (Behaviour Driven Development)

**Execução:** Particionamento de Equivalência.

## :earth_americas: Padrão Adotado

**Nomenclatura de Teste:** [Cenário] - [ID teste] - [Nome do teste]

**Nomenclatura de Defeito:** [API] - [Descrição]

Testes foram divididos em duas partes:

- Teste Funcional: Foi testado as requisições conforme regras negociais.
- Teste de Performance: Foi testado perfomance da aplicação para simular diversos dados na API.


## :bar_chart: Report da Execução

1. Ao abrir o report gerado pela ferramenta qase 
2. Clicar em <Result> para obter informações mais detalhadas

- Link: <a href="https://app.qase.io/public/report/2b2f9d92d097f7f1ed0c0e607780752d83e38811"> Report API </a>

## :sob: Report de Bugs

- Foi gerada planilha excel e adicionada no github com imagens e descrição dos bug encontrados. Foi seguido o seguinte padrão para classificação dos bugs:

:red_circle: Block - Bloqueia completamente a utilização de uma funcionalidade básica ou da aplicação inteira

:yellow_circle: Major - Bloqueia a utilização de uma funcionalidade, mas não impede que o sistema possa ser utilizado por meio de alguma correção paleativa.

:green_circle: Minor - Problemas de baixa complexidade ou melhorias. Exemplo: Cor do botão está incorreto. Deveria ser verde e está com cor azul.

## :white_check_mark: Sugestão de Melhoria

- API de pagamento (/pix/payments) poderia ter um campos status de pagamento conforme especificação da API do BACEN
  - ATIVA: indica que o registro se refere a uma cobrança que foi gerada mas ainda não foi paga nem removida;
  - CONCLUIDA: indica que o registro se refere a uma cobrança que já foi paga e, por conseguinte, não pode acolher outro pagamento;
  - REMOVIDO_PELO_USUARIO_RECEBEDOR: indica que o usuário recebedor solicitou a remoção do registro da cobrança; e
  - REMOVIDO_PELO_PSP: indica que o PSP Recebedor solicitou a remoção do registro da cobrança.
  
  Referência: https://bacen.github.io/pix-api/
  
 - Não há documentação da API. Seria interessante documentar toda a API utilizando a ferramenta https://swagger.io/
  
## :stopwatch: Análise de Performance  
  
 - Não foi descrito qual o tempo de resposta ideal da API, porém foi agregado esse teste para verificar a resposta da aplicação. Podemos notar que existe um tempo sginificativo nas resposta e poderíamos melhorar o código. Print da análise está nas respectivas pastas do git.
  
  
 - Estimativa baseada em 10 usuários simultâneos
  
  API Account: Em média 90% dos usuários recebem a resposta em 1936ms
  
  API Pix Codes: Em média 90% dos usuários recebem a resposta em 1628ms
  
  API Pix Payments: Não foi possível avaliar a requisição, pois existe um bug crítico na API
  
 - Foi incluído no git o arquivo de configuração (JMeter) para teste da API.

