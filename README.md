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
  - JMeter (performance)


## :shipit:  Técnica de Teste

**Escrita:** Utilizado padrão BDD (Behaviour Driven Development)

**Execução:** Particionamento de Equivalência.

## :earth_americas: Padrão Adotado

**Nomenclatura de Teste:** [Cenário] - [ID teste] - [Nome do teste]

**Nomenclatura de Defeito:** [API] - [Descrição]

Testes foram divididos em duas partes:

- Teste de Sistema: Foi testado a funcionalidade da aplicação conforme regras negociais.
- Teste de Performance: Foi testado perfomance da aplicação para simular diversos dados na API.


## :bar_chart: Report da Execução

1. Ao abrir o report gerado pela ferramenta qase 
2. Clicar em <Result> para obter informações mais detalhadas

- Teste de Unidade: https://app.qase.io/public/report/eac1d4291bb04ef17e3056b9582687e49dfd1f4a
- Teste de Sistema: https://app.qase.io/public/report/f5a3b8fd678938e79441e22cb666d256e3314617

## :white_check_mark: Sugestão de Melhoria

- 

