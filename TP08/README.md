# TP 08 — Mini audit de sécurité

## Objectif

Comprendre le déroulement d'un audit.

## Travail demandé

Définir critères, preuves, non-conformités.

## Livrable

Rapport d'audit.

---

## Solution

---

# RAPPORT D'AUDIT DE SÉCURITÉ — Réseau informatique d'une PME

**Date de l'audit :** 10-14 février 2026  
**Auditeur :** Cabinet AuditSec (auditeur certifié ISO 27001 Lead Auditor)  
**Entité auditée :** DistribPlus SARL — PME de distribution (120 employés)  
**Référentiel :** ISO/IEC 27001:2022 / ISO/IEC 27002:2022  
**Type d'audit :** Audit de sécurité interne  
**Classification :** Confidentiel

---

## 1. Introduction

### 1.1 Objectif de l'audit

Évaluer le niveau de sécurité du système d'information de DistribPlus SARL, identifier les non-conformités par rapport au référentiel ISO 27001:2022 et formuler des recommandations d'amélioration.

### 1.2 Périmètre

| Élément | Description |
|---------|-------------|
| Infrastructure réseau | LAN, Wi-Fi, accès Internet, VPN |
| Serveurs | 3 serveurs physiques (ERP, fichiers, messagerie) |
| Postes de travail | 120 postes sous Windows 10/11 |
| Applications | ERP (Sage), messagerie (Exchange), CRM |
| Données | Données clients, données financières, données RH |
| Sites | Siège social (Paris) + 2 agences régionales |

### 1.3 Méthodologie

L'audit a été conduit en 5 phases :
1. **Planification** : définition du périmètre et du planning
2. **Revue documentaire** : analyse des politiques et procédures existantes
3. **Entretiens** : responsable IT, direction, utilisateurs clés
4. **Tests techniques** : scans de vulnérabilités, vérifications de configuration
5. **Rédaction du rapport** : constats, preuves, recommandations

---

## 2. Critères d'audit

Les critères d'audit sont les exigences de référence contre lesquelles la conformité est évaluée :

| # | Domaine audité | Critère d'audit (ISO 27001/27002) | Description |
|---|---------------|----------------------------------|-------------|
| C1 | Politique de sécurité | A.5.1 — Politiques de sécurité de l'information | Existence et diffusion d'une PSSI approuvée |
| C2 | Organisation de la sécurité | A.5.2 — Rôles et responsabilités | Rôles sécurité clairement définis et attribués |
| C3 | Gestion des actifs | A.5.9 — Inventaire des actifs | Inventaire à jour des actifs informationnels |
| C4 | Contrôle d'accès | A.5.15 — Contrôle d'accès | Politique de contrôle d'accès formalisée et appliquée |
| C5 | Authentification | A.8.5 — Authentification sécurisée | Mécanismes d'authentification robustes |
| C6 | Gestion des correctifs | A.8.8 — Gestion des vulnérabilités techniques | Processus de patch management en place |
| C7 | Sauvegardes | A.8.13 — Sauvegarde des informations | Politique de sauvegarde et tests de restauration |
| C8 | Sécurité réseau | A.8.20-22 — Sécurité des réseaux | Segmentation, pare-feu, protection périmétrique |
| C9 | Journalisation | A.8.15 — Journalisation | Journalisation des événements de sécurité |
| C10 | Gestion des incidents | A.5.24-28 — Gestion des incidents | Procédure de gestion des incidents de sécurité |
| C11 | Continuité d'activité | A.5.29-30 — Continuité d'activité | Plan de continuité / reprise d'activité |
| C12 | Sensibilisation | A.6.3 — Sensibilisation à la sécurité | Programme de sensibilisation du personnel |

---

## 3. Constats d'audit

### 3.1 Tableau des constats

| # | Critère | Constat | Type | Preuves collectées | Criticité |
|---|---------|--------|------|-------------------|-----------|
| F1 | C1 | Aucune PSSI formalisée. La sécurité repose sur des pratiques informelles. | Non-conformité majeure | Absence de document, confirmation du responsable IT | 🔴 Critique |
| F2 | C2 | Pas de RSSI ni de responsable sécurité désigné. Le responsable IT gère seul tous les aspects. | Non-conformité majeure | Organigramme, entretien direction | 🔴 Critique |
| F3 | C3 | L'inventaire des actifs est un fichier Excel non maintenu depuis 18 mois. Certains équipements ne sont pas répertoriés. | Non-conformité mineure | Fichier Excel daté, comparaison avec l'inventaire physique | 🟠 Élevée |
| F4 | C4 | Les droits d'accès ne sont jamais revus. Des anciens employés ont encore des comptes actifs (3 identifiés). | Non-conformité majeure | Export Active Directory, liste des départs RH | 🔴 Critique |
| F5 | C5 | Mots de passe de 6 caractères minimum sans complexité. Pas de MFA. Le mot de passe administrateur est partagé entre 2 personnes. | Non-conformité majeure | Politique GPO Active Directory, entretien | 🔴 Critique |
| F6 | C6 | Les mises à jour Windows ne sont pas automatisées. 40 % des postes ont des correctifs en retard de plus de 6 mois. Pas de suivi des vulnérabilités. | Non-conformité majeure | Rapport WSUS, scan Nessus | 🔴 Critique |
| F7 | C7 | Les sauvegardes sont réalisées sur un disque externe branché au serveur 24/7 (pas de copie hors site). Jamais testées en restauration. | Non-conformité majeure | Vérification physique, entretien responsable IT | 🔴 Critique |
| F8 | C8 | Réseau à plat (pas de segmentation). Wi-Fi avec mot de passe unique partagé entre employés et visiteurs. Pare-feu avec règles par défaut. | Non-conformité majeure | Scan réseau, configuration pare-feu, entretien | 🔴 Critique |
| F9 | C9 | Journalisation minimale (logs Windows par défaut). Aucune centralisation ni revue des journaux. Rétention de 30 jours seulement. | Non-conformité mineure | Configuration serveurs, entretien | 🟠 Élevée |
| F10 | C10 | Aucune procédure de gestion des incidents documentée. Le responsable IT « gère au cas par cas ». | Non-conformité majeure | Absence de document, entretien | 🟠 Élevée |
| F11 | C11 | Aucun PCA ni PRA formalisé. En cas de sinistre majeur, aucune procédure de reprise n'est définie. | Non-conformité majeure | Absence de document, entretien direction | 🔴 Critique |
| F12 | C12 | Aucune campagne de sensibilisation réalisée. Les employés ne connaissent pas les risques de phishing. | Non-conformité mineure | Entretien employés, absence de supports de formation | 🟠 Élevée |

