# CORVUS — corpus canonique

> Source unique de contenu pour tous les tests de skills de la galerie.
> Les skills encodent le vestiaire ; ce fichier reste le corps.
> Chaque page de test puise ici : sections, chiffres, récits, copies. Rien n'invente en dehors.

---

## Identité

- **Nom** : CORVUS
- **Tagline** : L'agent qui exécute tout. Sans un clic.
- **Signature** : Il travaille quand tu dors. Il signe son travail.
- **Mission** : rendre la machine fidèle — veiller, réparer, consigner, sans surveillance.
- **Ton** : sobre, précis, une pointe de malice corvide.
- **Fait distinctif** : un agent local, pas un cloud. Tes scripts, tes logs, ta machine. Il ne quitte jamais le perchoir.

## Manifeste

Un agent n'est pas un assistant. Un assistant attend qu'on lui demande ; un agent sait déjà. CORVUS veille parce que la machine, elle, ne dort jamais : les disques se remplissent, les certificats expirent, les sauvegardes s'oublient. Ce travail invisible mérite un ouvrier invisible.

Nous l'avons bâti sur le corbeau : il se souvient des visages, cache pour l'hiver, reconnaît les outils, et ne donne jamais l'alerte pour rien. La nuit, il patrouille. Au matin, il dépose un rapport signé — pas une notification, un rapport : ce qu'il a vu, ce qu'il a fait, ce qu'il réparera demain.

Aucune magie là-dedans. Des scripts écrits en langage naturel, relus, datés, signés. La seule illusion est celle du repos : tu crois que rien ne s'est passé, et c'est exactement le travail.

## Capacités (8)

1. **Veille 24/7** — Processus, sauvegardes, seuils disque, certificats : surveillés en continu, consignés au matin.
2. **Zéro clic** — La tâche dictée en langage naturel, le script écrit, relu, lancé.
3. **Auto-curatif** — Un service tombe : il redémarre, applique le correctif, consigne l'incident.
4. **Langage naturel** — « Sauvegarde la base toutes les nuits à 3 h, garde sept copies. » Il l'écrit en cron mieux que toi.
5. **Rapports signés** — Chaque intervention produit une note datée, signée, relisible. Rien d'anonyme.
6. **Mémoire de corvidé** — Il se souvient de la dernière panne, du dernier correctif, du dernier visage qui a validé.
7. **Escadrille** — Plusieurs machines, un seul regard : la console regroupe le parc, du portable au serveur de l'atelier.
8. **Silence respecté** — Tout tourne en local, permissions minimales, bac à sable pour tout essai. Il ne parle que quand c'est nécessaire.

## Récits d'usage (3)

**La nuit du disque plein.** Mercredi, 3 h 12. Le disque de sauvegarde atteint 94 %. CORVUS compresse les archives de la semaine, purge les doublons, re-classe les restes. Au matin : 41 % — et une note de trois lignes sur la table de nuit.

**La sauvegarde oubliée.** Le script de sauvegarde tournait plus depuis la mise à jour de février. Personne n'avait vu. Lui si : la date du dernier dépôt manquait au rituel. Il a relancé, vérifié, signé.

**L'escalade silencieuse.** Le certificat du serveur expire dans 72 heures et le renouvellement échoue deux fois. Il réessaie selon la procédure, échoue une troisième, et là — seulement là — il te réveille. Une alerte justifiée vaut dix ignorées.

## Transcript console (pour effets terminal / typing / scramble)

```
$ corvus veille --nuit
23:41  disque sauvegarde 94% → compression des archives
01:07  service "photos" tombé ×1 → relance, correctif appliqué
03:12  purge doublons : 118 Go libérés
04:55  certificat atelier : J-72, renouvellement tenté (échec ×2)
05:30  rapport signé déposé — 3 lignes, 0 clics
$ corvus bilan --matin
nuit #2048 · 2 interventions · 0 escalade
```

## Chiffres (pour compteurs animés)

