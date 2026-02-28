# TP 05 — Politique de sécurité

## Objectif

Rédiger une politique complète.

## Travail demandé

Rédaction d'une politique d'entreprise.

## Livrable

Document professionnel 4–6 pages.

---

## Solution

---

# POLITIQUE DE SÉCURITÉ DES SYSTÈMES D'INFORMATION (PSSI)

**Entreprise :** TélécomSecure SA  
**Version :** 1.0  
**Date :** Février 2026  
**Classification :** Interne — Diffusion contrôlée  
**Approuvé par :** Direction Générale (COMEX)

---

## Table des matières

1. [Objet et périmètre](#1-objet-et-périmètre)
2. [Références réglementaires et normatives](#2-références-réglementaires-et-normatives)
3. [Gouvernance de la sécurité](#3-gouvernance-de-la-sécurité)
4. [Classification des actifs et des données](#4-classification-des-actifs-et-des-données)
5. [Contrôle d'accès](#5-contrôle-daccès)
6. [Sécurité des réseaux et des communications](#6-sécurité-des-réseaux-et-des-communications)
7. [Gestion des incidents de sécurité](#7-gestion-des-incidents-de-sécurité)
8. [Continuité d'activité](#8-continuité-dactivité)
9. [Sensibilisation et formation](#9-sensibilisation-et-formation)
10. [Conformité et audit](#10-conformité-et-audit)
11. [Sanctions](#11-sanctions)
12. [Révision du document](#12-révision-du-document)

---

## 1. Objet et périmètre

### 1.1 Objet

La présente Politique de Sécurité des Systèmes d'Information (PSSI) définit les principes, les règles et les exigences de sécurité que TélécomSecure SA met en œuvre pour protéger ses systèmes d'information, ses données et ses actifs numériques.

### 1.2 Périmètre

Cette politique s'applique à :
- **L'ensemble du personnel** de TélécomSecure SA (employés, intérimaires, stagiaires)
- **Les prestataires et sous-traitants** ayant accès aux systèmes d'information
- **Tous les systèmes d'information**, incluant les infrastructures réseau (4G/5G, fibre), les serveurs, les postes de travail, les applications métier et les services cloud
- **Toutes les données** traitées, stockées ou transmises par l'entreprise

### 1.3 Objectifs de sécurité

La PSSI vise à garantir les propriétés fondamentales suivantes :
- **Confidentialité** : protéger les informations contre tout accès non autorisé
- **Intégrité** : garantir l'exactitude et la complétude des données
- **Disponibilité** : assurer l'accès aux systèmes et données en temps voulu
- **Traçabilité** : enregistrer et suivre les actions réalisées sur les systèmes

---

## 2. Références réglementaires et normatives

| Référence | Description |
|-----------|-------------|
| RGPD (Règlement UE 2016/679) | Protection des données personnelles |
| Directive NIS 2 (UE 2022/2555) | Sécurité des réseaux et systèmes d'information |
| ISO/IEC 27001:2022 | Système de management de la sécurité de l'information |
| ISO/IEC 27002:2022 | Bonnes pratiques de contrôles de sécurité |
| Loi Informatique et Libertés | Cadre national de protection des données |
| Recommandations ANSSI | Guides de sécurité de l'Agence nationale de la sécurité des systèmes d'information |
| PCI DSS v4.0 | Sécurité des données de cartes de paiement (si applicable) |

---

## 3. Gouvernance de la sécurité

### 3.1 Responsabilités

| Rôle | Responsabilités |
|------|----------------|
| **Direction Générale** | Approuve la PSSI, alloue les ressources et budgets nécessaires |
| **RSSI** | Définit et pilote la stratégie de sécurité, rend compte au COMEX |
| **DPO** | Veille à la conformité RGPD et aux obligations de protection des données |
| **DSI** | Met en œuvre les mesures techniques de sécurité |
| **Managers** | S'assurent du respect de la PSSI dans leurs équipes |
| **Tous les collaborateurs** | Respectent les règles de sécurité et signalent les incidents |

### 3.2 Comité de sécurité

Un comité de sécurité se réunit **mensuellement** et comprend le RSSI, le DSI, le DPO, un représentant de la Direction Générale et les responsables des pôles sécurité. Il a pour missions de :
- Suivre le tableau de bord sécurité et les indicateurs
- Valider les projets de sécurité
- Arbitrer les décisions relatives aux risques
- Assurer le suivi des plans d'action

---

## 4. Classification des actifs et des données

### 4.1 Niveaux de classification

| Niveau | Description | Exemples | Mesures de protection |
|--------|-------------|----------|----------------------|
| **C4 — Très secret** | Données dont la divulgation causerait un préjudice extrêmement grave | Clés de chiffrement, secrets industriels | Chiffrement fort, accès très restreint, double authentification |
| **C3 — Confidentiel** | Données dont la divulgation causerait un préjudice important | Données clients, données financières, code source | Chiffrement, contrôle d'accès strict, journalisation |
| **C2 — Interne** | Données à usage interne uniquement | Procédures internes, organigrammes | Contrôle d'accès par rôle |
| **C1 — Public** | Données pouvant être diffusées publiquement | Communiqués de presse, offres commerciales | Aucune restriction d'accès |

### 4.2 Règles de gestion

- Tout actif informationnel doit être **inventorié** et avoir un **propriétaire** désigné
- Le propriétaire est responsable de la **classification** et de la **revue périodique** de la classification
- Les données classifiées C3 et C4 doivent être **chiffrées** au repos et en transit

---

## 5. Contrôle d'accès

### 5.1 Principes

- **Moindre privilège** : chaque utilisateur ne dispose que des droits strictement nécessaires à sa fonction
- **Besoin d'en connaître** : l'accès à l'information est limité aux personnes qui en ont besoin
- **Séparation des tâches** : les fonctions critiques sont réparties entre plusieurs personnes

### 5.2 Règles

| Domaine | Règle |
|---------|-------|
| Authentification | Authentification multi-facteurs (MFA) obligatoire pour tous les accès aux systèmes critiques et aux accès distants |
| Mots de passe | Minimum 12 caractères, complexité imposée (majuscules, minuscules, chiffres, caractères spéciaux), renouvellement tous les 90 jours |
| Comptes à privilèges | Comptes d'administration nominatifs, distincts des comptes utilisateur, journalisation complète |
| Accès distant | VPN obligatoire avec MFA, postes conformes à la politique de sécurité |
| Revue des droits | Revue trimestrielle des droits d'accès par les managers et le RSSI |
| Départ d'un collaborateur | Désactivation immédiate des accès le jour du départ |

---

## 6. Sécurité des réseaux et des communications

### 6.1 Architecture réseau

- **Segmentation réseau** obligatoire : zones DMZ, réseau de production, réseau d'administration, réseau invités
- **Pare-feu** de nouvelle génération (NGFW) en périmètre et inter-zones
- **Système de détection et prévention d'intrusion** (IDS/IPS) sur les flux réseau critiques

### 6.2 Communications

| Type | Exigence |
|------|----------|
| Communications internes | Chiffrement TLS 1.3 minimum |
| E-mails sensibles | Chiffrement S/MIME ou PGP |
| Transferts de fichiers | SFTP ou solution sécurisée approuvée |
| Wi-Fi | WPA3, réseau dédié pour les invités, réseau distinct pour les postes de travail |

### 6.3 Surveillance

- Journalisation centralisée via un **SIEM** (Security Information and Event Management)
- Rétention des journaux de sécurité pendant **12 mois minimum**
- Surveillance 24/7 par le **SOC** (Security Operations Center)

---

## 7. Gestion des incidents de sécurité

### 7.1 Définition

Un incident de sécurité est tout événement compromettant la confidentialité, l'intégrité ou la disponibilité des systèmes d'information ou des données.

### 7.2 Processus de gestion des incidents

| Phase | Actions | Délai |
|-------|---------|-------|
| **1. Détection** | Identifier l'incident via le SOC, les alertes ou les signalements | Temps réel |
| **2. Qualification** | Évaluer la criticité et classifier l'incident | < 1 heure |
| **3. Confinement** | Isoler les systèmes affectés pour limiter la propagation | < 4 heures |
| **4. Éradication** | Supprimer la cause de l'incident | < 24 heures |
| **5. Restauration** | Remettre les systèmes en état opérationnel | Selon criticité |
| **6. Retour d'expérience** | Analyser l'incident, documenter les leçons apprises | < 1 semaine |

### 7.3 Notification

- **Notification interne** au RSSI dans l'heure suivant la détection
- **Notification à la CNIL** dans les 72 heures en cas de violation de données personnelles (Art. 33 RGPD)
- **Notification aux personnes concernées** si risque élevé pour leurs droits (Art. 34 RGPD)

---

## 8. Continuité d'activité

### 8.1 Plan de Continuité d'Activité (PCA)

- Les processus métier critiques sont identifiés et documentés
- Les **objectifs de temps de reprise (RTO)** et les **objectifs de point de reprise (RPO)** sont définis pour chaque processus critique
- Les sauvegardes sont réalisées quotidiennement et testées mensuellement

### 8.2 Plan de Reprise d'Activité (PRA)

| Élément | Exigence |
|---------|----------|
| Sauvegarde | Règle 3-2-1 : 3 copies, 2 supports différents, 1 copie hors site |
| Site de secours | Datacenter de secours géographiquement distant (> 50 km) |
| Tests PRA | Tests annuels avec exercices de bascule |
| RTO critique | Infrastructure réseau < 4 heures, applications métier < 8 heures |

---

## 9. Sensibilisation et formation

| Public | Type de formation | Fréquence |
|--------|------------------|-----------|
| Tous les collaborateurs | Sensibilisation sécurité générale (phishing, mots de passe, données) | À l'embauche + annuelle |
| Personnel IT | Formation technique avancée (sécurité réseau, gestion des vulnérabilités) | Semestrielle |
| Développeurs | Développement sécurisé (OWASP, secure coding) | Annuelle |
| COMEX et managers | Enjeux stratégiques de la cybersécurité, gouvernance | Annuelle |
| Nouveaux arrivants | Session d'intégration sécurité | À l'embauche |

---

## 10. Conformité et audit

### 10.1 Audits

| Type d'audit | Fréquence | Réalisé par |
|-------------|-----------|-------------|
| Audit interne de sécurité | Semestriel | Auditeur interne / RSSI |
| Audit externe de conformité | Annuel | Cabinet d'audit certifié |
| Tests d'intrusion | Annuel (+ ad hoc pour les projets critiques) | Prestataire externe certifié (PASSI) |
| Scan de vulnérabilités | Mensuel | Équipe sécurité opérationnelle |

### 10.2 Indicateurs de sécurité (KPI)

| Indicateur | Cible |
|-----------|-------|
| Taux de disponibilité des systèmes critiques | > 99,9 % |
| Délai moyen de détection des incidents | < 1 heure |
| Délai moyen de résolution des incidents critiques | < 24 heures |
| Taux de conformité des correctifs de sécurité | > 95 % dans les 30 jours |
| Taux de participation aux formations sécurité | 100 % |
| Nombre de vulnérabilités critiques non corrigées | 0 |

---

## 11. Sanctions

Le non-respect de la présente politique de sécurité peut entraîner des sanctions disciplinaires pouvant aller jusqu'au licenciement, conformément au règlement intérieur de TélécomSecure SA. En cas de violation intentionnelle ou de négligence grave ayant causé un préjudice à l'entreprise, des poursuites judiciaires pourront être engagées.

---

## 12. Révision du document

| Élément | Détail |
|---------|--------|
| Fréquence de révision | Annuelle ou en cas de changement majeur (organisationnel, réglementaire, technique) |
| Responsable de la révision | RSSI |
| Approbation | Direction Générale (COMEX) |
| Diffusion | Tous les collaborateurs via l'intranet, prestataires via les contrats |

---

**Document approuvé par :**

| Nom | Fonction | Date | Signature |
|-----|----------|------|-----------|
| ________________ | Directeur Général | __/__/2026 | ____________ |
| ________________ | RSSI | __/__/2026 | ____________ |
| ________________ | DPO | __/__/2026 | ____________ |
