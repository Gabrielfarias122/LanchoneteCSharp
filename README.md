CHAPA QUENTE LANCHES - Sistema web de lanchonete (C# / ASP.NET Core MVC)

COMO RODAR
1. Instale o .NET SDK 8 ou mais novo: https://dotnet.microsoft.com/download
   (confira no terminal com:  dotnet --version)
2. Abra esta pasta no VS Code (Arquivo > Abrir Pasta).
   Dica: instale a extensão "C# Dev Kit" quando o VS Code sugerir.
3. Abra o terminal do VS Code (Ctrl + ') e rode:
       dotnet run
   Na primeira vez precisa de internet para baixar o pacote do banco (SQLite).
4. Abra no navegador:  http://localhost:5080

O banco de dados (lanchonete.db) é criado sozinho na primeira execução,
já com o administrador, um cliente de teste e 12 produtos.
Para zerar tudo, pare o programa e apague o arquivo lanchonete.db.

CONTAS PARA TESTE
Administrador: admin@chapaquente.com  /  admin123
Cliente:       cliente@teste.com      /  123456
(também dá para criar novas contas de cliente em "Criar conta")

TECNOLOGIAS
C#, ASP.NET Core MVC (Razor), Entity Framework Core + SQLite,
autenticação por cookie com perfis (Admin e Cliente), senhas com PBKDF2.

O QUE O SISTEMA FAZ
- Cadastro de conta, login e logout, com permissões diferentes
- Cliente: monta o carrinho, finaliza o pedido, acompanha o andamento,
  cancela pedidos recém-feitos e edita seus dados
- Administrador: resumo de vendas, pedidos (muda o status), produtos
  (cadastrar, editar, excluir, ocultar, enviar foto), usuários (bloquear)
  e histórico de todas as operações realizadas
- Busca por nome, filtro por categoria e ordenação por preço
- Imagens dos produtos (wwwroot/images) e upload de fotos (wwwroot/uploads)

ESTRUTURA
Controllers/  lógica de cada tela        Models/       tabelas do banco
Views/        telas (Razor)              ViewModels/   dados das telas
Data/         banco e dados iniciais     Services/     senha, formatos, carrinho
wwwroot/      css, imagens e uploads     Program.cs    configuração do sistema
