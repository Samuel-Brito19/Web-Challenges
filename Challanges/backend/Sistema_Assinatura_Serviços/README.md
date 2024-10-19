
# Desafio 3: Sistema de Assinaturas de Serviços

## Cenário:
Você está criando um sistema de assinatura onde usuários podem se inscrever em serviços oferecidos por diferentes provedores. Usuários podem pagar por uma assinatura e acessar o serviço durante o período de vigência.

## Regras de Negócio:
1. Os usuários devem ter Nome, E-mail, CPF (únicos no sistema) e saldo disponível para pagar por assinaturas.
2. Os **Provedores de Serviço** oferecem assinaturas com diferentes preços e durações.
3. O sistema deve validar se o usuário tem saldo suficiente antes de completar a assinatura.
4. Após o pagamento da assinatura, o serviço deve ser ativado para o usuário e uma notificação deve ser enviada ao provedor.
5. O sistema deve permitir a renovação automática da assinatura caso o saldo do usuário seja suficiente.
6. As transações de pagamento devem ser processadas de forma segura e, em caso de falha, a assinatura não deve ser ativada.
7. Use o mock https://util.devi.tools/api/v2/authorize (GET) para autorizar a assinatura e https://util.devi.tools/api/v1/notify (POST) para notificar o provedor.

## Endpoints:
### Assinar Serviço:
```
POST /subscribe
Content-Type: application/json

{
  "userId": 3,
  "serviceId": 7,
  "amount": 50.0
}
```