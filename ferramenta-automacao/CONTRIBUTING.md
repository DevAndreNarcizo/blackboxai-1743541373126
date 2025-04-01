# Guia de Contribuição

Obrigado por considerar contribuir com o AutoBiz! Este documento fornece diretrizes e instruções para contribuir com o projeto.

## Índice

1. [Código de Conduta](#código-de-conduta)
2. [Como Contribuir](#como-contribuir)
3. [Ambiente de Desenvolvimento](#ambiente-de-desenvolvimento)
4. [Padrões de Código](#padrões-de-código)
5. [Processo de Commit](#processo-de-commit)
6. [Pull Requests](#pull-requests)
7. [Reportando Bugs](#reportando-bugs)
8. [Sugerindo Melhorias](#sugerindo-melhorias)

## Código de Conduta

Este projeto segue um Código de Conduta. Ao participar, espera-se que você mantenha este código. Por favor, reporte comportamento inaceitável para devteam@autobiz.com.

## Como Contribuir

1. Fork o repositório
2. Clone seu fork: `git clone https://github.com/seu-usuario/autobiz.git`
3. Crie uma branch para sua feature: `git checkout -b feature/nome-da-feature`
4. Faça suas alterações
5. Commit suas mudanças: `git commit -m 'Adiciona nova feature'`
6. Push para a branch: `git push origin feature/nome-da-feature`
7. Abra um Pull Request

## Ambiente de Desenvolvimento

### Pré-requisitos

- Python 3.8+
- Node.js 14+
- Docker e Docker Compose
- Make

### Configuração

1. Instale as dependências:
```bash
make install
```

2. Configure as variáveis de ambiente:
```bash
cp backend/.env.example backend/.env
# Edite o arquivo .env com suas configurações
```

3. Inicialize o banco de dados:
```bash
make init-db
```

4. Inicie o projeto:
```bash
make run-backend  # Em um terminal
make run-frontend # Em outro terminal
```

## Padrões de Código

### Python

- Siga o PEP 8
- Use Type Hints
- Docstrings em todas as funções e classes
- Testes unitários para novas funcionalidades
- Mantenha a cobertura de testes acima de 80%

### JavaScript

- Use ES6+
- Siga o Airbnb JavaScript Style Guide
- Prefira funções assíncronas/await sobre .then()
- Documente funções complexas

### HTML/CSS

- Use HTML5 semântico
- Siga as convenções do Tailwind CSS
- Mantenha a responsividade
- Teste em diferentes navegadores

## Processo de Commit

### Mensagens de Commit

Use mensagens de commit claras e descritivas:

```
tipo(escopo): descrição curta

Descrição mais detalhada se necessário
```

Tipos:
- feat: Nova feature
- fix: Correção de bug
- docs: Documentação
- style: Formatação
- refactor: Refatoração
- test: Testes
- chore: Tarefas de manutenção

### Branches

- `main`: Produção
- `develop`: Desenvolvimento
- `feature/*`: Novas features
- `fix/*`: Correções
- `docs/*`: Documentação

## Pull Requests

1. Atualize sua branch com a última versão da develop
2. Resolva conflitos se necessário
3. Certifique-se que os testes passam
4. Atualize a documentação se necessário
5. Descreva suas mudanças no PR
6. Link issues relacionadas
7. Aguarde review

### Template de PR

```markdown
## Descrição
Descreva suas alterações

## Tipo de mudança
- [ ] Bug fix
- [ ] Nova feature
- [ ] Breaking change
- [ ] Documentação

## Checklist
- [ ] Testes adicionados/atualizados
- [ ] Documentação atualizada
- [ ] Código segue os padrões
```

## Reportando Bugs

Use o template de issue para bugs:

```markdown
### Descrição
Descreva o bug

### Passos para Reproduzir
1. Passo 1
2. Passo 2
3. ...

### Comportamento Esperado
O que deveria acontecer

### Comportamento Atual
O que está acontecendo

### Ambiente
- OS:
- Navegador:
- Versão:
```

## Sugerindo Melhorias

Use o template de issue para features:

```markdown
### Descrição
Descreva a feature

### Motivação
Por que esta feature é necessária

### Proposta
Como implementar

### Alternativas Consideradas
Outras abordagens consideradas
```

## Dúvidas

Para dúvidas que não são bugs, use:
- [Discussions](https://github.com/autobiz/discussions)
- [Stack Overflow](https://stackoverflow.com/questions/tagged/autobiz)
- Email: devteam@autobiz.com

## Agradecimentos

Agradecemos a todos os contribuidores que ajudam a melhorar este projeto!