### 3.2 Synthèse des résultats

| Niveau de conformité | Nombre de critères | Pourcentage |
|---------------------|--------------------|-------------|
| ✅ Conforme | 0 | 0 % |
| ⚠️ Non-conformité mineure | 3 | 25 % |
| ❌ Non-conformité majeure | 9 | 75 % |

**Taux de conformité global : 0 %** — Aucun des 12 critères d'audit n'est pleinement satisfait.

---

## 4. Classification des non-conformités

### 4.1 Non-conformités critiques (traitement immédiat)

| # | Non-conformité | Risque associé |
|---|---------------|----------------|
| F4 | Comptes d'anciens employés actifs | Accès non autorisé aux données de l'entreprise |
| F5 | Mots de passe faibles et partagés | Compromission des comptes, usurpation d'identité |
| F6 | Correctifs en retard de 6+ mois | Exploitation de vulnérabilités connues (ransomware) |
| F7 | Sauvegardes non sécurisées et non testées | Perte de données irréversible en cas d'incident |
| F8 | Réseau non segmenté | Propagation latérale rapide en cas d'intrusion |

### 4.2 Non-conformités élevées (traitement prioritaire)

| # | Non-conformité | Risque associé |
|---|---------------|----------------|
| F1 | Absence de PSSI | Aucun cadre de référence pour la sécurité |
| F2 | Absence de responsable sécurité | Aucun pilotage de la sécurité |
| F10 | Absence de procédure d'incidents | Réponse tardive et inadaptée aux incidents |
| F11 | Absence de PCA/PRA | Arrêt prolongé de l'activité en cas de sinistre |

---

## 5. Plan de recommandations

| Priorité | Recommandation | Non-conformité | Responsable | Délai | Coût estimé |
|----------|---------------|---------------|-------------|-------|-------------|
| 🔴 1 | Désactiver immédiatement les comptes des anciens employés | F4 | Responsable IT | Immédiat | 0 € |
| 🔴 2 | Renforcer la politique de mots de passe (12 car., complexité, MFA) | F5 | Responsable IT | 1 semaine | 500 €/an (MFA) |
| 🔴 3 | Automatiser le déploiement des correctifs (WSUS/Intune) | F6 | Responsable IT | 2 semaines | 0-2 000 € |
| 🔴 4 | Sécuriser les sauvegardes (3-2-1, copie hors site, tests mensuels) | F7 | Responsable IT | 1 mois | 1 000-3 000 €/an |
| 🔴 5 | Segmenter le réseau (VLANs) et sécuriser le Wi-Fi (WPA3, SSID séparé) | F8 | Responsable IT | 1 mois | 2 000-5 000 € |
| 🟠 6 | Rédiger et diffuser une PSSI | F1 | Direction + IT | 2 mois | 0-5 000 € |
| 🟠 7 | Désigner un référent sécurité (interne ou RSSI externalisé) | F2 | Direction | 2 mois | 500-2 000 €/mois |
| 🟠 8 | Mettre à jour et maintenir l'inventaire des actifs | F3 | Responsable IT | 1 mois | 0 € |
| 🟠 9 | Centraliser la journalisation (solution SIEM légère) | F9 | Responsable IT | 3 mois | 1 000-3 000 €/an |
| 🟠 10 | Formaliser la procédure de gestion des incidents | F10 | Référent sécurité | 2 mois | 0 € |
| 🟠 11 | Rédiger un PCA/PRA | F11 | Direction + IT | 3 mois | 0-3 000 € |
| 🟡 12 | Lancer un programme de sensibilisation (e-learning + phishing simulé) | F12 | Référent sécurité + RH | 3 mois | 1 000-3 000 €/an |

**Budget estimé total : 6 000 à 27 000 € la première année**

---

## 6. Conclusion

L'audit de sécurité de DistribPlus SARL révèle un niveau de maturité sécuritaire **très faible**, avec 9 non-conformités majeures sur 12 critères évalués. L'entreprise est exposée à des risques significatifs, notamment :

- **Risque de ransomware** : les correctifs non appliqués et le réseau non segmenté constituent un vecteur d'attaque majeur
- **Risque de fuite de données** : les accès non contrôlés et l'absence de journalisation empêchent toute détection
- **Risque de perte de données** : les sauvegardes non sécurisées et non testées ne garantissent aucune reprise

Les 5 actions critiques (désactivation des comptes, mots de passe, correctifs, sauvegardes, segmentation) doivent être mises en œuvre **immédiatement** pour réduire l'exposition aux risques les plus graves.

Un audit de suivi est recommandé dans **6 mois** pour vérifier la mise en œuvre des recommandations.

---

**Fait à Paris, le 14 février 2026**

**L'auditeur :** ________________ (Certifié ISO 27001 Lead Auditor)

**Le responsable IT :** ________________

**La direction :** ________________
