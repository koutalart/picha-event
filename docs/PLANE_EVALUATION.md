# Évaluation de Plane — étude préalable

Plane est un candidat open source, pas une décision irréversible.

## Vérifications requises
- Licence exacte de la version choisie et obligations en cas de modification ou de mise à disposition réseau.
- Fonctionnalités disponibles en Community Edition : workspaces, membres, rôles, tâches, commentaires, fichiers, API, webhooks.
- Possibilité d'isoler strictement plusieurs organisateurs, y compris pour utilisateurs multi-espaces.
- Capacités et limites des API : création, affectation, commentaires, statuts, échéances, pièces jointes, événements webhook, quotas.
- Authentification et clés de service; aucune clé à privilèges élevés côté client.
- Ressources VPS, mise à jour, sauvegardes, migration et restauration.
- Stratégie d'export si Plane est remplacé.
- Test d'intégration bout en bout sur deux organisations avec refus d'accès croisés.

## Décision attendue
Rédiger docs/ADR-001-task-engine.md avec : options Plane / moteur natif / autre open source, matrice avantages-risques, preuves (versions et liens de documentation), prototype minimal, recommandation. Ne pas intégrer Plane en production avant validation de l'ADR.
