# Architecture proposée — à valider par Codex

## Découpage
- Frontend : Next.js + TypeScript, responsive, identité PICHA #5850EC.
- Backend PICHA : API TypeScript dédiée, authentification, autorisations, organisations, événements, prestataires, notifications et audit.
- PostgreSQL : source de vérité PICHA pour les données métier et les autorisations.
- Stockage compatible S3 : documents privés, jamais accessibles publiquement.
- Resend : emails transactionnels.
- Plane : candidat optionnel comme moteur de missions, uniquement derrière un adaptateur serveur.

## Règles impératives
- Toute entité métier est rattachée à une organisation. Les événements sont rattachés à une organisation. Les missions et documents sont liés à un événement.
- Aucune clé Plane, S3 ou Resend dans le navigateur.
- Contrôle d'accès serveur sur chaque route et objet, pas seulement dans l'interface.
- La correspondance IDs PICHA ↔ IDs Plane doit être persistée et testée.
- Prévoir une interface TaskProvider avec implémentation locale et/ou Plane pour éviter le verrouillage.
- Éviter une double source de vérité pour statuts, commentaires et affectations : trancher après prototype d'intégration.
- Les opérations cross-organisation sont interdites par défaut.
- Journaliser les changements importants et préserver les historiques.
- Vérifier les licences et obligations AGPL avant de modifier ou exposer Plane comme service.

## Modèle conceptuel initial
User, Organization, Membership, Event, EventMembership, Team, Task, TaskAssignment, TaskComment, TaskChecklistItem, TaskAttachment, TaskActivity, Vendor, VendorEngagement, VendorCheck, Incident, Notification, AuditLog, ExternalTaskMapping.

## Séquence de réalisation
1. Audit de Plane et ADR (adopter, adapter ou abandonner).
2. Socle technique, schéma PostgreSQL, authentification, permissions et tests d'isolation.
3. Événements, membres et rôles.
4. Missions, vues, commentaires, fichiers, validations.
5. Prestataires et suivi terrain.
6. Notifications, tableaux de bord, recette Tropikal Xmas.

Ne pas déployer en production sans revue de sécurité et sauvegardes vérifiées.
