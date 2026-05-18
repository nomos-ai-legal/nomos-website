Nomos AI — Brand & Style Guide
Brief à destination du développeur du site nomos-ai.fr (ou équivalent). Ce document fixe la palette, la typographie, le logo et quelques règles d'application. Tout est en variables CSS prêtes à coller.

1. Concept en une phrase
Nomos AI — la délibération juridique, augmentée.

Nomos AI (du grec ancien nomos : loi, et krisis : jugement, discernement) est une société de formation en intelligence artificielle juridique, à destination d'avocats et de professionnels du droit sérieux.

L'identité visuelle repose sur deux idées :

Athènes, berceau du droit et de la pensée occidentale. Couleurs et typographie tirées de la Grèce classique : le bleu de la mer Égée, le vert sauge de l'olivier, le marbre tiède du Parthénon.
La délibération dialectique. L'IA juridique n'est pas une balance qui tranche : c'est une confrontation d'arguments qui mène au discernement. Le logo — un monogramme spéculaire de deux K qui se font face, diagonales convergeant vers un point central — traduit cette délibération en signe géométrique.
Le ton général est classique, sobre, érudit. Pas de gradients, pas d'effets, pas de néon. La marque doit pouvoir vivre aussi bien sur un papier à en-tête de cabinet que sur une interface SaaS.

2. Palette
Trois couleurs principales. C'est tout.

Rôle	Nom	HEX	RGB	Usage
Primaire / texte	Bleu Égée	#163A5F	22, 58, 95	Wordmark, texte courant, titres, fond sombre
Accent	Olivier (sauge)	#6B8A5A	107, 138, 90	Accent du logo, liens, balises, hover
Fond	Marbre	#F5F0E1	245, 240, 225	Fond principal du site, cartes
Nuances complémentaires
Nom	HEX	Usage
Marbre profond	#ECE5D0	Cartes posées sur Marbre, sections alternées
Filet (rule)	#D9D2BF	Bordures, séparateurs, hairlines
Texte secondaire	#7A7567	Légendes, métadonnées, datestamps
Texte courant	#2C3540	Paragraphes (légèrement adouci par rapport au Bleu Égée)
Olivier clair	#A8BD93	Variante de l'accent sur fond sombre uniquement
Variables CSS — à coller dans :root
:root {
  /* Couleurs primaires */
  --color-primary:        #163A5F;  /* Bleu Égée */
  --color-accent:         #6B8A5A;  /* Olivier */
  --color-background:     #F5F0E1;  /* Marbre */

  /* Surfaces & filets */
  --color-surface:        #ECE5D0;  /* Marbre profond */
  --color-rule:           #D9D2BF;  /* Filet 1px */

  /* Texte */
  --color-text:           #2C3540;  /* Paragraphes */
  --color-text-muted:     #7A7567;  /* Métadonnées */
  --color-text-on-dark:   #F5F0E1;  /* Texte sur fond Égée */

  /* Variantes pour fond sombre */
  --color-accent-on-dark: #A8BD93;  /* Olivier éclairci */
}
Règles d'usage
Le bleu Égée est dominant. Il porte la voix de la marque : texte, titres, wordmark.
L'olivier est rare. Réservé aux accents : un mot souligné dans un titre, un état hover, l'un des deux K du monogramme, une étiquette. Si tout est olivier, plus rien n'est olivier.
Le marbre est le silence. Fond principal, jamais saturé, jamais blanc pur.
Pas de noir pur. Le texte n'utilise jamais #000. La couleur la plus sombre du site est #163A5F.
Pas de blanc pur. Le fond le plus clair est #F5F0E1.
Contraste minimal AA respecté : Bleu Égée sur Marbre = 10.6:1 ✓. Olivier sur Marbre = 3.9:1 — utilisable seulement pour grand texte ou éléments décoratifs, pas pour du texte courant.
3. Typographie
Wordmark (logo)
Famille : Marcellus (Google Fonts, gratuit)
Graisse : 400 (Regular)
Casse : TOUT EN CAPITALES — NOMOS AI
Interlettrage : 0.28em (très généreux, registre inscriptionnel romain)
À utiliser uniquement pour le wordmark. Ne pas utiliser Marcellus comme typo de titre ailleurs.
Titres & corps de site
Titres : Cormorant Garamond, graisse 500, italique pour les inflexions/emphases.
Corps de texte : Inter, graisses 300/400/500. Le sans-serif moderne assure la lisibilité écran et tient le contraste avec les serifs antiques.
Étiquettes / horodatages : JetBrains Mono, graisse 400, capitales, letter-spacing: 0.18em.
Imports — à coller dans le <head>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,500;0,600;1,400;1,500&family=Inter:wght@300;400;500;600&family=JetBrains+Mono:wght@400;500&family=Marcellus&display=swap" rel="stylesheet">
Variables CSS
:root {
  --font-wordmark: 'Marcellus', 'Trajan Pro', Georgia, serif;
  --font-display:  'Cormorant Garamond', Georgia, serif;
  --font-body:     'Inter', -apple-system, 'Helvetica Neue', Arial, sans-serif;
  --font-mono:     'JetBrains Mono', 'SF Mono', Menlo, monospace;
}
Échelle typographique recommandée
Élément	Famille	Taille	Graisse	Letter-spacing
Hero H1	display	56–72px	500	-0.01em
H2	display	36–44px	500	-0.005em
H3	display	24–28px	500	0
Eyebrow / étiquette	mono	11–12px	500, MAJ	0.18em
Paragraphe	body	16–17px	400	0
Texte large (lede)	body	19–21px	300	0
Bouton	body	14px	500, MAJ	0.08em
Légende	body	13px	400	0
4. Le logo
Anatomie
Le logo se compose de deux éléments :

