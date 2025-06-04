# redis-datadog-guardian

## Présentation

Ce projet Ansible automatise la supervision avancée de Redis et Sentinel avec Datadog. Il permet d'assurer la disponibilité, la conformité et la visibilité des instances Redis dans votre infrastructure.

## Fonctionnalités principales

- **Vérification des services** :
  - Détecte et liste les services Redis et Sentinel actifs sur chaque hôte.
  - Vérifie que l'agent Datadog est bien installé et opérationnel.
- **Configuration automatique** :
  - Configure les fichiers nécessaires pour l'intégration Datadog/Redis.
  - Applique les bonnes pratiques de configuration sur les services Redis/Sentinel.
- **Gestion des rôles Redis** :
  - Identifie les rôles (master, replica, sentinel) de chaque instance.
- **Redémarrage contrôlé** :
  - Orchestration du redémarrage des services Redis/Sentinel si nécessaire.
- **Supervision & logs** :
  - Active la supervision Datadog sur toutes les instances Redis.
  - Met en place la rotation des logs pour garantir la pérennité des journaux.

## Utilisation rapide

1. **Préparer l'inventaire** :
   - Renseignez vos hôtes dans `inventories/hosts`.
2. **Sécuriser les secrets** :
   - Chiffrez vos mots de passe et clés API avec Ansible Vault (ex : `ansible-vault encrypt group_vars/all/vault.yml`).
3. **Lancer le playbook** :
   ```bash
   ansible-playbook deployment/playbook.yml -i inventories/hosts --ask-vault-pass
   ```

## Structure du projet

- `deployment/playbook.yml` : Playbook principal
- `deployment/roles/` : Rôles Ansible modulaires
- `group_vars/` : Variables d'environnement et secrets (à chiffrer)

## Bonnes pratiques

- **Ne stockez jamais de secrets en clair**. Utilisez systématiquement Ansible Vault pour toute information sensible.
- Consultez la documentation officielle Ansible Vault pour plus d'options : https://docs.ansible.com/ansible/latest/user_guide/vault.html

---

Pour toute question ou contribution, contactez l'équipe DevOps. 