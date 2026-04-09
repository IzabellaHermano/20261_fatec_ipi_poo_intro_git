<h1>Mastering Version Control: An Introduction to Git</h1>

<h2>Comandos de Configuração e Inicialização</h2>
<ul>
  <li>git init: Cria um novo repositório Git (a pasta oculta .git) no diretório atual.</li>
  <li>git config --local user.name "Nome": Define o nome do responsável pelas operações no repositório local.</li>
  <li>git config --local user.email "email@exemplo.com": Define o e-mail do responsável no repositório local.</li>
  <li>git config --global core.editor "code --wait": Configura o VS Code como editor padrão para mensagens de commit, esperando o fechamento do arquivo para confirmar a operação.</li>
  <li>git config --global init.defaultBranch main: Define "main" como o nome padrão para a branch inicial em novos repositórios.</li>
  <li>git config --list: Exibe todas as configurações realizadas.</li>
  <li>git config --list --show-origins: Mostra as configurações e a origem de onde cada uma foi definida.</li>
</ul>

<h2>Comandos de Fluxo de Trabalho Local (Estados dos Arquivos)</h2>
<p>O Git gerencia arquivos através de estados específicos:</p>
<ol>
  <li>Untracked: Arquivo no diretório, mas não controlado pelo Git.</li>
  <li>Tracked (Unmodified): Arquivo controlado e igual à última versão salva.</li>
  <li>Tracked (Modified): Arquivo controlado, mas com edições em relação ao último commit.</li>
  <li>Tracked (Staged): Arquivo pronto para ser incluído no próximo commit.</li>
</ol>

<ul>
  <li>git status: Exibe o estado atual dos arquivos no diretório de trabalho.</li>
  <li>git status -s: Exibe o estado de forma enxuta/curta.</li>
  <li>git add &lt;arquivo&gt;: Transporta o arquivo para o estado Staged.</li>
  <li>git commit: Torna as alterações no estado Staged permanentes, abrindo o editor para a mensagem.</li>
  <li>git commit -m "mensagem": Realiza o commit diretamente com a mensagem informada.</li>
  <li>git commit -a: Atalho que adiciona arquivos modificados ao commit sem precisar usar o git add explicitamente.</li>
  <li>git diff: Mostra o conteúdo modificado no arquivo que ainda não foi para o estado Staged.</li>
  <li>git rm: Comando ilustrado no diagrama para mover um arquivo do estado rastreado (Tracked) para não rastreado (Untracked).</li>
</ul>

<h2>Comandos de Histórico e Visualização</h2>
<ul>
  <li>git log: Lista os commits realizados.</li>
  <li>git log -p: Mostra o histórico de commits incluindo o código contido (patch).</li>
  <li>git log --pretty=oneline: Exibe o histórico de forma simplificada.</li>
</ul>

<h2>Gerenciamento de Versões (Tags e Semântica)</h2>
<p>Tags marca versões "entregáveis" seguindo o padrão de Major, Minor e Patch (ex: v1.0.0).</p>
<ul>
  <li>git tag -a &lt;nome_tag&gt; -m "mensagem": Cria uma tag anotada.</li>
  <li>git tag --list ou git tag: Lista as tags criadas.</li>
  <li>git show &lt;nome_tag&gt;: Exibe os detalhes de uma tag específica.</li>
</ul>

<h2>Gerenciamento de Branches e Ponteiros</h2>
<ul>
  <li>Ponteiro HEAD: Referência usada pelo Git para decidir qual versão está ativa.</li>
  <li>Branch: Ponteiro que referencia um commit específico.</li>
  <li>git branch: Exibe o nome da branch atual.</li>
</ul>

<h2>Comandos de Repositório Remoto (Remote)</h2>
<ul>
  <li>git remote add origin &lt;url&gt;</li>
  <li>git remote</li>
  <li>git remote -v</li>
  <li>git push &lt;remote&gt; &lt;branch&gt;</li>
  <li>git push &lt;remote&gt; &lt;tag&gt;</li>
  <li>git push &lt;remote&gt; --tags</li>
  <li>git remote remove origin</li>
