# Consensus Commit 👨🏻‍💻
Uma especificação para dar um significado legível às mensagens de commit

## Resumo

A especificação do Consensus Commit é uma convenção simples para utilizar nas mensagens de commit. Ela define um conjunto de regras para criar um histórico de commit explícito.

A mensagem do commit deve ser estruturada da seguinte forma:

```shell script
<tipo>[escopo opcional]: <descrição>

[corpo opcional]

[rodapé opcional]
```

O commit contém os seguintes elementos estruturais, para comunicar a intenção ao utilizador da sua biblioteca:

* fix: um commit do tipo fix soluciona um problema na sua base de código (isso se correlaciona com PATCH do versionamento semântico).
* feat: um commit do tipo feat inclui um novo recurso na sua base de código (isso se correlaciona com MINOR do versionamento semântico).
* BREAKING CHANGE: um commit que contém o texto BREAKING CHANGE:, no começo do texto do corpo opcional ou do rodapé opcional, inclui uma modificação que quebra a compatibilidade da API (isso se correlaciona com MAJOR do versionamento semântico). Uma BREAKING CHANGE pode fazer parte de commits de qualquer tipo.
* Outros: tipos adicionais são permitidos além de fix: e feat:, por exemplo @commitlint/config-conventional (baseado na Convenção do Angular) recomenda-se chore:, docs:, style:, refactor:, perf:, test:, entre outros.

Também recomendamos improvement para commits que melhoram uma implementação atual sem adicionar um novo recurso ou consertar um bug. Observe que esses tipos não são obrigatórios pela especificação do Conventional Commits e não têm efeito implícito no versionamento semântico (a menos que incluam uma BREAKING CHANGE). Um escopo pode ser adicionado ao tipo do commit, para fornecer informações contextuais adicionais e está contido entre parênteses, por exemplo:
```shell script
feat(parser): adiciona capacidade de interpretar arrays.
```

### Exemplos

#### Mensagem de commit com descrição e modificação que quebra a compatibilidade no corpo
```shell script
feat: permitir que o objeto de configuração fornecido estenda outras configurações

BREAKING CHANGE: a chave `extends`, no arquivo de configuração, agora é utilizada
para estender outro arquivo de configuração
```

#### Mensagem de commit com ! opcional para chamar a atenção para quebra a compatibilidade
```shell script
chore!: remove Node 6 da matriz de testes

BREAKING CHANGE: removendo Node 6 que atinge o final de vida em Abril
```

#### Mensagem de commit sem corpo
```shell script
docs: ortografia correta de CHANGELOG
```

#### Mensagem de commit com escopo
```shell script
feat(lang): adiciona tradução para português brasileiro
```
#### Mensagem de commit de uma correção utilizando número de ticket (opcional)
```shell script
fix: corrige pequenos erros de digitação no código

veja o ticket para detalhes sobre os erros de digitação corrigidos

closes issue #12
```
## Git Emoji's

|   Commit type              | Emoji                                         |
|:---------------------------|:----------------------------------------------|
| Initial commit             | :tada: `:tada:`                               |
| Version tag                | :bookmark: `:bookmark:`                       |
| New feature                | :sparkles: `:sparkles:`                       |
| Bugfix                     | :bug: `:bug:`                                 |
| Metadata                   | :card_index: `:card_index:`                   |
| Documentation              | :books: `:books:`                             |
| Documenting source code    | :bulb: `:bulb:`                               |
| Performance                | :racehorse: `:racehorse:`                     |
| Cosmetic                   | :lipstick: `:lipstick:`                       |
| Tests                      | :rotating_light: `:rotating_light:`           |
| Adding a test              | :white_check_mark: `:white_check_mark:`       |
| Make a test pass           |  ✓ `:heavy_check_mark:`       |
| General update             | :zap: `:zap:`                                 |
| Improve format/structure   | :art: `:art:`                                 |
| Refactor code              | :hammer: `:hammer:`                           |
| Removing code/files        | :fire: `:fire:`                               |
| Continuous Integration     | :green_heart: `:green_heart:`                 |
| Security                   | :lock: `:lock:`                               |
| Upgrading dependencies     | :arrow_up: `:arrow_up:`                       |
| Downgrading dependencies   | :arrow_down: `:arrow_down:`                   |
| Lint                       | :shirt: `:shirt:`                             |
| Translation                | :alien: `:alien:`                             |
| Text                       | :pencil: `:pencil:`                           |
| Critical hotfix            | :ambulance: `:ambulance:`                     |
| Deploying stuff            | :rocket: `:rocket:`                           |
| Fixing on MacOS            | :apple: `:apple:`                             |
| Fixing on Linux            | :penguin: `:penguin:`                         |
| Fixing on Windows          | :checkered_flag: `:checkered_flag:`           |
| Work in progress           | :construction:  `:construction:`              |
| Adding CI build system     | :construction_worker: `:construction_worker:` |
| Analytics or tracking code | :chart_with_upwards_trend: `:chart_with_upwards_trend:` |
| Removing a dependency      | :heavy_minus_sign: `:heavy_minus_sign:`       |
| Adding a dependency        | :heavy_plus_sign: `:heavy_plus_sign:`         |
| Docker                     | :whale: `:whale:`                             |
| Configuration files        | :wrench: `:wrench:`                           |
| Package.json in JS         | :package: `:package:`                         |
| Merging branches           | :twisted_rightwards_arrows: `:twisted_rightwards_arrows:` |
| Bad code / need improv.    | :hankey: `:hankey:`                           |
| Reverting changes          | :rewind: `:rewind:`                           |
| Breaking changes           | :boom: `:boom:`                               |
| Code review changes        | :ok_hand: `:ok_hand:`                         |
| Accessibility              | :wheelchair: `:wheelchair:`                   |
| Move/rename repository     | :truck: `:truck:`                             |
| Other                      | [Be creative](http://www.emoji-cheat-sheet.com/)  |

Todos os diretos reservados a https://www.conventionalcommits.org/pt-br/v1.0.0-beta.4/#resumo
