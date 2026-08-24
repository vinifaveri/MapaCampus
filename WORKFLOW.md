Workflow

1 - Modelo

O projeto utiliza uma versão simplificada do GitHub Flow.

A branch `main` representa a versão estável do projeto. 

Alterações de conteúdo e manutenções são desenvolvidas em branches separadas.

Após a conclusão de uma alteração, a branch é revisada e integrada à `main`.

---------------------------------------------------

2 - Branches

`main`
Branch principal e estável do projeto.
Não devem ser desenvolvidas funcionalidades diretamente nela, exceto a
configuração inicial do repositório.

`feature/*`
Utilizada para novas funcionalidades.
Exemplo:
`feature/pagina-inicial`
Fluxo:
`main -> feature/* -> main`

`content/*`
Utilizada para alterações de conteúdo.
Exemplo:
`content/titulo-principal`
Fluxo:
`main -> content/* -> main`

`maintenance/*`
Utilizada para manutenção e ajustes no repositório.
Exemplo:
`maintenance/rastreabilidade`
Fluxo:
`main -> maintenance/* -> main`

---------------------------------------------------

3 - Atualização das branches

Antes de criar uma nova branch:
`bash`
git switch main
git pull origin main
Depois:
git switch -c nome-da-branch

Antes da integração, a branch deve estar atualizada em relação à
main.

---------------------------------------------------

4 - Política de commits

Os commits seguem o padrão:

tipo(escopo): descrição
Exemplo:
feat(html): cria estrutura inicial da página

As mensagens devem ser:curtas ,objetivas ,escritas no presente ,relacionadas a apenas uma mudança ,suficientemente claras para explicar a alteração realizada.

---------------------------------------------------

5 - Commits

Tipo / Utilização
feat / Nova funcionalidade
fix / Correção de problema
docs / Alteração de documentação
style / Alteração sem impacto funcional no código
refactor / Reorganização interna do código
chore / Manutenção geral do projeto
mapa / alterações diretamente relacionados ao mapa do campus
data / inclusão ou alteração dos dados dos pontos úteis
detalhes / usado para alterações de detalhes de um ponto.

---------------------------------------------------

6 - Revisão
As alterações devem ser feitas em branches específicas.

Depois que o desenvolvimento estiver concluído: 
a branch é enviada ao GitHub;
é criado um Pull Request;
as mudanças são revisadas;
possíveis conflitos são resolvidos;
a branch é integrada à main

Sempre que possível será utilizado merge commit, evitando squash, para preservar o histórico dos commits.

---------------------------------------------------

7 - Conflitos

Quando ocorrer um conflito:
identificar os arquivos conflitantes;
analisar as duas versões;
decidir qual conteúdo deve permanecer ou combinar as alterações;
remover os marcadores de conflito;
adicionar o arquivo corrigido;

criar um commit registrando a resolução.
Exemplo:
git add index.html
git commit -m "conflict(html): resolve divergência no título"

---------------------------------------------------

8 - Reversão de alterações
Quando uma alteração já estiver registrada no histórico e precisar serdesfeita, o projeto utiliza:
"git revert"
em vez de apagar o histórico.

Exemplo:
git revert --no -commit HEAD
git commit -m "fix(html): reverte alteração anterior"

Dessa maneira, o commit original continua registrado e um novo commitdocumenta sua reversão.

---------------------------------------------------

9 - Revisão antes do merge
Antes de integrar uma branch:
git diff main...nome-da-branch

Também pode ser utilizado:
git log --oneline --graph --decorate --all
Revisar tanto as alterações quanto o histórico antes da integração.