Le monogramme spéculaire — deux N en miroir, séparés par un point central. Le N gauche en Bleu Égée (le droit, l'argument), le N droit en Olivier (la sagesse, la contre-position). Les diagonales convergent vers un point central : la décision après délibération.
Le wordmark — NOMOS AI en Marcellus, capitales espacées.
Construction du monogramme (SVG, viewBox 1024×1024)
<svg viewBox="0 0 1024 1024" fill="none" xmlns="http://www.w3.org/2000/svg">
  <g fill="none" stroke-linecap="round" stroke-linejoin="round" stroke-width="22">
    <!-- K gauche : Bleu Égée -->
    <path d="M 232 180 L 232 580" stroke="#163A5F"/>
    <path d="M 232 380 L 412 180" stroke="#163A5F"/>
    <path d="M 232 380 L 412 580" stroke="#163A5F"/>
    <!-- K droit (miroir) : Olivier -->
    <path d="M 792 180 L 792 580" stroke="#6B8A5A"/>
    <path d="M 792 380 L 612 180" stroke="#6B8A5A"/>
    <path d="M 792 380 L 612 580" stroke="#6B8A5A"/>
  </g>
  <!-- Point central : le moment de la décision -->
  <circle cx="512" cy="380" r="14" fill="#163A5F"/>
</svg>
Variantes livrées (dossier downloads/)
Fichier	Format	Taille	Fond	Usage
nomos-square-light.svg	SVG	Marbre	site, en-tête, cartes	
nomos-square-dark.svg	SVG	Bleu Égée	fond foncé, hero inversé	
nomos-round-light.svg	SVG	Marbre cerclé	avatar, favicon	
nomos-round-dark.svg	SVG	Bleu Égée rond	avatar fond sombre	
Règles d'application
Taille minimale : monogramme seul à partir de 24×24px. Avec wordmark à partir de 140px de large.
Espace de protection (clear space) : la hauteur d'un K autour du logo, minimum.
Favicon / avatar : utiliser le monogramme seul, sans wordmark.
Fond sombre : sur Bleu Égée, le K de gauche passe en marbre, le K de droite en #A8BD93 (olivier éclairci) pour conserver le contraste.
Ne pas : étirer, ajouter d'ombre, modifier les couleurs, placer sur un fond bariolé, redessiner les K en serif, remplir l'intérieur des K, fermer les diagonales en X.
5. Composants — repères rapides
Boutons
.btn-primary {
  background: var(--color-primary);
  color: var(--color-background);
  font-family: var(--font-body);
  font-weight: 500;
  font-size: 14px;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  padding: 14px 24px;
  border: 0;
  border-radius: 2px;
  transition: background 160ms ease;
}
.btn-primary:hover { background: #0E2A47; }

.btn-secondary {
  background: transparent;
  color: var(--color-primary);
  border: 1px solid var(--color-primary);
  /* même typographie que .btn-primary */
}
Liens
a {
  color: var(--color-primary);
  text-decoration: underline;
  text-decoration-color: var(--color-accent);
  text-decoration-thickness: 1px;
  text-underline-offset: 4px;
}
a:hover { color: var(--color-accent); }
Filets et séparateurs
Utiliser des <hr> à 1px en var(--color-rule). Éviter les ombres portées : on travaille à la ligne, pas au volume.

Frise « méandre » (optionnelle)
Le méandre grec — discret, en olivier, hauteur ~14px — peut servir de séparateur entre grandes sections.

<svg viewBox="0 0 1280 14" preserveAspectRatio="none">
  <pattern id="meander" width="56" height="14" patternUnits="userSpaceOnUse">
    <path d="M0 12 H8 V4 H24 V12 H32 V4 H48 V12 H56"
          fill="none" stroke="#6B8A5A" stroke-width="1"/>
  </pattern>
  <rect width="100%" height="14" fill="url(#meander)"/>
</svg>
6. Voix & ton
Public : avocats, juristes, magistrats — public sérieux.
Registre : sobre, précis, érudit, pas universitaire-poussiéreux. Pas d'emoji. Pas de superlatifs publicitaires.
Métaphore filée : la délibération, le discernement, la décision après confrontation — jamais le « combat », jamais la « victoire ». La marque éclaire, elle ne tranche pas seule : elle aide à juger.
Baseline : « La délibération juridique, augmentée. »
7. À éviter
❌ Noir pur (#000) et blanc pur (#FFF)
❌ Gradients, ombres portées colorées, glassmorphism
❌ Emoji, illustrations cartoon, mascottes
❌ Plus de deux couleurs dans une même vue (Bleu Égée + Marbre, avec un seul accent olivier)
❌ Le symbole de la balance, de Thémis, du marteau du juge
❌ Polices décoratives autres que les quatre listées
❌ Italiques au kilomètre — uniquement pour les inflexions des titres
📄 Nomos AI — Démarche & Choix
À destination du développeur (et de quiconque doit comprendre, défendre ou prolonger l'identité). Pourquoi ce nom, ce signe, ces couleurs, cette typographie. Avant le brief technique, le raisonnement.

Le problème à résoudre
Concevoir une marque pour Nomos AI, une société de formation en intelligence artificielle juridique, à destination d'avocats et de professionnels du droit sérieux.

Trois écueils à éviter :

L'écueil legaltech générique — un nom abstrait inventé (Juro, Lexa, Lawai), une typographie sans-serif moderniste, une palette teal-violet sortie d'un dashboard SaaS. Le résultat : on s'adresse à des avocats avec le vocabulaire visuel des fintechs. Crédibilité zéro auprès du public cible.
L'écueil cabinet d'avocats classique — la balance dorée, Times New Roman, des colonnes de marbre. Le résultat : on dit « tradition » mais on n'a rien à dire sur l'IA. La marque sent la poussière, pas la pensée.
L'écueil de la rupture forcée — un manifeste « On réinvente le droit ! » avec un lettrage manuscrit fluo. Aucun avocat ne s'y reconnaît.
La marque doit tenir la gravité du droit ET la précision de l'outil. Une identité qui parle d'autorité et d'intelligence à la fois.

Le nom : Nomos AI
Le nom combine deux concepts grecs fondamentaux. Nomos (νόμος) signifie la loi, l'ordre établi et le discernement juridique. Krisis (κρίσις) signifie le jugement, le discernement, le moment de la décision. Ensemble, ils expriment :

Le jugement, le discernement — la capacité de séparer le vrai du faux, l'essentiel de l'accessoire ;
Le moment de la décision — l'instant où, après délibération, on tranche ;
L'examen attentif — l'acte de peser les arguments avant de conclure.
C'est exactement ce que fait un juriste — et c'est exactement ce qu'une bonne IA juridique permet : non pas remplacer le jugement, mais l'augmenter en peuplant la délibération de plus d'arguments, de plus de précédents, de plus d'angles. La machine ne décide pas ; elle élargit le champ de ce qu'on peut peser.

Nomos AI a trois vertus pratiques :

Court, mémorable, prononçable dans les langues européennes (no-mos).
Grec, savant, sans être ésotérique. Un avocat reconnaît les racines du droit.
Pas encore usé dans l'écosystème legaltech français. Une identité distincte et ancrée.
Baseline : « La délibération juridique, augmentée. » Augmentée, pas remplacée. C'est la promesse exacte.

L'idée centrale : la dialectique
L'IA juridique ne tranche pas. Elle n'est pas une balance. Elle est un interlocuteur qui élargit la délibération.

Or la délibération a une forme : c'est la dialectique — la confrontation organisée de deux positions, dont émerge le discernement. C'est l'art de Socrate, d'Aristote, de la dispute scolastique médiévale, et finalement de la procédure contradictoire dont tout le droit moderne est l'héritier.

Cette intuition structure toute l'identité :

Deux couleurs principales, qui dialoguent (le bleu, l'olivier) plutôt qu'une seule qui domine ;
Un symbole spéculaire — deux N en miroir, deux interlocuteurs qui se font face ;
Un point au centre — l'instant où la délibération s'arrête sur une décision.
Tout dit la même chose, sous trois angles.

Le signe : deux K spéculaires
Le monogramme est composé de deux lettres N placées en miroir, séparées par un point central.

N · ɴ
Trois lectures simultanées :

La lettre initiale, doublée et confrontée. N est l'initiale de Nomos. La doubler en miroir n'est pas un effet décoratif : c'est traduire la dialectique en typographie. Une lettre devient deux interlocuteurs.
Les diagonales qui convergent vers le centre. Les quatre diagonales (deux par K) pointent toutes vers le centre du signe. La géométrie raconte l'histoire : deux arguments qui se rejoignent dans la décision.
Le point central. Petit, précis, en bleu Égée — il marque le moment où la délibération s'arrête. Le K seul aurait été un monogramme. Le point en fait un récit : il y a eu krisis.
Choix techniques :

Strokes ouvertes, terminaisons rondes. Le signe ne tranche pas — il dialogue. Pas de pointes agressives. Pas d'angles fermés. La précision sans la dureté.
Stroke-width généreuse (22 sur 1024). Visible en favicon comme en banderole. Volonté de présence claire à toutes les échelles — pas un trait timide.
Deux couleurs, pas une. Le N gauche en bleu Égée (le droit, la position), le N droit en olivier (la sagesse, la contre-position). C'est tout l'écart entre Nomos AI et un wordmark monochrome interchangeable.
Pourquoi pas d'autres symboles habituels :

❌ La balance / Thémis — déjà partout dans le secteur, surchargé. Et surtout : Thémis tranche. Nomos AI fait délibérer. Pas la même promesse.
❌ La chouette d'Athéna — joli mais kitsch en logo, et tellement utilisé qu'il ne signifie plus rien.
❌ La colonne grecque, le Parthénon — trop littéral, suggère le passé plutôt que l'augmentation.
❌ Une icône abstraite type "réseau de neurones" — c'est le langage tech, pas le langage droit. On parle au public d'abord, pas à OpenAI.
La palette : Égée & Olivier
Deux pigments et un marbre, tirés directement d'Athènes — berceau du droit, de la dialectique, et de la philosophie occidentale.

Bleu Égée — #163A5F
Le bleu profond de la mer Égée vu depuis la côte attique : ni cobalt vif (trop tech), ni navy industriel (trop banque), mais une teinte chargée d'iode et d'ombre. Sur le plan symbolique : la clarté, l'autorité tranquille, la distance du juriste qui examine. Sur le plan pratique : contraste 10.6:1 sur le marbre — accessibilité AA largement satisfaite pour tout texte courant.

Olivier — #6B8A5A
Le vert sauge de l'olivier qui pousse à Athènes depuis trois millénaires — l'arbre sacré d'Athéna, la couronne du sage, l'emblème de la transmission, de la patience, du discernement lent qui s'enracine. Pas un vert juridique vert-tableau-noir-style ; un vert végétal, mat, méditerranéen. Utilisé en accent rare — un mot souligné, un état hover, l'un des deux K du logo. Sa rareté est ce qui lui donne sa valeur.

Marbre — #F5F0E1
Le ton du marbre du Pentélique vu au soleil, légèrement tiède, jamais blanc pur. C'est le fond du site, le silence sur lequel se posent les deux pigments. Le blanc pur (#FFF) appartient à Apple, à Notion, aux dashboards. Le marbre tiède est un parti pris : la marque a une température.

Pourquoi pas d'or, pas de bordeaux, pas de noir
L'or appartient à la justice institutionnelle, au passé pesant. Nomos AI regarde devant.
Le bordeaux est le code couleur des cabinets britanniques classiques (Magic Circle). Trop référencé, et trop solennel.
Le noir pur n'existe pas dans la palette. Le texte le plus sombre du site est le bleu Égée. Détail : sur fond marbre, le noir tape ; le bleu accompagne.
La typographie : Marcellus pour le wordmark
Le wordmark est composé en Marcellus (Google Fonts, gratuit), tout en capitales, avec un interlettrage très généreux (0.28em).

N O M O S

Pourquoi Marcellus :

C'est une typographie inscriptionnelle, dessinée à partir des capitales romaines monumentales — celles de la colonne Trajane, des frontons, des stèles. Elle ne ressemble à aucun "logotype tech". Elle ressemble à une inscription gravée dans la pierre.
Légèreté + autorité. Trait fin, contraste modéré, terminaisons élégantes : elle dit « pesé, soigné, posé », pas « lourd, premium, banque ».
Free. Pas de licence à gérer, charge légère via Google Fonts.
Différenciation. Nomos AI a un son visuel singulier et mémorable dès la première seconde, distinct de toute autre legaltech.
Pour le reste du site : Cormorant Garamond (titres, inflexions italiques) + Inter (corps de texte) + JetBrains Mono (étiquettes, horodatages). Quatre familles seulement, toutes gratuites, toutes hébergeables sur Google Fonts.

Ce qu'on rejette explicitement
❌ Inter / Roboto / Helvetica seules. Trop neutres, trop SaaS — la marque perd toute densité.
❌ Playfair Display. Top du listing « élégant » mais trop vu, trop "femme blogueuse 2018".
❌ Trajan Pro. L'original inscriptionnel — mais payant, et tellement utilisé dans le cinéma qu'il a perdu son sens. Marcellus en hérite sans le bagage.
❌ Garamond italique au kilomètre. Tentation classique. Tient deux pages, lasse au bout de trois.
L'application : trois disciplines
Discipline n°1 — la rareté de l'accent. L'olivier (#6B8A5A) n'apparaît qu'une fois par vue : sur le N droit du logo, ou sur un état hover, ou sur un mot d'une phrase de titre. Pas davantage. Une couleur qu'on voit partout cesse d'être un accent ; elle devient le décor.

Discipline n°2 — le silence. Le marbre est dominant. Les sections ne sont pas remplies par défaut : elles le sont par nécessité. Toute zone non habitée doit le rester. Le site n'a pas peur du vide ; il en a besoin.

Discipline n°3 — la ligne, pas le volume. Filets à 1 pixel en #D9D2BF. Pas d'ombres portées colorées. Pas de glassmorphism. Pas de fonds en gradient. Nomos AI est dessiné, pas modelé. La hiérarchie visuelle vient de la typographie et de l'espace, jamais d'effets graphiques.

Ce que le site doit donner à voir
À l'arrivée sur la homepage, un avocat doit comprendre en trois secondes :

Ce n'est pas une legaltech générique. La marque a une culture, une assise, une opinion. Le marbre, le serif inscriptionnel, le signe géométrique le disent avant tout texte.
Ce n'est pas un cabinet poussiéreux non plus. L'olivier, le signe contemporain, la mise en page aérée disent un présent, pas un musée.
Le droit est pris au sérieux, et l'IA aussi. Aucune des deux promesses n'est diluée. Pas de « révolution », pas de « disruption ». Une intelligence augmentée pour des juristes sérieux.
Le reste — les pages, les flows, les composants — peut se développer à partir de ce socle. Mais c'est ce socle qu'il faut respecter à la lettre, parce que c'est lui qui fait la différence entre une marque qui a quelque chose à dire et une de plus.