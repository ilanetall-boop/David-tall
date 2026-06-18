# 👁️ Conscience — celle qui te lâche pas

Ta conscience dans la poche. Elle suit ta vie, te fixe des objectifs, te dit quoi
faire au quotidien — et surtout elle **te réclame des preuves**, parce qu'elle sait
que tu peux mentir. Pas de photo = pas validé. Et si tu envoies rien, elle te
confronte : *« t'as craqué ? »*

C'est une app **100% locale** : tout reste sur ton appareil, rien n'est envoyé sur
internet (ni tes données, ni tes photos, ni tes conversations avec l'IA).

## Ce qu'elle fait

- **Check-up de départ** : âge, sexe, taille, poids, activité, objectif poids.
- **Calcul du besoin calorique** (Mifflin-St Jeor) ajusté à ton objectif, avec un
  plancher de sécurité (pas de régime dangereux).
- **Preuves obligatoires** :
  - pesée → photo du pèse-personne (pieds + chiffre visibles) ;
  - repas → photo de l'assiette.
- **Multi-domaines** : elle ne surveille pas que le poids. Tu choisis les domaines
  de ta vie qu'elle suit (sport, eau, sommeil, cigarette, écrans, dépenses, lecture,
  spiritualité…), chacun avec son type de preuve.
- **Missions du jour + indice de conscience** : un score quotidien basé sur les
  preuves que tu donnes, avec l'historique des 7 derniers jours.
- **Elle parle** : synthèse vocale locale (français). Tu peux aussi lui parler au micro.
- **Sa propre IA** : un vrai modèle de langage (WebLLM) qui tourne **entièrement sur
  ton appareil** via WebGPU. Le modèle se télécharge une fois, puis marche hors-ligne.
  Repli automatique en « mode local » si l'appareil ne gère pas WebGPU.
- **Rappels** : notifications locales aux heures que tu définis par engagement.
- **Installable (PWA)** : ajoute-la à ton écran d'accueil, elle marche hors-ligne.

## Comment l'utiliser

### En local
Ouvre `index.html` dans un navigateur récent (**Chrome / Edge** conseillé pour
l'IA et les notifications). Sur téléphone : les boutons photo ouvrent l'appareil photo.

> ⚠️ Certaines fonctions (service worker, micro, notifications, WebGPU) exigent un
> contexte sécurisé : `https://` ou `http://localhost`. En ouvrant le fichier en
> `file://`, l'app fonctionne mais ces fonctions avancées peuvent être bloquées.

Petit serveur local :
```bash
cd conscience
python3 -m http.server 8000
# puis ouvrir http://localhost:8000
```

### En ligne (GitHub Pages)
1. Dans les *Settings* du dépôt → *Pages*, active la publication depuis la branche voulue.
2. L'app sera servie sur `https://<utilisateur>.github.io/<repo>/conscience/`.
3. Ouvre l'URL sur ton téléphone et « Ajouter à l'écran d'accueil ».

## Notes techniques

- Pas de build, pas de dépendances à installer : du HTML/CSS/JS pur.
- Données stockées dans `localStorage` (clé `conscience.v1`).
- L'IA est chargée à la demande depuis `https://esm.run/@mlc-ai/web-llm` ; le modèle
  est ensuite mis en cache par le navigateur et tourne en local.
- L'app n'est pas un avis médical. Pour tout objectif santé, consulte un pro.
