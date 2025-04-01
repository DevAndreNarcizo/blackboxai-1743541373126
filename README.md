
AutoBiz - Sistema de Automação para Pequenos Negócios
Sistema web completo para automatizar a gestão de pequenos negócios, incluindo controle de estoque, emissão de notas fiscais e integração com WhatsApp.

Funcionalidades
Controle de Estoque

Cadastro e gestão de produtos
Controle de entrada e saída
Alertas de estoque baixo
Relatórios de movimentação
Notas Fiscais

Emissão de notas fiscais
Gestão de clientes
Histórico de emissões
Cancelamento de notas
Integração WhatsApp

Recebimento de pedidos
Gestão de status
Notificações automáticas
Histórico de conversas
Dashboard

Visão geral do negócio
Gráficos de vendas
Produtos mais vendidos
Indicadores de desempenho
Tecnologias Utilizadas
Backend
Python 3.8+
Flask (Framework Web)
SQLAlchemy (ORM)
JWT (Autenticação)
SQLite (Banco de Dados)
Frontend
HTML5
Tailwind CSS
JavaScript
Font Awesome
Google Fonts
Requisitos
Python 3.8 ou superior
Node.js 14 ou superior (para desenvolvimento frontend)
SQLite3
Instalação
Clone o repositório:
git clone https://github.com/seu-usuario/autobiz.git
cd autobiz
Crie e ative um ambiente virtual Python:
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows
Instale as dependências do backend:
cd backend
pip install -r requirements.txt
Configure as variáveis de ambiente:
cp .env.example .env
# Edite o arquivo .env com suas configurações
Inicialize o banco de dados:
flask db upgrade
Executando o Projeto
Inicie o servidor backend:
cd backend
flask run
Abra o frontend:
cd frontend
python -m http.server 8000
Acesse a aplicação em seu navegador:
http://localhost:8000
Estrutura do Projeto
ferramenta-automacao/
├── backend/
│   ├── routes/
│   │   ├── auth.py
│   │   ├── dashboard.py
│   │   ├── estoque.py
│   │   ├── notas.py
│   │   └── whatsapp.py
│   ├── utils/
│   │   ├── error_handlers.py
│   │   └── logger.py
│   ├── app.py
│   ├── config.py
│   ├── models.py
│   └── requirements.txt
├── frontend/
│   ├── dashboard.html
│   ├── estoque.html
│   ├── index.html
│   ├── login.html
│   ├── notas.html
│   ├── pedidos.html
│   ├── registro.html
│   └── configuracoes.html
└── README.md
Planos e Limites
Plano Free
Até 50 produtos cadastrados
30 notas fiscais por mês
Dashboard básico
Suporte por email
Plano Premium
Produtos ilimitados
Notas fiscais ilimitadas
Dashboard completo
Suporte prioritário
Relatórios avançados
Contribuindo
Faça um Fork do projeto
Crie uma branch para sua feature (git checkout -b feature/AmazingFeature)
Commit suas mudanças (git commit -m 'Add some AmazingFeature')
Push para a branch (git push origin feature/AmazingFeature)
Abra um Pull Request
Segurança
Autenticação via JWT
Senhas criptografadas
Proteção contra CSRF
Validação de inputs
Logs de segurança
Suporte
Para suporte, envie um email para suporte@autobiz.com ou abra uma issue no GitHub.

Licença
Este projeto está licenciado sob a licença MIT - veja o arquivo LICENSE para detalhes.

Autor
Desenvolvido por Seu Nome

Agradecimentos
Flask
Tailwind CSS
Font Awesome
Google Fonts