</ul>

<h2>Recuperação de Versões Antigas</h2>
<ul>
  <li>Como funciona: Cada commit salva o estado atual e mantém histórico.</li>
  <li>Segurança: Permite recuperar versões anteriores sem perder trabalho.</li>
  <li>Visualização: Use git log -p para ver alterações detalhadas.</li>
</ul>

<h2>O Ponteiro HEAD e Branches</h2>
<ul>
  <li>Ponteiro HEAD: Define qual versão está ativa no diretório.</li>
  <li>Branches: Permitem múltiplos caminhos de desenvolvimento.</li>
</ul>

<h2>Convenção de Commits</h2>

<table border="1">
  <tr>
    <th>Tipo</th>
    <th>Nome</th>
    <th>Quando usar?</th>
  </tr>
  <tr>
    <td>feat</td>
    <td>Feature</td>
    <td>Introduz uma nova funcionalidade ao código.</td>
  </tr>
  <tr>
    <td>fix</td>
    <td>Bug Fix</td>
    <td>Corrige um erro/bug.</td>
  </tr>
  <tr>
    <td>docs</td>
    <td>Documentação</td>
    <td>Alterações apenas em documentação.</td>
  </tr>
  <tr>
    <td>style</td>
    <td>Estilo</td>
    <td>Alterações de formatação.</td>
  </tr>
  <tr>
    <td>refactor</td>
    <td>Refatoração</td>
    <td>Melhoria sem alterar funcionalidade.</td>
  </tr>
  <tr>
    <td>perf</td>
    <td>Performance</td>
    <td>Melhoria de desempenho.</td>
  </tr>
  <tr>
    <td>test</td>
    <td>Testes</td>
    <td>Adição/correção de testes.</td>
  </tr>
  <tr>
    <td>build</td>
    <td>Build</td>
    <td>Alterações em dependências.</td>
  </tr>
  <tr>
    <td>ci</td>
    <td>CI</td>
    <td>Configuração de integração contínua.</td>
  </tr>
  <tr>
    <td>chore</td>
    <td>Tarefas rotineiras</td>
    <td>Outras alterações gerais.</td>
  </tr>
  <tr>
    <td>revert</td>
    <td>Reversão</td>
    <td>Reverte commit anterior.</td>
  </tr>
</table>

<h3>Estrutura Padrão</h3>
<p>&lt;tipo&gt;[escopo opcional]: &lt;descrição&gt;</p>
<p>Exemplo: feat(calculadora): soma adicionada</p>

<h2>Tags (Marcos de Versão)</h2>
<ul>
  <li>git tag -a v1.0.0 -m "mensagem"</li>
</ul>

<h3>Tag Leve (Lightweight)</h3>
<ul>
  <li>git tag &lt;nome-da-tag&gt;</li>
  <li>Exemplo: git tag v1.1.0-beta</li>
</ul>

<h3>Tag Anotada (Annotated)</h3>
<ul>
  <li>git tag -a &lt;nome-da-tag&gt; -m "mensagem"</li>
  <li>Exemplo: git tag -a v2.0.0 -m "Release oficial"</li>
</ul>

<h2>Tabela Comparativa de Comandos</h2>

<table border="1">
  <tr>
    <th>Objetivo</th>
    <th>Comando</th>
  </tr>
  <tr>
    <td>Criar Leve</td>
    <td>git tag v1.0.0</td>
  </tr>
  <tr>
    <td>Criar Anotada</td>
    <td>git tag -a v1.0.0 -m "Mensagem"</td>
  </tr>
  <tr>
    <td>Listar Tags</td>
    <td>git tag</td>
  </tr>
  <tr>
    <td>Ver detalhes</td>
    <td>git show v1.0.0</td>
  </tr>
  <tr>
    <td>Deletar Tag</td>
    <td>git tag -d v1.0.0</td>
  </tr>
</table>