- **2 048** nuits sans incident majeur
- **97,3 %** des incidents résolus avant le réveil
- **41** machines en escadrille (parc moyen constaté)
- **0** clic, médiane hebdomadaire

## Témoignages (3)

> « Le matin, je lis trois lignes et je sais. Je n'ai plus ouvert un gestionnaire de tâches depuis mars. »
> — Solène M., photographe, 2 machines

> « Il a relancé un service à 1 h du matin et je l'ai su en lisant le rapport. C'est ça, tenir une escadrille. »
> — Karim B., indépendant, 4 machines

> « Mon ancien monitoring me criait dessus. Lui me parle quand il faut. Je dors. »
> — Églantine R., dev backend, 3 machines

## Formules (3)

**Corneille — 0 €**
Pour dompter une machine avec l'agent.
- 1 agent, 1 machine
- Missions illimitées
- Rapports quotidiens
- Communauté

**Corbeau — 9 €/mois** *(recommandé)*
L'escadrille complète, la mémoire longue.
- Agents illimités, 3 machines
- Missions programmées
- Rapports signés et archivés
- Auto-curatif avancé
- Priorité correctifs

**Murmuration — sur devis**
Pour les parcs qui bougent ensemble.
- Parc d'agents illimité
- Console d'escadrille
- Intégrations atelier
- Accompagnement

## FAQ (6)

**Est-ce que ça tourne dans le cloud ?** Non. Tout est local : scripts, journaux, rapports. Rien ne quitte la machine, sauf les mises à jour que tu acceptes.

**Que se passe-t-il si je débranche la machine la nuit ?** Il reprend au retour, là où le rituel s'était arrêté, et le rapport mentionne le trou.

**Peut-il casser quelque chose ?** Chaque essai passe au bac à sable ; chaque action est journalisée et réversible pendant 30 jours.

**Faut-il savoir coder ?** Non. On lui parle, il écrit le script et te le montre avant de l'adopter.

**Différence avec un cron ?** Le cron exécute. CORVUS constate, décide, répare, et rend compte. Le cron ne signe rien.

**Et mon ancien monitoring ?** Il peut le remplacer, ou simplement le surveiller. Les corbeaux ne chassent pas les autres oiseaux, ils les observent.

## Équipe (4)

- **anne.exe** — fondatrice, mécanique du vol. Écrit les boucles qui dorment.
- **corbin** — scripts et langage naturel. Parle à la machine comme à un moineau.
- **freya** — console d'escadrille. Dessine les tableaux de bord de nuit.
- **m. le hibou** — revue de code nocturne. Ne fait pas de bruit, fait des remarques.

## Journal des versions (6)

- **v2.4** — mémoire de corvidé : rappel de la dernière panne dans le rapport du matin.
- **v2.3** — bac à sable étendu aux scripts réseau ; 30 jours de retour arrière.
- **v2.2** — escadrille : la console regroupe jusqu'à 9 machines.
- **v2.1** — rapports signés : chaque intervention porte date et empreinte.
- **v2.0** — langage naturel : dicter la tâche, relire le script.
- **v1.0** — il a veillé sa première nuit. Personne ne l'a remarqué. C'était voulu.

## Concepts visuels (pour heroes 3D, parallaxe, illustrations)

- **Le corbeau de filets** — silhouette de corbeau assemblée en wireframe 1px, qui se recompose à l'arrivée.
- **La plume iridescente** — macro d'une plume bleu-noir où l'accent vert-bleu ne vit que dans le reflet.
- **La console nocturne** — écran seul dans le noir, curseur qui attend, 5 h 30 : le rapport se signe.
- **La table de nuit** — le rapport papier de trois lignes posé à côté d'un téléphone muet.
- **L'escadrille** — trois silhouettes de machines alignées sur un fil, une seule veilleuse allumée.

## Appels à l'action & contact

- Primaire : « Laisser CORVUS veiller »
- Secondaire : « Lire le manifeste »
- Contact : bonjour@corvus.dev
- Mentions : © 2026 Corvus — fait avec soin, la nuit.
