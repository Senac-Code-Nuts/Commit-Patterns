# Padrão de Mensagens de Commit

Este projeto adota o padrão **Conventional Commits**, que estrutura mensagens de commit para facilitar a automação de versionamento semântico e geração automática de changelogs.

# Regras do padrão de commits

1. Todas as mensagens de commit devem estar em português.
2. **SEGUIR** o formato do Conventional Commits
- Tipo (feat, fix, perf, etc.)
- Escopo opcional ((player), (ui), (build))
- Dois pontos : depois do escopo
- Mensagem curta e objetiva
- Linha em branco opcional e descrição detalhada se necessário

## Formato básico

| Tipo         | Descrição                                       | Exemplo                                        |
| ------------ | ----------------------------------------------- | ---------------------------------------------- |
| **feat**     | Nova funcionalidade / sistema / gameplay        | `feat(player): adiciona sistema de pulo`       |
| **fix**      | Correção de bug visual, físico, ou gameplay     | `fix(ui): corrige bug no HUD`                  |
| **perf**     | Melhoria de performance no build ou runtime     | `perf(build): otimiza tempo de compilação`     |
| **docs**     | Atualização de documentação, README, tutoriais  | `docs(readme): atualiza guia de setup`         |
| **style**    | Ajuste visual, layout, formatação de código     | `style(material): corrige shader`              |
| **refactor** | Refatoração de código sem mudar gameplay        | `refactor(ai): limpa scripts de comportamento` |
| **test**     | Novos testes ou ajustes em testes automatizados | `test(character): adiciona testes de salto`    |
| **chore**    | Atualização de dependências, configs, build     | `chore(deps): atualiza pacote Unity`           |
| **ci**       | Alterações em pipeline CI/CD ou build scripts   | `ci(github): melhora cache do pipeline`        |

## Escopo (opcional)

O escopo serve para indicar a área afetada pelo commit, como:

- auth
- ui
- api
- build

Exemplo:

```
feat(auth): adicionar suporte a dois fatores
```

## Breaking changes

Quando uma mudança incompatível com versões anteriores é feita, deve-se indicar um breaking change. Dificilmente isso vai rolar e se rolar vai ser comigo (Murillo). Isso pode ser feito de duas formas:

Colocando um ! após o tipo ou escopo:

```
feat(player)!: altera PlayerController para novo sistema de física
```

Ou usando um rodapé com o texto BREAKING CHANGE: seguido da descrição:

```
fix(build): ajustar pipeline para Unity 6000.4.0f1

BREAKING CHANGE: o projeto foi migrado para Unity 6000.4.0f1; builds antigas podem não funcionar, e alguns assets precisam ser reimportados.
```

## Exemplo completo
```
chore(unity): atualizar projeto para Unity 6000.4.0f1

O projeto foi migrado para a nova versão da Unity para aproveitar melhorias no HDRP e no pipeline de build.

BREAKING CHANGE: alguns assets e scripts podem precisar ser reimportados, e builds antigas podem não funcionar.
```

## Referências

O texto foi baseado em [Conventional Commits Org](https://www.conventionalcommits.org/en/v1.0.0/).
