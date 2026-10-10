# Instructions Codex — PICHA Event

Tu travailles dans le dépôt koutalart/picha-event.

## Mission
Construire un MVP SaaS multi-organisateurs de gestion événementielle. Lis d'abord docs/MVP_SPEC.md, docs/ARCHITECTURE.md et docs/PLANE_EVALUATION.md.

## Priorités
1. Auditer Plane, rédiger une ADR fondée sur des tests et des sources.
2. Proposer une architecture maintenable et sécurisée.
3. Implémenter par petites PR vérifiables : auth + isolation, événements, missions, prestataires, documents.
4. Exécuter lint, tests, build et tests d'isolation avant chaque PR.

## Exigences
- Français par défaut dans l'interface.
- Responsive mobile-first, sobre, premium, pas de tableau de bord surchargé.
- Ne pas copier l'interface de ChatGPT.
- Identité PICHA : #5850EC.
- Pas de comptes, mots de passe, clés API ni données privées dans le dépôt.
- Pas d'accès inter-organisateurs; autorisations vérifiées côté serveur.
- Ne pas introduire de dépendance à Plane dans les composants UI : utiliser un adaptateur.
- Pas de déploiement production ni de migration destructive sans validation.
- Ne pas confondre PICHA Event avec PICHA Ticket ou PICHA Scan.

## Première tâche
Inspecte le dépôt, vérifie les hypothèses de docs/PLANE_EVALUATION.md, rédige docs/ADR-001-task-engine.md puis propose le plan de la première PR applicative. N'implémente pas toute la plateforme d'un seul coup.
