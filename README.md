ettorecammarata.github.io/app-store

## Come funzionano i download

I repo delle app sono privati, quindi i loro link alle release danno 404 a chi non è loggato.
Ogni app ha qui una release fissa (tag = nome app in minuscolo, es. `shinitodo`) con il file a nome
stabile: `https://github.com/ettorecammarata/app-store/releases/download/<tag>/<file>`.

Per pubblicare una nuova versione, sostituisci il file nella release dello store:

```
gh release upload shinitodo ShiniTodo-0.0.18-release.apk#shinitodo.apk -R ettorecammarata/app-store --clobber
```

Il nome dopo `#` è solo l'etichetta: il file caricato deve già chiamarsi come nel link
(`shinitodo.apk`), quindi rinominalo prima di caricarlo.

## Icone

Ogni scheda mostra l'icona dell'app da `icons/` (`<img class="app-icon" src="icons/<tag>.svg">`).
Le icone vettoriali Android (vector drawable / adaptive icon) sono convertite in SVG: per le
adaptive icon il `viewBox` è `18 18 72 72`, cioè la parte visibile dei 108dp. Gli angoli
arrotondati li mette il CSS, quindi l'SVG resta quadrato e a tutto campo.
