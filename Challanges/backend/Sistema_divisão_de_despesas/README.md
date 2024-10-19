
# Desafio 2: Sistema de Divisão de Despesas

## Cenário:
Você está criando um sistema para dividir despesas entre amigos. Os usuários podem criar um grupo de despesas, adicionar participantes, e realizar o pagamento das suas respectivas partes.

## Regras de Negócio:
1. Os usuários devem ter Nome, E-mail e CPF (únicos no sistema) e um saldo inicial.
2. Um usuário pode criar um **Grupo de Despesa**, onde ele define o total da despesa e os participantes.
3. Cada participante do grupo terá uma parte proporcional da despesa que precisa pagar.
4. Os pagamentos entre os usuários do grupo são realizados diretamente de suas carteiras.
5. Antes de realizar o pagamento, o sistema deve validar se o usuário tem saldo suficiente.
6. Caso todos os participantes paguem suas partes, a despesa será marcada como quitada.
7. O sistema deve notificar os membros do grupo sobre o status da despesa. Use o mock https://util.devi.tools/api/v1/notify para simular o envio de notificações.

## Endpoints:
### Criar Grupo de Despesa:
```
POST /expense-group
Content-Type: application/json

{
  "name": "Jantar com Amigos",
  "totalAmount": 300.0,
  "members": [2, 4, 5]
}
```
  
### Pagar Parte da Despesa:
```
POST /pay-expense
Content-Type: application/json

{
  "groupId": 1,
  "payer": 2,
  "amount": 100.0
}