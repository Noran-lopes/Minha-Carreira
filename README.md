# Minha Carreira

> Uma solução **N7sistem**, desenvolvida por **Noran**.

O **Minha Carreira** é uma página web criada para ajudar pessoas a organizar candidaturas a vagas de emprego em um único lugar. A ferramenta atende processos de **CLT, estágio, trainee, jovem aprendiz, trabalho temporário, freelance, PJ e outros formatos de contratação**.

A proposta é simples: substituir anotações espalhadas, links perdidos e controles manuais por um painel visual no qual cada pessoa consegue acompanhar empresas, vagas, prazos, etapas e próximas ações.

---

## Principais funcionalidades

### Gestão de candidaturas

- Cadastro de empresa, vaga ou programa, tipo de contratação e plataforma;
- Registro da data de inscrição e do próximo prazo;
- Controle da etapa atual e da próxima ação;
- Inclusão do link direto da candidatura;
- Edição e exclusão dos registros;
- Pesquisa por empresa, vaga ou programa;
- Filtros por etapa, tipo de vaga e plataforma.

### Painel de acompanhamento

A página inicial apresenta indicadores como:

- Total de candidaturas;
- Processos em andamento;
- Entrevistas;
- Aprovações;
- Prazos nos próximos sete dias;
- Distribuição das candidaturas por etapa.

### Funil seletivo interativo

As candidaturas são organizadas nas seguintes etapas:

1. Inscrito;
2. Teste online;
3. Dinâmica;
4. Entrevista com RH;
5. Entrevista com gestor;
6. Finalista;
7. Aprovado.

No computador, os cards podem ser arrastados entre as colunas. Em dispositivos móveis, a etapa pode ser alterada pelo formulário de edição.

### Portais de vagas

A plataforma oferece atalhos para portais conhecidos e permite que cada pessoa cadastre os próprios portais.

Para adicionar um novo portal, basta informar:

- Nome do portal;
- URL de acesso.

Os portais personalizados podem ser editados ou excluídos e ficam salvos no navegador.

### Importação e exportação

A aplicação permite:

- Importar arquivos `.xlsx`, `.xls` e `.csv`;
- Exportar as candidaturas para Excel;
- Exportar as candidaturas para CSV;
- Baixar uma planilha-modelo;
- Utilizar o arquivo exportado como backup ou para transferir os dados para outro navegador.

Os exemplos fictícios da página não são incluídos na exportação.

### Informações públicas sobre empresas

No cadastro de uma candidatura, o usuário pode acionar uma busca opcional para tentar localizar informações públicas sobre a empresa, como:

- Ramo de atuação;
- Número aproximado de funcionários;
- País ou sede;
- Presença nacional ou global;
- Fonte consultada.

Os resultados devem ser revisados antes do salvamento, pois bases públicas podem apresentar informações incompletas ou desatualizadas.

---

## Primeiro acesso

Na primeira visita, a pessoa pode:

- Conhecer a plataforma com exemplos fictícios;
- Importar uma planilha já preenchida;
- Baixar a planilha-modelo.

Um roteiro rápido apresenta as principais áreas da ferramenta.

Ao cadastrar a primeira candidatura própria, a aplicação pergunta se os exemplos fictícios devem ser removidos. Caso a pessoa escolha removê-los, apenas a nova base pessoal continuará disponível e as indicações de base demonstrativa desaparecerão.

---

## Como os dados são armazenados

O **Minha Carreira** não utiliza conta, login ou banco de dados.

As candidaturas e os portais personalizados são armazenados no `localStorage` do navegador. Isso significa que:

- Cada navegador mantém uma base própria;
- Os dados não são sincronizados automaticamente entre dispositivos;
- Limpar os dados do navegador pode apagar as informações;
- A navegação anônima pode não preservar os registros após o fechamento;
- A exportação periódica é recomendada como forma de backup.

A planilha importada é processada no próprio navegador. A pesquisa de empresas acessa uma fonte pública somente quando o usuário aciona o botão de busca.

---

## Estrutura esperada da planilha

A planilha deve conter as seguintes colunas:

