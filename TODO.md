# TODO: Configurar envio do formulário por email

## Passos para configurar o EmailJS:

1. Acesse https://www.emailjs.com/ e crie uma conta gratuita.
2. Vá para "Email Services" e adicione um novo serviço (escolha Gmail).
3. Configure o serviço com seu email (elizaalanoca12@gmail.com) e a senha de app fornecida (xurp alpu eeak cusr).
4. Vá para "Email Templates" e crie um novo template.
   - No campo "Subject", defina algo como: "Novo contato do site: {{from_name}}".
   - No campo "Content" (corpo do email), inclua as variáveis exatamente onde deseja que elas apareçam. As variáveis disponíveis são:
     - {{from_name}} para o nome do visitante
     - {{from_email}} para o email do visitante
     - {{message}} para a mensagem
     - {{to_email}} para o seu email (elizaalanoca12@gmail.com)
   - Exemplo completo de template (copie e cole no campo Content):
     ```
     Olá Elizabeth,

     Você recebeu um novo contato através do seu site de portfólio.

     Detalhes do visitante:
     Nome: {{from_name}}
     Email: {{from_email}}

     Mensagem:
     {{message}}

     Responder para: {{from_email}}

     Atenciosamente,
     Sistema de Contato do Site
     ```
   - Certifique-se de que as variáveis estão entre chaves duplas {{ }} e sem espaços extras. Se o template não incluir {{from_name}} e {{from_email}}, o email só mostrará a mensagem.
5. Anote o Service ID (do serviço Gmail), Template ID (do template criado) e Public Key (no dashboard da conta).
6. No arquivo script.js, substitua:
   - "YOUR_PUBLIC_KEY" pela sua Public Key
   - "YOUR_SERVICE_ID" pelo Service ID do Gmail
   - "YOUR_TEMPLATE_ID" pelo Template ID
7. Salve o script.js e teste o formulário: abra index.html no navegador, role até "Contato", preencha nome, email e mensagem, envie. Deve aparecer alerta "Mensagem enviada com sucesso!" e você receber o email completo com nome, email e mensagem.

## Observações:
- O envio é feito diretamente do navegador, sem necessidade de backend.
- Certifique-se de que o email de destino está correto no templateParams.
- Se houver erros, verifique o console do navegador.
