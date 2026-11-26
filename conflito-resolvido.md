# Conflito resolvido

## O que aconteceu
Duas branches alteraram a mesma linha do arquivo `README.md`, que é o título do guia:
- Na `main`, o título foi alterado para "Guia de Cibersegurança para Iniciantes".
- Na `feature/readme`, o título foi alterado para "Cibersegurança para iniciantes".

Ao tentar integrar a `feature/readme` na `main` com `git merge feature/readme`, o Git não conseguiu decidir qual versão manter e exibiu esta mensagem:

`CONFLICT (content): Merge conflict in README.md`

## Como identifiquei o conflito
- O `git status` mostrou `both modified: README.md`.
- O arquivo apresentou os marcadores `<<<<<<< HEAD`, `=======` e `>>>>>>> feature/readme`.

## Decisão
Mantive o conteúdo completo do README escrito na `feature/readme`, pois ele tinha todas as seções do guia. Para o título, usei "Cibersegurança para Iniciantes", que é direto e combina com o tema do projeto.

## Como resolvi
1. Abri o `README.md` e removi os três marcadores de conflito.
2. Deixei apenas a versão final do texto.
3. Conferi com `git diff --check` que não havia marcadores restantes.
4. Executei `git add README.md` para marcar o conflito como resolvido.
5. Executei `git commit` para concluir o merge.
6. Executei `git push` para enviar o resultado ao GitHub.

## Resultado
O merge foi concluído sem marcadores no arquivo e o README final contém todas as seções do guia.