---
title: "git rebase -i; Porque o histórico de commits importa"
author: Caio Pavanelli
date: 2020-09-02
draft: true
hideToc: false
enableToc: true
enableTocContent: false
tags: 
- hard skills
- git
- pr
- rebase
---

Quando se aprende um pouco de `git`, normalmente é ensinado que sejam efetuados commits frequentes para preservar a granularidade de alterações e evitar perda de desenvolvimento. Porém, o que muitas vezes se perde nesse conceito, é que cada commit deve na verdade ser **âtomico**, ou seja, conter uma alteração isolada e independente. Uma ferramenta que pode ajudar a manter a frequência de commits e manter a atomicidade desejada é o **rebase interativo**.

## Processo de peer review

Num processo de desenvolvimento utilizando **gitflow** com **peer review**, o desenvolvedor trabalha tipicamente em uma feature branch de forma isolada. Uma vez que o trabalho foi testado e está pronto para ser integrado em **develop**, um **pull request** é aberto para que seja validado por outro membro da equipe. As alterações são validadas e então é realizado o **merge** das branches.

Ao realizar uma revisão de PR, um ponto que também deve ser observado é o histórico de commits do PR. Além obviamente de validar se as alterações efetuadas são condizentes com a feature desenvolvida, o histórico de commits pode, e deve, ser motivo de pedir revisão. Se o histórico não possuir mensagens claras e sucintas do que cada commit representa, não há razão para que ele seja aceito. Uma hipótese que deixa isso mais evidente é quando o histórico de commits da feature branch possui correções.

### Exemplo 1

Observe o histórico de commits abaixo de uma feature branch hipotética em review.

```bash
7777777 feat: modificacao seis
6666666 fix: corrige modificacao tres
5555555 feat: modificacao cinco
4444444 feat: modificacao quatro
3333333 feat: modificacao tres
2222222 feat: modificacao dois
1111111 feat: modificacao um
```

Note que o commit `6666666` corrige uma modificação efetuada no commit `3333333`. Note também que para identificar isso foi necessário confiar na mensagem descritiva dos commits efetuados, o que nem sempre pode ser realizado. Considerando também que o resultado final atende as expectativas de desenvolvimento tanto em funcionalidade quanto em qualidade de código, existem 2 possibilidades deste PR ser aceito. A primeira é pedir revisão para que seja feito o `squash` de todas as modificações em um único commit, e adicionando uma mensagem de commit mais detalhada. A segunda é pedir revisão para que o commit `6666666` seja agregado ao commit `3333333` através do `rebase`, e só então mergear na branch principal.

```bash
$ git rebase -i 3333333^
```

## Git rebase interativo

O git rebase interativo é uma ferramente bastante poderosa e que deve ser usada com bastante atenção. Ela permite reescrever o histórico de commits, podendo adicionar, editar, excluir e mesclar qualquer commit efetuado. Um bom material de apoio para se aprofundar mais nesse comando pode ser encontrado no capítulo 7.6 do livro [Pro Git](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History).