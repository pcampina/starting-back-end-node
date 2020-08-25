# Recuperação de senha

**RF (Requisitos Funcionais)**

- O usuário deve poder recuperar sua senha informando o seu e-mail
- O usuário deve receber um e-mail com instruções com recuperação de senha
- O usuário deve poder resetar sua senha

**RNF (Requisitos não funcionais)**

- Utilizar Mailtrap para testar envios em ambiente de desenvolvimento
- Utilizar Amazon SES para envios em produção
- O envio de e-mails deve acontecer em segundo plano (background job)

**RN (Regras de negócio)**

- O link enviado por e-mail para resetar senha deve expirar em 2 horas
- O usuário precisa confirmar a nova senha ao resetar a sua senha

# Atualização de Perfil

**RF**

- O usuário deve poder atualizar seu perfil (nome, email e senha)

**RN**

- O usuário não pode alterar o e-mail para um e-mail já utilizado
- Para atualizar sua senha, o usuário deve informar sua senha antiga
- Para atualizar sua senha, o usuário precisa confirmar a nova senha

# Painel do Prestador

**RF**

- O usuário deve poder listar seus agendamentos de um dia especifico
- O prestador deve receber uma notificação sempre que houver um novo agendamento
- O prestador deve poder visualizar as notificações não lidas

**RNF**

- Os agendamentos do prestador no dia devem ser armazenados em cache
- As notificações do prestador devem ser armazenadas no MongoDB
- As notificações do prestador devem ser enviadas em tempo-real utilizando socket.io

**RN**

- A notificação deve ter um status de lida ou não lida para que o prestador possa controlar seus horarios

# Agendamento de Serviços

**RF**

- O usuário deve poder listar todos os prestadores de serviços cadastrados
- O usuário deve conseguir listar pelo menos 1 prestador com dia e horario disponível
- O usuário deve poder listar horários disponíveis em um dia específico de um prestador
- O usuário deve poder realizar um novo agendamento com um prestador

**RNF**

- A listagem de prestadores deve ser armazenada em cache

**RN**

- Cada agendamento deve durar 1 hora exatamente
- Os agendamentos devem estar disponíveis entre 8h às 18h (Primeiro horário às 8H, último às 17h)
- O usuário não pode agendar em um horário já ocupado
- O usuário não pode agendar em um horário que já passou
- O usuário não pode agendar serviços consigo mesmo
