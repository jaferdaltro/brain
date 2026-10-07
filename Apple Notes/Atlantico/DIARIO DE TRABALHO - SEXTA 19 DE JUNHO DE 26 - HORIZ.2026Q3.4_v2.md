---
apple-notes-id: B47A836D-738B-4183-98D2-891B317285CC
---
#report #hp #atlantico #2026Q3 

## Luis Marquitti
==🔵A única maneira para o fix é usar o cache? Pq o cache é todo feito pela propria API, a MFE em si não deveria e nem precisa de nada referente ao cache.==
Bom dia Luis,
Por aqui tudo joia!
O trackedImageLoadKeys não é cache de imagem, é apenas para garantir que o evento do analytics seja disparado somente uma vez, mesmo que o código que o dispara seja executado múltiplas vezes. Fazendo uma análise desse hook.

trackImageLoadEvent -> evento do Analytics (que será o log)