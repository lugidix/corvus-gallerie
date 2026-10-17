# CORVUS × 13 — galerie de styles

Le même produit fictif (CORVUS, agent local d'automatisation nocturne) habillé par
13 skills : **10 thèmes purs** mesurés sur des sites réels + **3 moteurs d'effets**
qui renforcent chaque thème sans jamais changer ses couleurs.

## Pages thèmes (identité préservée)

| Page | Identité | Scène 3D threejs |
|---|---|---|
| [Apple](apple/) | #F5F5F7, pilule bleue #0071E3 | sphère satinée + anneau |
| [Chanel](chanel/) | noir & blanc strict, capitales | tore porcelaine |
| [Dior](Dior/) | noir, didone espacée | monolithe obsidienne |
| [Hermes Agent](hermes-agent/ ou « Hermes Agent/ ») | bleu électrique #0000F2 | tunnel wireframe |
| [Gucci](gucci/) | liseré vert/rouge, Garamond | ruban laiton vert |
| [Hermès maison](hermes-maison/) | blanc + orange #F37021 | ruban TubeGeometry |
| [Louis Vuitton](louis-vuitton/) | brun #8B6337 + or | quatre anneaux dorés |
| [Luxe crème](luxe-creme/) | crème #F5EEE9, Lenis + GSAP | sphères mates |
| [Sombre Awwwards](sombre-awwwards/) | #0F0F0F + jaune, typo géante | tore wireframe géant |
| [Vercel](vercel/) | #0A0A0A, gradient-text | prisme triangulaire |

## Moteurs d'effets (pages autonomes)

- [genjutsu](genjutsu/) — pipeline `paint` : thèse « plume de corbeau », MASTER.md, audit.
- [design-dna](design-dna/) — palette mesurée (ΔE 0,21), lucioles, registre génératif.
- [threejs](threejs/) — murmuration de 600 points, plume iridescente, bloom.

## Corpus

Tout le contenu (manifeste, capacités, récits, chiffres, témoignages…) vient d'une
source unique : [`contenu-corvus.md`](contenu-corvus.md).

Chaque page embarque : reveals au scroll avec stagger, un canvas 2D dans la palette du
thème, une scène three.js r169 avec parallaxe souris, fallback statique si WebGL absent
ou `prefers-reduced-motion`, et pause du rendu hors viewport.

Galerie : [index.html](index.html)
