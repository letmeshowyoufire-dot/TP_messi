# TP 06 — Association risques et contrôles

## Objectif

Associer les bons contrôles aux bons risques.

## Travail demandé

Contrôles préventifs, détectifs, correctifs.

## Livrable

Tableau structuré.

---

## Solution

### 1. Contexte

Ce TP vise à associer les contrôles de sécurité appropriés aux risques identifiés dans le TP 03 et classifiés dans le TP 04. Les contrôles sont classés en trois catégories : préventifs, détectifs et correctifs, conformément aux bonnes pratiques ISO 27001/27002 et au cadre NIST CSF.

### 2. Rappel des types de contrôles

| Type de contrôle | Description | Objectif |
|-----------------|-------------|----------|
| **Préventif** | Empêche l'incident de se produire | Réduire la probabilité |
| **Détectif** | Détecte l'incident en cours ou après coup | Identifier rapidement les incidents |
| **Correctif** | Remédie aux conséquences de l'incident | Réduire l'impact et restaurer |

### 3. Tableau d'association risques et contrôles

#### R01 — Ransomware paralysant le SIH (Criticité : 🔴 Critique)

| Type | Contrôle | Référence ISO 27002 | Description |
|------|----------|-------------------|-------------|
| Préventif | Gestion des correctifs (Patch Management) | A.8.8 | Appliquer les correctifs de sécurité sous 30 jours pour les vulnérabilités critiques |
| Préventif | Segmentation réseau | A.8.22 | Isoler les réseaux critiques (SIH, IoMT, administration) |
| Préventif | Protection contre les malwares (EDR/XDR) | A.8.7 | Déployer un EDR sur tous les postes et serveurs |
| Préventif | Filtrage des e-mails et du web | A.8.23 | Solutions anti-spam, anti-phishing et filtrage URL |
| Préventif | Formation anti-phishing | A.6.3 | Campagnes de sensibilisation trimestrielles |
| Détectif | SIEM / SOC 24/7 | A.8.16 | Surveillance continue et corrélation des alertes |
| Détectif | Détection des comportements anormaux (UEBA) | A.8.16 | Identifier les activités suspectes sur les endpoints |
| Correctif | Sauvegardes hors ligne (air-gap) | A.8.13 | Sauvegardes quotidiennes avec copie hors ligne non accessible |
| Correctif | Plan de réponse aux incidents ransomware | A.5.26 | Procédure détaillée de confinement et restauration |
| Correctif | PRA (Plan de Reprise d'Activité) | A.5.30 | Reprise des systèmes critiques en < 4 heures |

#### R02 — Vol de données patients par phishing (Criticité : 🔴 Critique)

| Type | Contrôle | Référence ISO 27002 | Description |
|------|----------|-------------------|-------------|
| Préventif | Authentification multi-facteurs (MFA) | A.8.5 | MFA obligatoire sur tous les accès aux données patients |
| Préventif | Formation et sensibilisation | A.6.3 | Exercices de simulation de phishing réguliers |
| Préventif | Filtrage e-mails avancé | A.8.23 | Détection des liens et pièces jointes malveillantes |
| Préventif | Politique de mots de passe robustes | A.5.17 | Minimum 12 caractères, complexité, non-réutilisation |
| Détectif | Surveillance des connexions suspectes | A.8.16 | Alertes sur les connexions inhabituelles (géo, horaire) |
| Détectif | DLP (Data Loss Prevention) | A.8.12 | Détection des transferts de données sensibles non autorisés |
| Détectif | Journalisation des accès | A.8.15 | Traçabilité complète des accès aux données patients |
| Correctif | Révocation des sessions compromises | A.8.5 | Invalidation immédiate des sessions et tokens |
| Correctif | Notification de violation (RGPD Art. 33-34) | A.5.26 | Procédure de notification CNIL et personnes concernées |

#### R03 — Compromission des dispositifs IoMT (Criticité : 🟠 Élevé)

| Type | Contrôle | Référence ISO 27002 | Description |
|------|----------|-------------------|-------------|
| Préventif | Inventaire et classification des IoMT | A.5.9 | Registre exhaustif de tous les dispositifs médicaux connectés |
| Préventif | Segmentation réseau IoMT | A.8.22 | Réseau dédié isolé pour les dispositifs médicaux |
| Préventif | Mises à jour firmware | A.8.8 | Programme de mise à jour coordonné avec le service biomédical |
| Préventif | Durcissement des configurations | A.8.9 | Désactivation des services et ports inutiles |
| Détectif | Surveillance réseau IoMT | A.8.16 | Monitoring spécifique du trafic des dispositifs médicaux |
| Détectif | Scan de vulnérabilités | A.8.8 | Scans réguliers des dispositifs IoMT |
| Correctif | Isolation d'urgence | A.8.22 | Procédure de déconnexion rapide des dispositifs compromis |
| Correctif | Basculement en mode dégradé | A.5.30 | Procédures manuelles de remplacement |

#### R04 — Accès non autorisé aux dossiers patients (Criticité : 🔴 Critique)

| Type | Contrôle | Référence ISO 27002 | Description |
|------|----------|-------------------|-------------|
| Préventif | Contrôle d'accès basé sur les rôles (RBAC) | A.5.15 | Accès aux dossiers selon le rôle et le service médical |
| Préventif | MFA | A.8.5 | Double authentification pour l'accès au DPI |
| Préventif | Principe du moindre privilège | A.5.15 | Droits minimaux nécessaires à la fonction |
| Préventif | Chiffrement des données | A.8.24 | Chiffrement des données patients au repos et en transit |
| Détectif | Journalisation et audit des accès | A.8.15 | Enregistrement de chaque accès aux dossiers patients |
| Détectif | Revue périodique des droits | A.5.18 | Revue trimestrielle des droits d'accès par les managers |
| Détectif | Alertes sur accès inhabituels | A.8.16 | Détection des accès en dehors des heures ou services habituels |
| Correctif | Révocation immédiate des accès | A.5.18 | Blocage immédiat du compte en cas d'accès non autorisé |

#### R05 — Panne serveur sans sauvegarde fonctionnelle (Criticité : 🟠 Élevé)

| Type | Contrôle | Référence ISO 27002 | Description |
|------|----------|-------------------|-------------|
| Préventif | Redondance matérielle | A.8.14 | Serveurs en cluster, alimentation redondante |
| Préventif | Sauvegardes automatisées (3-2-1) | A.8.13 | 3 copies, 2 supports, 1 hors site |
| Préventif | Maintenance préventive | A.7.13 | Contrats de maintenance et remplacement proactif |
| Détectif | Monitoring infrastructure | A.8.16 | Surveillance des performances et alertes prédictives |
| Détectif | Tests de restauration mensuels | A.8.13 | Vérification mensuelle de l'intégrité des sauvegardes |
| Correctif | PRA avec RTO défini | A.5.30 | Reprise en < 4 h pour les serveurs critiques |

#### R06 — Erreur humaine sur base de données (Criticité : 🟠 Élevé)

| Type | Contrôle | Référence ISO 27002 | Description |
|------|----------|-------------------|-------------|
| Préventif | Procédures opérationnelles documentées | A.5.37 | Procédures détaillées pour toute opération sur les BDD |
| Préventif | Environnements séparés (dev/test/prod) | A.8.31 | Interdiction de tester en production |
| Préventif | Contrôle des changements | A.8.32 | Processus de validation avant toute modification |
| Préventif | Formation des opérateurs | A.6.3 | Formation aux procédures et aux risques |
| Détectif | Journalisation des opérations | A.8.15 | Traçabilité complète des actions sur les BDD |
| Correctif | Restauration de sauvegarde | A.8.13 | Restauration à un point dans le temps (point-in-time recovery) |

#### R07 — Coupure électrique prolongée (Criticité : 🟠 Élevé)

| Type | Contrôle | Référence ISO 27002 | Description |
|------|----------|-------------------|-------------|
| Préventif | Onduleurs (UPS) | A.7.11 | Autonomie de 30 minutes minimum pour les systèmes critiques |
| Préventif | Groupe électrogène | A.7.11 | Démarrage automatique, autonomie de 72 heures |
| Préventif | Double alimentation électrique | A.7.11 | Raccordement à deux sources d'alimentation distinctes |
| Détectif | Surveillance de l'alimentation | A.7.12 | Alertes en temps réel sur les coupures et bascules |
| Correctif | Procédure d'arrêt propre | A.7.11 | Arrêt ordonné des systèmes en cas de dépassement de l'autonomie |
| Correctif | PCA en mode dégradé | A.5.30 | Procédures manuelles de continuité d'activité |

#### R08 — Attaque DDoS sur le réseau (Criticité : 🟡 Modéré)

| Type | Contrôle | Référence ISO 27002 | Description |
|------|----------|-------------------|-------------|
| Préventif | Solution anti-DDoS cloud | A.8.20 | Service de mitigation DDoS chez un prestataire spécialisé |
| Préventif | Dimensionnement des liens réseau | A.8.20 | Bande passante suffisante pour absorber les pics |
| Détectif | Monitoring du trafic réseau | A.8.16 | Détection des volumes anormaux de trafic |
| Correctif | Plan de bascule réseau | A.8.14 | Procédure de bascule vers des liens alternatifs |

### 4. Tableau synthétique

| Risque | Nb Préventifs | Nb Détectifs | Nb Correctifs | Total contrôles |
|--------|:------------:|:-----------:|:------------:|:--------------:|
| R01 — Ransomware | 5 | 2 | 3 | 10 |
| R02 — Vol données (phishing) | 4 | 3 | 2 | 9 |
| R03 — Compromission IoMT | 4 | 2 | 2 | 8 |
| R04 — Accès non autorisé | 4 | 3 | 1 | 8 |
| R05 — Panne serveur | 3 | 2 | 1 | 6 |
| R06 — Erreur humaine BDD | 4 | 1 | 1 | 6 |
| R07 — Coupure électrique | 3 | 1 | 2 | 6 |
| R08 — Attaque DDoS | 2 | 1 | 1 | 4 |
| **Total** | **29** | **15** | **13** | **57** |

### 5. Conclusion

L'association risques-contrôles montre que la majorité des contrôles sont de nature **préventive** (51 %), ce qui est conforme aux bonnes pratiques de sécurité qui privilégient la prévention. Les risques critiques (R01, R02, R04) bénéficient du plus grand nombre de contrôles, reflétant leur priorité de traitement. Chaque risque est couvert par au moins un contrôle de chaque type (préventif, détectif, correctif), assurant une défense en profondeur. L'ensemble des contrôles sont alignés sur les exigences de l'ISO 27002:2022.
