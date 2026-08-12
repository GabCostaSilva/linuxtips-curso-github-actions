# Curso de GitHub Actions - LinuxTips

Um repositório de curso completo para aprender **GitHub Actions**, a plataforma de automação CI/CD que ajuda você a automatizar seu fluxo de trabalho de software diretamente no seu repositório GitHub.

## 📚 Sobre Este Curso

Este repositório contém exemplos práticos, exercícios e documentação para dominar o GitHub Actions. Seja você um iniciante ou alguém procurando aprofundar seus conhecimentos de automação, este curso cobre tudo, desde a configuração básica de workflows até padrões avançados de CI/CD.

## 🎯 Objetivos do Curso

Ao completar este curso, você aprenderá a:

- ✅ Entender os fundamentos e conceitos principais do GitHub Actions
- ✅ Criar e configurar workflows do GitHub (sintaxe YAML)
- ✅ Construir pipelines de CI/CD automatizados
- ✅ Disparar workflows em vários eventos do GitHub
- ✅ Usar runners hospedados no GitHub e auto-hospedados
- ✅ Implementar automação de testes, linting e deployment
- ✅ Gerenciar segredos e variáveis de ambiente com segurança
- ✅ Criar e usar ações personalizadas
- ✅ Monitorar e depurar execuções de workflow
- ✅ Implementar melhores práticas para workflows em produção

## 📋 Conteúdo do Curso

### Módulo 1: Fundamentos
- Introdução ao GitHub Actions
- Sintaxe e estrutura de workflows
- Eventos que disparam workflows

### Módulo 2: Workflows e Jobs
- Configuração de workflows
- Dependências entre jobs e orquestração
- Usando a diretiva `runs-on`

### Módulo 3: Steps e Actions
- Execução de steps e condicionais
- Usando ações oficiais e da comunidade
- Variáveis de ambiente e segredos

### Módulo 4: Pipelines de CI/CD
- Automação de testes
- Verificações de qualidade de código e linting
- Compilação e envio de imagens Docker
- Estratégias de deployment

### Módulo 5: Tópicos Avançados
- Compilações em matriz e paralelização
- Criando ações personalizadas
- Depurando workflows
- Otimização de performance

### Módulo 6: Melhores Práticas
- Gerenciamento de segredos e segurança
- Documentação de workflows
- Tratamento de erros e notificações
- Monitoramento e logging

## 🚀 Começando

### Pré-requisitos

- Uma conta no GitHub
- Conhecimento básico de Git e linha de comando
- Entendimento da sintaxe YAML
- Familiaridade com conceitos de CI/CD (útil, mas não obrigatório)

### Setup

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/GabCostaSilva/linuxtips-curso-github-actions.git
   cd linuxtips-curso-github-actions
   ```

2. **Explore os exemplos:**
   Cada pasta de módulo contém exemplos de workflow funcionais que você pode estudar e adaptar.

3. **Crie seus próprios workflows:**
   Faça um fork deste repositório ou crie seu próprio repositório para praticar a criação de workflows.

## 📁 Estrutura do Repositório

```
linuxtips-curso-github-actions/
├── README.md
├── .github/
│   └── workflows/
│       ├── 01-hello-world.yml
│       ├── 02-on-push-pull-request.yml
│       ├── 03-matrix-build.yml
│       ├── 04-secrets-and-env.yml
│       ├── 05-docker-build.yml
│       ├── 06-deploy.yml
│       └── ...
├── scripts/
│   └── (Scripts utilitários usados nos workflows)
├── tests/
│   └── (Arquivos de teste e workflows de teste)
└── docs/
    └── (Documentação adicional e folhas de cola)
