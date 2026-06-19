# 🧠 Mon IA — assistant personnel

Ton assistant IA **rien qu'à toi**, 100% local. Il connaît tes **projets**, tes
**tâches** et tes **notes**, et t'aide dans **toutes tes activités** (jobs, créa, code…).
Rien ne sort de ton appareil.

## L'idée
« Avoir sa propre IA » = **un modèle open-source + TA mémoire + tes outils**.
- Le **modèle** (cerveau) tourne en local via WebLLM/WebGPU — téléchargé une fois, puis hors-ligne.
- La **mémoire**, c'est ce qui le rend unique : ton profil, tes projets, tes tâches, tes notes
  sont injectés dans le contexte pour qu'il réponde *pour toi*.

## Fonctions (v1)
- **Profil** : qui tu es, tes jobs/activités (utilisé par l'IA).
- **Projets** : tes chantiers, avec description et icône.
- **Tâches** : à faire / fait, rattachables à un projet.
- **Notes** : capture d'idées, recherchées par l'IA quand c'est pertinent.
- **Chat IA** : l'assistant local qui connaît tout ça + **voix** (lecture + micro).
- **PWA** : installable, hors-ligne.

## Usage
Ouvre `index.html` (Chrome/Edge conseillé). Pour les fonctions avancées
(IA WebGPU, micro, hors-ligne), sers le dossier en `https://` ou `localhost` :
```bash
cd mon-ia && python3 -m http.server 8000   # http://localhost:8000
```

## À venir (les « mains » de l'IA)
- Que l'IA **crée/coche des tâches** elle-même depuis le chat.
- Intégrations (agenda, mails, fichiers).
- Mémoire long terme structurée par projet.