```text
Empresa
Vaga / Programa
Tipo de Vaga
Plataforma
Data Inscrição
Status
Próxima Etapa
Data Limite
Link
Ramo de Atuação
Funcionários
Presença
País / Sede
Fonte Empresa
```

As colunas **Empresa** e **Vaga / Programa** são essenciais para que uma linha seja importada.

Para datas preenchidas manualmente, recomenda-se o formato:

```text
DD/MM/AAAA
```

---

## Como foi desenvolvido

O projeto foi desenvolvido como uma aplicação web estática, utilizando:

- **HTML5** para a estrutura da página;
- **CSS3** para a identidade visual, responsividade e acessibilidade;
- **JavaScript puro** para a lógica da aplicação;
- **LocalStorage** para persistência dos dados no navegador;
- **HTML Drag and Drop API** para movimentação dos cards no funil;
- **SheetJS** para leitura e geração de arquivos Excel e CSV;
- **Wikidata API** para a busca opcional de informações públicas sobre empresas;
- **GitHub Pages** como opção de publicação da página.

A aplicação não depende de framework, servidor, API própria ou banco de dados. Toda a interface e a lógica principal estão concentradas no arquivo `index.html`.

Essa abordagem foi escolhida para manter o projeto:

- Simples de publicar;
- Fácil de compartilhar;
- Responsivo;
- De baixo custo;
- Independente de instalação;
- Adequado para uso individual.

---

## Estrutura do repositório

```text
.
├── index.html
├── 404.html
└── README.md
```

### `index.html`

Arquivo principal da aplicação. Contém a estrutura, os estilos e a lógica de funcionamento.

### `404.html`

Página alternativa utilizada pelo GitHub Pages quando uma rota não é encontrada.

### `README.md`

Documentação, instruções de uso, detalhes técnicos e orientações de publicação.

---

## Como executar localmente

Para uma visualização rápida, abra o arquivo `index.html` em um navegador moderno.

Para reproduzir de forma mais próxima ao GitHub Pages, execute um servidor local na pasta do projeto. Exemplo com Python:

```bash
python3 -m http.server 8000
```

Depois, acesse:

```text
http://localhost:8000
```

---

## Como publicar no GitHub Pages

1. Crie um repositório no GitHub;
2. Envie `index.html`, `404.html` e `README.md` para a raiz do repositório;
3. Abra **Settings**;
4. Acesse **Pages**;
5. Em **Build and deployment**, selecione **Deploy from a branch**;
6. Escolha a branch principal;
7. Selecione a pasta `/root`;
8. Salve e aguarde a geração do endereço público.

Após a publicação, o projeto poderá ser acessado por um endereço semelhante a:

```text
https://seuusuario.github.io/nome-do-repositorio/
```

---

## Limitações atuais

- Não existe sincronização automática entre dispositivos;
- Não existe recuperação de dados apagados do navegador;
- A busca de empresas depende de conexão com a internet e da disponibilidade da fonte pública;
- A leitura e a geração de Excel dependem do carregamento do componente externo utilizado pela página;
- Os portais personalizados ficam disponíveis somente no navegador em que foram cadastrados;
- A aplicação foi projetada para uso individual e não possui colaboração entre usuários.

---

## Próximas evoluções possíveis

- Autenticação de usuários;
- Sincronização em nuvem;
- Lembretes por e-mail ou calendário;
- Cadastro de contatos e recrutadores;
- Histórico de movimentações;
- Campos personalizados;
- Estatísticas de conversão por etapa;
- Exportação dos portais personalizados;
- Integração com calendário;
- Versão com banco de dados para acesso em vários dispositivos.

---

## Privacidade

A aplicação não envia as candidaturas para um servidor próprio. Os dados permanecem no navegador até que sejam apagados pelo usuário ou pelo próprio navegador.

Antes de utilizar a ferramenta para armazenar informações sensíveis, recomenda-se revisar o funcionamento do `localStorage`, manter backups atualizados e evitar o uso em dispositivos públicos ou compartilhados.

---

## Autoria

**N7sistem**  
Desenvolvido por **Noran**

---

## Licença

Antes da publicação pública ou distribuição do código, defina uma licença para o projeto. Caso o objetivo seja permitir uso, cópia e adaptação com atribuição, uma opção comum é a licença MIT.