```

## 💡 Conceitos-chave

### Workflow
Um processo automatizado configurável feito de um ou mais jobs. Definido por um arquivo YAML em `.github/workflows/`.

### Job
Um conjunto de steps que executam no mesmo runner. Jobs podem ser executados sequencialmente ou em paralelo.

### Step
Uma tarefa individual que pode executar comandos ou chamar uma ação.

### Action
Uma unidade de código reutilizável. Construa a sua própria ou use ações compartilhadas pela comunidade do GitHub.

### Runner
Um servidor que tem a aplicação GitHub Actions runner instalada e pronta para executar jobs.

### Event
Uma atividade específica que dispara um workflow (por exemplo, push, pull request, agendamento).

## 🔐 Segurança

Ao trabalhar com GitHub Actions:

- ✅ Use GitHub Secrets para dados sensíveis (chaves de API, tokens, senhas)
- ✅ Nunca faça commit de segredos no repositório
- ✅ Use tokens OIDC para autenticação quando possível
- ✅ Faça auditoria regular e rotação de tokens de acesso
- ✅ Restrinja permissões de workflow ao mínimo necessário
- ✅ Revise cuidadosamente dependências e ações de terceiros

### Exemplo: Usando Secrets

```yaml
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Deploy
        env:
          API_KEY: ${{ secrets.API_KEY }}
          DEPLOY_URL: ${{ secrets.DEPLOY_URL }}
        run: ./deploy.sh
```

## 📖 Recursos Úteis

- [Documentação do GitHub Actions](https://docs.github.com/pt/actions)
- [Marketplace de GitHub Actions](https://github.com/marketplace?type=actions)
- [Sintaxe de Workflow do GitHub Actions](https://docs.github.com/pt/actions/using-workflows/workflow-syntax-for-github-actions)
- [Melhores Práticas de GitHub Actions](https://docs.github.com/pt/actions/learn-github-actions/workflow-comments)

## 🤝 Contribuindo

Contribuições são bem-vindas! Se você tiver:

- Exemplos de workflows para compartilhar
- Correções de bugs ou melhorias
- Aprimoramentos de documentação
- Ideias para novos módulos

Por favor, sinta-se à vontade para enviar um pull request. Certifique-se de que suas contribuições:

- Seguem a estrutura e convenções de nomenclatura existentes
- Incluem comentários claros explicando o workflow
- Incluem uma breve descrição do que o workflow faz
- São testadas para garantir que funcionem corretamente

## 📝 Exemplos e Exercícios

Cada módulo inclui:

- **Exemplos documentados**: Exemplos de workflow do mundo real com comentários inline
- **Exercícios**: Tarefas práticas para treinar suas habilidades
- **Soluções**: Soluções de referência para comparação

## 🐛 Resolução de Problemas

### Problemas Comuns

**Workflow não está sendo disparado?**
- Verifique se os eventos de disparo estão configurados corretamente
- Verifique se o arquivo de workflow está em `.github/workflows/`
- Garanta que a sintaxe YAML é válida

**Ação não encontrada?**
- Verifique se a versão da ação existe (por exemplo, `actions/checkout@v3`)
- Procure por erros de digitação no nome da ação

**Secrets não estão funcionando?**
- Garanta que os secrets estejam devidamente definidos nas configurações do repositório
- Use a sintaxe correta: `${{ secrets.SECRET_NAME }}`
- Secrets não podem ser acessados fora de workflows

**Problemas de permissão?**
- Verifique as permissões de workflow no diretório `.github/workflows/`
- Verifique se o runner tem acesso necessário aos recursos

## 📧 Suporte e Dúvidas

Para dúvidas ou problemas:

1. Verifique a [Documentação do GitHub Actions](https://docs.github.com/pt/actions)
2. Procure por issues existentes neste repositório
3. Abra uma nova issue com uma descrição clara e arquivos de workflow relevantes

## 📄 Licença

Este material do curso está disponível para uso educacional e prático. Sinta-se à vontade para adaptar e usar estes exemplos em seus projetos.

---

**Boa Automação! 🚀**

Construído com ❤️ para a Comunidade Linux Tips
