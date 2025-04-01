.PHONY: help install run test lint clean docker-build docker-run docker-stop

# Variáveis
PYTHON = python3
PIP = pip
FLASK = flask
DOCKER = docker
DOCKER_COMPOSE = docker-compose
PYTEST = pytest
BLACK = black
FLAKE8 = flake8

help: ## Mostra esta mensagem de ajuda
	@echo 'Comandos disponíveis:'
	@grep -E '^[a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'

install: ## Instala as dependências do projeto
	@echo 'Instalando dependências...'
	cd backend && $(PIP) install -r requirements.txt

run-backend: ## Inicia o servidor backend
	@echo 'Iniciando servidor backend...'
	cd backend && $(FLASK) run

run-frontend: ## Inicia o servidor frontend
	@echo 'Iniciando servidor frontend...'
	cd frontend && $(PYTHON) -m http.server 8000

test: ## Executa os testes
	@echo 'Executando testes...'
	cd backend && $(PYTEST) -v

lint: ## Executa o linter e formatador de código
	@echo 'Executando linter e formatador...'
	cd backend && $(BLACK) .
	cd backend && $(FLAKE8) .

clean: ## Limpa arquivos temporários e caches
	@echo 'Limpando arquivos temporários...'
	find . -type d -name "__pycache__" -exec rm -rf {} +
	find . -type f -name "*.pyc" -delete
	find . -type f -name "*.pyo" -delete
	find . -type f -name "*.pyd" -delete
	find . -type f -name ".coverage" -delete
	find . -type d -name "*.egg-info" -exec rm -rf {} +
	find . -type d -name "*.egg" -exec rm -rf {} +
	find . -type d -name ".pytest_cache" -exec rm -rf {} +
	find . -type d -name ".coverage" -exec rm -rf {} +
	find . -type d -name "htmlcov" -exec rm -rf {} +

docker-build: ## Constrói as imagens Docker
	@echo 'Construindo imagens Docker...'
	$(DOCKER_COMPOSE) build

docker-run: ## Inicia os containers Docker
	@echo 'Iniciando containers...'
	$(DOCKER_COMPOSE) up -d

docker-stop: ## Para os containers Docker
	@echo 'Parando containers...'
	$(DOCKER_COMPOSE) down

docker-logs: ## Mostra logs dos containers
	@echo 'Mostrando logs...'
	$(DOCKER_COMPOSE) logs -f

init-db: ## Inicializa o banco de dados
	@echo 'Inicializando banco de dados...'
	cd backend && $(FLASK) db upgrade

create-migration: ## Cria uma nova migração do banco de dados
	@echo 'Criando nova migração...'
	cd backend && $(FLASK) db migrate -m "$(message)"

backup-db: ## Faz backup do banco de dados
	@echo 'Fazendo backup do banco de dados...'
	@timestamp=$$(date +%Y%m%d_%H%M%S); \
	cp backend/database.db "backup/database_$$timestamp.db"

restore-db: ## Restaura backup do banco de dados
	@echo 'Restaurando backup do banco de dados...'
	@if [ -z "$(file)" ]; then \
		echo "Especifique o arquivo de backup com 'file=<arquivo>'"; \
		exit 1; \
	fi
	cp "$(file)" backend/database.db

check-deps: ## Verifica por dependências desatualizadas
	@echo 'Verificando dependências...'
	cd backend && $(PIP) list --outdated

update-deps: ## Atualiza todas as dependências
	@echo 'Atualizando dependências...'
	cd backend && $(PIP) freeze | cut -d= -f1 | xargs -n1 $(PIP) install -U

security-check: ## Executa verificação de segurança
	@echo 'Executando verificação de segurança...'
	cd backend && safety check

generate-requirements: ## Gera arquivo requirements.txt atualizado
	@echo 'Gerando requirements.txt...'
	cd backend && $(PIP) freeze > requirements.txt

setup-dev: ## Configura ambiente de desenvolvimento
	@echo 'Configurando ambiente de desenvolvimento...'
	cp backend/.env.example backend/.env
	make install
	make init-db

prod-deploy: ## Deploy para produção
	@echo 'Realizando deploy para produção...'
	git pull
	make docker-build
	make docker-stop
	make docker-run

# Mensagem padrão se nenhum comando for especificado
default: help