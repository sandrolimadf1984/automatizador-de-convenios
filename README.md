<div align="center">

# 🤖 Automatizador de Convênios

**Automação de lançamento de códigos de procedimentos em portais de autorização de convênios**

![Versão](https://img.shields.io/badge/vers%C3%A3o-2.1.0-2d7dff)
![Status](https://img.shields.io/badge/status-online-2ecc71)
![Uso](https://img.shields.io/badge/uso-interno%20%C2%B7%20Sabin%20Bras%C3%ADlia-f5c518)

*Cole os códigos uma vez. O robô digita por você.*

</div>

---

## 📌 O que é

O **Automatizador de Convênios** é uma ferramenta que roda direto no navegador (sem instalar
nenhum programa) e automatiza o preenchimento de códigos de procedimentos nos portais de
autorização dos convênios de saúde.

O trabalho que antes era feito digitando código por código, campo por campo, passa a ser feito
assim: a pessoa **cola a lista inteira de códigos** numa caixinha, clica em
**🚀 INICIAR AUTOMAÇÃO**, e o robô digita tudo no portal — incluindo as quantidades quando um
código se repete na lista.

## ⚙️ Como funciona por dentro

A mágica está em um **bookmarklet**: um favorito do navegador que, em vez de abrir um site,
executa um pequeno código. Esse código busca o arquivo `automatizador.js` deste repositório e o
executa na página do portal que estiver aberta.

```
Clique no favorito 🤖 Automatizador
        │
        ▼
Busca o automatizador.js mais recente deste repositório
        │
        ▼
Abre o painel por cima do portal
        │
        ▼
Você escolhe o convênio → cola os códigos → o robô trabalha
```

A consequência mais importante desse desenho: **toda atualização feita no `automatizador.js`
chega automaticamente para todos os usuários** no próximo clique do favorito. Ninguém precisa
reinstalar, baixar ou atualizar nada.

### Os cinco caminhos do carregador

Alguns portais têm regras de segurança que proíbem a página de buscar arquivos de fora. Para
esses casos, o favorito tenta cinco caminhos, em ordem, e para no primeiro que funcionar:

1. Busca direta no GitHub — é o caminho de sempre, usado na grande maioria dos portais
2. A mesma busca pela forma antiga (XHR)
3. Carregar como script pelo GitHub Pages, levando a chave de segurança da própria página
4. O mesmo, por um espelho
5. Janela auxiliar: uma janelinha abre no GitHub, pega o arquivo e devolve o texto por recado
   entre janelas — caminho que nenhuma regra de segurança de página consegue barrar

Se nenhum funcionar, ele abre um aviso dizendo exatamente qual caminho falhou e por quê.

## 🏥 Convênios suportados

| Convênio | Automação para |
|---|---|
| 🛠️ Affego | Fisco e Convênios Affego |
| 🩺 Amil | Rede Credenciada Amil |
| 💳 Assedf/Vida Card | Convênios ASSEDF / Vida Card |
| 🏛️ Assefaz | Convênios Assefaz |
| 🏦 BRB Saúde | Convênios BRB Saúde |
| 🏛️ Câmara dos Deputados | Câmara dos Deputados |
| 👨‍👩‍👦 Camed Saúde | Convênios Camed Saúde |
| 🧬 CNU Unimed | Autorizações CNU Unimed |
| 🌸 Evo Saúde | Convênios Evo Saúde |
| 🔷 Fascal | Convênios Fascal |
| 🔴 GEAP | Convênios GEAP Saúde |
| 🤝 Inas GDF | Convênios Inas GDF |
| 🏥 Medsenior | Convênio Medsenior |
| 🚔 PF Saúde | Convênios PF Saúde |
| 📝 Planassiste MPU | Planilhas do MPU |
| ⚖️ Plenum | Convênios de Advocacia e Justiça |
| 🛡️ PM | Polícia Militar |
| ✉️ Postal (Correios) | Logística Postal |
| 🧪 Proasa | Autorizações Proasa |
| 🩹 SAMP AGMP | Convênio SAMP AGMP |
| 💻 Serpro | Convênios Serpro |
| 🏛️ STJ | Superior Tribunal de Justiça |
| ⚖️ STM | Convênio STM (Plas/JMU) |
| 🌎 Sul America | Convênios SulAmérica |
| 🏛️ TJDF | Tribunal de Justiça do DF |
| 🗳️ TRE | Tribunal Regional Eleitoral |
| 📖 TRF | Tribunal Regional Federal |
| 🤝 TRT | Tribunal Regional do Trabalho |
| 🔨 TST | Tribunal Superior do Trabalho |
| 💚 Unimed Seguros | Convênio Unimed Seguros |
| 🩶 Unity Saúde | Convênios Unity Saúde |

Cada robô conhece a estrutura do seu portal: sabe em qual campo digitar, quando aguardar o
sistema responder, como preencher a quantidade quando um código se repete, e como salvar cada
item antes de passar ao próximo.

## ✨ Funcionalidades

**Contagem automática de quantidades** — se o mesmo código aparece 3 vezes na lista colada, o
robô lança o código uma vez com quantidade 3.

**☑️ Marcador de checkboxes** — um clique marca todas as caixinhas de seleção da página do portal
de uma vez.

**Painel arrastável** — segure em qualquer área livre do painel e arraste para onde não atrapalhar.

**⚠️ Avisos dinâmicos** — o painel exibe mensagens publicadas no arquivo `aviso.txt` deste
repositório. É o canal de comunicação com a equipe.

**Atualização invisível** — melhorias, correções e novos convênios entram em produção com um
simples commit neste repositório.

## 🚀 Instalação (menos de 1 minuto)

### Opção A — Arrastando (mais fácil)

1. Acesse a página de instalação: **https://sandrolimadf1984.github.io/automatizador-de-convenios/**
2. Pressione `Ctrl + Shift + B` para exibir a barra de favoritos
3. Arraste o botão azul **🤖 Automatizador** para a barra de favoritos

Funciona igual no Chrome, no Edge e no Firefox. No Firefox aparece uma caixinha de confirmação já
preenchida: é só clicar em **Salvar**.

### Opção B — Colando o código

1. Pressione `Ctrl + Shift + B` para exibir a barra de favoritos
2. Crie um favorito novo e dê o nome `🤖 Automatizador`
3. No campo do endereço, cole o código que está na página de instalação, no passo 4
4. Salve

## 📖 Como usar no dia a dia

1. Abra o portal de autorização do convênio e faça login normalmente
2. Clique no favorito **🤖 Automatizador** na barra
3. Clique no card do convênio desejado
4. Cole a lista de códigos na área tracejada
5. Clique em **🚀 INICIAR AUTOMAÇÃO** e acompanhe o robô trabalhar

## 📁 Estrutura do repositório

| Arquivo | Função |
|---|---|
| `automatizador.js` | O coração do projeto: interface + todos os robôs de automação |
| `index.html` | Página de instalação (GitHub Pages) com o botão de arrastar |
| `carregar.html` | Janela auxiliar usada nos portais que bloqueiam busca de arquivos |
| `aviso.txt` | Mensagens exibidas no painel de todos os usuários |
| `README.md` | Este documento |

## 🔧 Manutenção (para o mantenedor)

**Atualizar um robô ou a interface** — edite o `automatizador.js` e faça commit. Todos recebem no
próximo clique. Nos portais que usam os caminhos alternativos, a mudança leva cerca de um minuto
a mais, porque o GitHub Pages precisa republicar.

**Publicar um aviso para a equipe** — escreva a mensagem no `aviso.txt` e faça commit. Para
remover o aviso, deixe o arquivo vazio.

**Adicionar um convênio novo** — inclua o robô no objeto `robos`, cadastre a ficha dele em
`infoRobos` (ícone, cor, descrição e modo de entrada), acrescente a logo em `LOGOS` e adicione o
card na lista `EXIBICAO`, mantendo a ordem alfabética.

**Ligar o GitHub Pages** — necessário para a página de instalação e para os caminhos alternativos
do carregador: Settings → Pages → Branch `main`, pasta `/ (root)` → Save.

## ⚠️ Uso e responsabilidade

Ferramenta desenvolvida para **uso interno** da equipe, com o objetivo de eliminar digitação
repetitiva no lançamento de autorizações. Ela não burla nenhuma etapa dos portais — apenas digita,
no lugar do usuário, os mesmos dados que ele digitaria manualmente, com sua própria sessão
autenticada. A conferência dos códigos e das autorizações geradas continua sendo responsabilidade
de quem opera.

## 👨‍💻 Créditos

**Sandro de Lima Pereira** — interface, novos recursos, distribuição e manutenção desta versão.

Projeto construído de forma colaborativa a partir da automação original criada por
**André Fernandes**.

---

<div align="center">

*Feito com dedicação para facilitar o trabalho de quem autoriza. 🩵*

</div>
