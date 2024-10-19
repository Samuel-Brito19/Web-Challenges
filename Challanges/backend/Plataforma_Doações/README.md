
# Desafio 1: Plataforma de Doações

## Cenário:
Você está desenvolvendo uma plataforma de doações onde usuários podem fazer doações para causas específicas. A plataforma tem dois tipos de usuários: **Doadores** e **Organizações de Caridade**.

## Regras de Negócio:
1. Cada usuário (Doador ou Organização de Caridade) deve ter Nome Completo, E-mail, CPF/CNPJ (únicos no sistema) e uma carteira de saldo.
2. **Doadores** podem doar para as **Organizações de Caridade**, mas não entre si.
3. **Organizações de Caridade** só podem receber doações, não podem realizar transferências ou doações.
4. Antes de finalizar uma doação, o sistema deve validar se o Doador tem saldo suficiente para a transação.
5. A doação deve ser processada como uma transação segura, ou seja, em caso de falha ou inconsistência, a operação deve ser revertida.
6. O sistema deve enviar uma notificação para a **Organização de Caridade** após a doação ser concluída com sucesso.
7. Deve existir um serviço de terceiros para notificar a organização. Use o mock https://util.devi.tools/api/v1/notify (POST) para simular o envio de notificações.

## Endpoint de Doação:
```
POST /donate
Content-Type: application/json

{
  "value": 150.0,
  "donor": 3,
  "charity": 8
}
```