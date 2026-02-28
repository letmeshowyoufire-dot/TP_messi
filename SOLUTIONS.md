# SOLUTIONS COMPLÈTES — CSEC 533
## Enterprise Security Infrastructure Controls and Regulatory Compliance

**Travaux Pratiques — Version complète**  
**Date :** Février 2026

---

## Sommaire

1. [TP 01 — Analyse d'un cas réel de non-conformité](#tp-01--analyse-dun-cas-réel-de-non-conformité)
2. [TP 02 — Organisation de la sécurité d'une entreprise](#tp-02--organisation-de-la-sécurité-dune-entreprise)
3. [TP 03 — Identification des risques](#tp-03--identification-des-risques)
4. [TP 04 — Matrice de risques](#tp-04--matrice-de-risques)
5. [TP 05 — Politique de sécurité](#tp-05--politique-de-sécurité)
6. [TP 06 — Association risques et contrôles](#tp-06--association-risques-et-contrôles)
7. [TP 07 — Audit GDPR](#tp-07--audit-gdpr)
8. [TP 08 — Mini audit de sécurité](#tp-08--mini-audit-de-sécurité)
9. [TP 09 — Programme de conformité](#tp-09--programme-de-conformité)
10. [TP 10 — Gestion d'incident et PCA/PRA](#tp-10--gestion-dincident-et-pcapra)

---

# TP 01 — Analyse d'un cas réel de non-conformité

## Objectif

Comprendre les impacts réels d'une violation de données.

## Énoncé

Une entreprise e-commerce subit une fuite de données (noms, emails, mots de passe, cartes bancaires) et reçoit une forte amende GDPR.

## Travail demandé

Identifier les données sensibles, les risques, les lois violées, proposer des mesures correctives.

## Livrable

Rapport 2-3 pages.

---

## Solution

### 1. Identification des données sensibles compromises

| Catégorie | Données | Classification RGPD | Niveau de sensibilité |
|-----------|---------|--------------------|-----------------------|
| Identité | Noms complets | Donnée personnelle (Art. 4 RGPD) | Moyen |
| Contact | Adresses e-mail | Donnée personnelle (Art. 4 RGPD) | Moyen |
| Authentification | Mots de passe | Donnée personnelle critique | Élevé |
| Financière | Numéros de cartes bancaires | Donnée sensible (PCI DSS) | Très élevé |

### 2. Analyse des risques associés

#### Risques pour les personnes concernées

| Risque | Description | Impact | Probabilité |
|--------|-------------|--------|-------------|
| Usurpation d'identité | Utilisation des noms et emails pour créer de faux comptes | Élevé | Moyenne |
| Fraude financière | Utilisation frauduleuse des cartes bancaires | Très élevé | Élevée |
| Credential stuffing | Réutilisation des mots de passe sur d'autres services | Élevé | Très élevée |
| Phishing ciblé | Campagnes de phishing personnalisées grâce aux données volées | Moyen | Élevée |
| Atteinte à la vie privée | Exposition de l'historique d'achats et des habitudes | Moyen | Moyenne |

#### Risques pour l'entreprise

| Risque | Impact estimé |
|--------|---------------|
| Amende RGPD | Jusqu'à 4 % du CA annuel mondial ou 20 M€ |
| Perte de confiance clients | Baisse du chiffre d'affaires de 10 à 30 % |
| Coûts de remédiation | 150 à 200 € par enregistrement compromis |
| Actions en justice collectives | Indemnisations potentielles de plusieurs millions |
| Atteinte à la réputation | Impact durable sur l'image de marque |

### 3. Lois et réglementations violées

| Réglementation | Article(s) violé(s) | Description de la violation |
|----------------|---------------------|-----------------------------|
| **RGPD** (Règlement UE 2016/679) | Art. 5(1)(f) | Principe d'intégrité et de confidentialité non respecté |
| | Art. 25 | Protection des données dès la conception non mise en œuvre |
| | Art. 32 | Mesures de sécurité techniques et organisationnelles insuffisantes |
| | Art. 33 | Notification à l'autorité de contrôle (délai de 72 h potentiellement non respecté) |
| | Art. 34 | Notification aux personnes concernées (en cas de risque élevé) |
| **PCI DSS** | Exigence 3 | Protection des données de cartes stockées non conforme |
| | Exigence 7 | Restriction d'accès aux données de titulaires de cartes insuffisante |
| | Exigence 8 | Authentification et accès insuffisamment sécurisés |
| **Loi Informatique et Libertés** (France) | Art. 34 | Obligation de sécurité des traitements non respectée |
| **Directive NIS 2** (si applicable) | Art. 21 | Mesures de gestion des risques de cybersécurité insuffisantes |

### 4. Mesures correctives proposées

#### Actions immédiates (0-72 h)

1. **Notification à la CNIL** dans un délai de 72 h conformément à l'Art. 33 du RGPD
2. **Notification aux personnes concernées** avec les recommandations de protection (Art. 34)
3. **Réinitialisation forcée** de tous les mots de passe utilisateurs
4. **Blocage des cartes bancaires** compromises en coordination avec les banques émettrices
5. **Isolation et analyse forensique** des systèmes compromis

#### Actions à court terme (1-3 mois)

| Mesure | Objectif | Priorité |
|--------|----------|----------|
| Chiffrement des données au repos (AES-256) | Protéger les données stockées | Critique |
| Hachage des mots de passe (bcrypt/Argon2) | Empêcher la lecture des mots de passe | Critique |
| Tokenisation des cartes bancaires | Supprimer le stockage direct des numéros | Critique |
| Mise en place d'un WAF | Protéger contre les attaques web | Élevée |
| Authentification multi-facteurs (MFA) | Renforcer l'authentification | Élevée |
| Journalisation centralisée (SIEM) | Détecter les incidents en temps réel | Élevée |

#### Actions à moyen terme (3-12 mois)

1. **Audit de sécurité complet** par un prestataire externe certifié
2. **Programme de sensibilisation** du personnel à la sécurité des données
3. **Mise en place d'un DPO** (Délégué à la Protection des Données) si non existant
4. **Tests d'intrusion réguliers** (au minimum annuels)
5. **Plan de réponse aux incidents** formalisé et testé
6. **Certification ISO 27001** pour structurer la gestion de la sécurité
7. **Mise en conformité PCI DSS** avec audit par un QSA (Qualified Security Assessor)

### 5. Conclusion

Cette violation de données illustre les conséquences graves d'un manque de mesures de sécurité adéquates. L'entreprise e-commerce s'expose à des sanctions financières lourdes (amende RGPD pouvant atteindre 4 % du CA mondial), à des pertes commerciales significatives et à une atteinte durable à sa réputation. La mise en œuvre rapide des mesures correctives identifiées est essentielle pour limiter l'impact de l'incident, se conformer aux obligations légales et restaurer la confiance des clients. Une approche proactive de la sécurité, intégrant la protection des données dès la conception (Privacy by Design), doit devenir un pilier stratégique de l'entreprise.


---

# TP 02 — Organisation de la sécurité d'une entreprise

## Objectif

Comprendre la structure de gouvernance sécurité.

## Énoncé

Création d'un service cybersécurité pour une entreprise télécom.

## Travail demandé

Organigramme sécurité, rôles, hiérarchie documentaire.

## Livrable

Schéma + rapport 2 pages.

---

## Solution

### 1. Contexte

L'entreprise télécom « TélécomSecure SA » compte 2 000 employés, gère des infrastructures réseau critiques (fibre, 4G/5G), des données clients sensibles et est soumise à plusieurs réglementations (RGPD, Directive NIS 2, recommandations ANSSI). La création d'un service cybersécurité structuré est indispensable.

### 2. Organigramme du service cybersécurité

```
                    ┌─────────────────────┐
                    │   Direction Générale │
                    │       (CEO)          │
                    └─────────┬───────────┘
                              │
                    ┌─────────▼───────────┐
                    │        RSSI          │
                    │ (Responsable de la   │
                    │ Sécurité des SI)     │
                    │ Rattaché au COMEX    │
                    └─────────┬───────────┘
                              │
          ┌───────────────────┼───────────────────┐
          │                   │                   │
┌─────────▼─────────┐ ┌──────▼──────────┐ ┌──────▼──────────┐
│  Pôle Gouvernance │ │   Pôle SOC      │ │  Pôle Sécurité  │
│  Risques &        │ │   (Security     │ │  Opérationnelle │
│  Conformité       │ │   Operations    │ │                 │
│                   │ │   Center)       │ │                 │
│ • DPO             │ │ • Responsable   │ │ • Architecte    │
│ • Analyste GRC    │ │   SOC           │ │   Sécurité      │
│ • Auditeur        │ │ • Analystes     │ │ • Ingénieurs    │
│   interne         │ │   N1/N2/N3      │ │   Sécurité      │
│                   │ │ • Analyste      │ │ • Pentester     │
│                   │ │   Threat Intel  │ │                 │
└───────────────────┘ └─────────────────┘ └─────────────────┘
```

### 3. Définition des rôles

| Rôle | Rattachement | Missions principales |
|------|-------------|---------------------|
| **RSSI** (Responsable de la Sécurité des SI) | Direction Générale / COMEX | Définir la stratégie sécurité, piloter les budgets, rendre compte au COMEX, superviser tous les pôles |
| **DPO** (Délégué à la Protection des Données) | Pôle Gouvernance | Veiller à la conformité RGPD, gérer les demandes d'exercice de droits, interfacer avec la CNIL |
| **Analyste GRC** | Pôle Gouvernance | Gestion des risques, conformité réglementaire, suivi des indicateurs de sécurité |
| **Auditeur interne** | Pôle Gouvernance | Conduire les audits de sécurité internes, vérifier la conformité des processus |
| **Responsable SOC** | Pôle SOC | Superviser le centre opérationnel de sécurité, coordonner la réponse aux incidents |
| **Analystes SOC N1/N2/N3** | Pôle SOC | Surveiller les alertes (N1), analyser les incidents (N2), mener des investigations approfondies (N3) |
| **Analyste Threat Intelligence** | Pôle SOC | Veille sur les menaces, analyse des indicateurs de compromission (IoC), rapports de menaces |
| **Architecte Sécurité** | Pôle Sécurité Opérationnelle | Concevoir les architectures sécurisées, valider les projets IT sous l'angle sécurité |
| **Ingénieurs Sécurité** | Pôle Sécurité Opérationnelle | Déployer et administrer les solutions de sécurité (pare-feu, SIEM, EDR, IAM) |
| **Pentester** | Pôle Sécurité Opérationnelle | Réaliser des tests d'intrusion, identifier les vulnérabilités, rédiger des rapports de remédiation |

### 4. Hiérarchie documentaire de la sécurité

La documentation de sécurité suit une hiérarchie pyramidale en 4 niveaux :

```
         ┌──────────────────────────┐
         │    Niveau 1 : PSSI       │
         │  (Politique de Sécurité  │
         │  des Systèmes            │
         │  d'Information)          │
         │  ► Document stratégique  │
         │  ► Approuvé par le COMEX │
         └────────────┬─────────────┘
                      │
      ┌───────────────▼────────────────┐
      │   Niveau 2 : Politiques        │
      │   spécifiques                   │
      │   ► Politique d'accès          │
      │   ► Politique de gestion       │
      │     des incidents              │
      │   ► Politique de sauvegarde    │
      │   ► Politique BYOD             │
      └───────────────┬────────────────┘
                      │
      ┌───────────────▼────────────────┐
      │   Niveau 3 : Procédures        │
      │   et standards                  │
      │   ► Procédure de réponse       │
      │     aux incidents              │
      │   ► Standard de durcissement   │
      │   ► Procédure de gestion       │
      │     des correctifs             │
      └───────────────┬────────────────┘
                      │
      ┌───────────────▼────────────────┐
      │   Niveau 4 : Guides et         │
      │   formulaires                   │
      │   ► Guide de sensibilisation   │
      │   ► Checklist d'audit          │
      │   ► Formulaire de demande      │
      │     d'accès                    │
      └────────────────────────────────┘
```

| Niveau | Type de document | Exemples | Responsable |
|--------|-----------------|----------|-------------|
| 1 | Politique générale (PSSI) | PSSI de TélécomSecure SA | RSSI + COMEX |
| 2 | Politiques spécifiques | Politique de contrôle d'accès, Politique de gestion des incidents, Politique de sauvegarde | RSSI |
| 3 | Procédures et standards | Procédure de réponse aux incidents, Standard de durcissement des serveurs, Procédure de patch management | Responsables de pôle |
| 4 | Guides et formulaires | Guide de sensibilisation utilisateur, Checklist d'audit, Formulaire de demande d'accès | Équipes opérationnelles |

### 5. Interactions avec les autres directions

| Direction | Interaction avec le service cybersécurité |
|-----------|------------------------------------------|
| Direction des Systèmes d'Information (DSI) | Collaboration sur l'architecture IT, le déploiement des solutions, la gestion des vulnérabilités |
| Direction Juridique | Conformité réglementaire, gestion des incidents avec implications légales |
| Direction des Ressources Humaines | Sensibilisation du personnel, gestion des accès liés aux mouvements de personnel |
| Direction Commerciale | Sécurité des données clients, conformité des offres |
| Direction Réseau | Sécurisation des infrastructures télécom (cœur de réseau, accès) |

### 6. Conclusion

L'organisation proposée pour le service cybersécurité de TélécomSecure SA repose sur trois pôles complémentaires (Gouvernance, SOC, Sécurité Opérationnelle) sous la direction du RSSI. Cette structure garantit une couverture complète des enjeux de sécurité : gouvernance et conformité, détection et réponse aux incidents, protection opérationnelle des systèmes. La hiérarchie documentaire à 4 niveaux assure la cohérence et la traçabilité de toutes les politiques et procédures de sécurité.


---

# TP 03 — Identification des risques

## Objectif

Identifier menaces et vulnérabilités réelles.

## Énoncé

Analyse des risques d'un système hospitalier.

## Travail demandé

Actifs, menaces, vulnérabilités, impacts.

## Livrable

Tableau ou rapport structuré.

---

## Solution

### 1. Contexte

Le Centre Hospitalier Universitaire (CHU) « Santé+ » gère un système d'information hospitalier (SIH) comprenant le dossier patient informatisé (DPI), les systèmes d'imagerie médicale (PACS), les dispositifs médicaux connectés et les systèmes administratifs. L'analyse de risques est menée selon la méthodologie EBIOS RM / ISO 27005.

### 2. Inventaire des actifs

| ID | Actif | Type | Propriétaire | Criticité |
|----|-------|------|-------------|-----------|
| A01 | Dossier Patient Informatisé (DPI) | Application | Direction médicale | Très élevée |
| A02 | Système d'imagerie médicale (PACS) | Application | Service radiologie | Très élevée |
| A03 | Serveurs du datacenter | Infrastructure | DSI | Très élevée |
| A04 | Réseau local (LAN/Wi-Fi) | Infrastructure | DSI | Élevée |
| A05 | Postes de travail médicaux | Matériel | DSI | Élevée |
| A06 | Dispositifs médicaux connectés (IoMT) | Matériel | Service biomédical | Très élevée |
| A07 | Système de messagerie | Application | DSI | Moyenne |
| A08 | Base de données patients | Données | Direction médicale | Très élevée |
| A09 | Sauvegardes | Données | DSI | Élevée |
| A10 | Personnel médical et IT | Humain | DRH | Élevée |

### 3. Identification des menaces

| ID | Menace | Source | Type | Actifs visés |
|----|--------|--------|------|-------------|
| M01 | Ransomware | Cybercriminels | Intentionnelle externe | A01, A02, A03, A08 |
| M02 | Phishing / Ingénierie sociale | Cybercriminels | Intentionnelle externe | A07, A10 |
| M03 | Vol de données patients | Attaquant interne/externe | Intentionnelle | A01, A08 |
| M04 | Panne matérielle serveurs | Usure / défaut | Accidentelle | A03, A09 |
| M05 | Coupure électrique | Aléa environnemental | Accidentelle | A03, A05, A06 |
| M06 | Erreur humaine (suppression, mauvaise config) | Personnel | Accidentelle interne | A01, A03, A08 |
| M07 | Attaque DDoS | Hacktivistes | Intentionnelle externe | A04 |
| M08 | Exploitation de vulnérabilités IoMT | Cybercriminels | Intentionnelle externe | A06 |
| M09 | Accès non autorisé aux données | Personnel non habilité | Intentionnelle interne | A01, A08 |
| M10 | Catastrophe naturelle (inondation, incendie) | Environnement | Accidentelle | A03, A09 |

### 4. Identification des vulnérabilités

| ID | Vulnérabilité | Actifs concernés | Menaces associées |
|----|---------------|-----------------|-------------------|
| V01 | Systèmes non patchés (Windows 7, logiciels obsolètes) | A03, A05 | M01, M03 |
| V02 | Absence d'authentification multi-facteurs (MFA) | A01, A07 | M02, M03, M09 |
| V03 | Mots de passe faibles ou partagés | A05, A01 | M03, M09 |
| V04 | Absence de segmentation réseau | A04 | M01, M07, M08 |
| V05 | Dispositifs IoMT sans mises à jour de sécurité | A06 | M08 |
| V06 | Absence de chiffrement des données au repos | A08, A09 | M03 |
| V07 | Sauvegardes non testées | A09 | M01, M04, M10 |
| V08 | Absence de formation cybersécurité du personnel | A10 | M02, M06 |
| V09 | Pas de plan de continuité d'activité (PCA) | Tous | M04, M05, M10 |
| V10 | Journalisation insuffisante | A01, A03 | M03, M09 |

### 5. Analyse des impacts

| Scénario de risque | Menace + Vulnérabilité | Impact sur la confidentialité | Impact sur l'intégrité | Impact sur la disponibilité | Impact global |
|-------------------|----------------------|------------------------------|----------------------|---------------------------|---------------|
| Ransomware sur le SIH | M01 + V01, V04 | Moyen (exfiltration possible) | Élevé (chiffrement des données) | Très élevé (arrêt des soins) | **Très élevé** |
| Vol de données patients par phishing | M02 + V02, V08 | Très élevé (fuite données de santé) | Faible | Faible | **Très élevé** |
| Compromission des dispositifs IoMT | M08 + V05, V04 | Moyen | Très élevé (risque vital patient) | Élevé | **Très élevé** |
| Panne serveur sans sauvegarde fonctionnelle | M04 + V07 | Faible | Élevé (perte de données) | Très élevé | **Élevé** |
| Accès non autorisé aux dossiers patients | M09 + V02, V03, V10 | Très élevé | Moyen (modification possible) | Faible | **Élevé** |
| Erreur humaine sur base de données | M06 + V08, V07 | Faible | Élevé (données corrompues) | Élevé | **Élevé** |
| Coupure électrique prolongée | M05 + V09 | Faible | Faible | Très élevé (arrêt des soins) | **Élevé** |
| Attaque DDoS sur le réseau | M07 + V04 | Faible | Faible | Élevé | **Moyen** |

### 6. Synthèse des risques identifiés

| Niveau de risque | Nombre de scénarios | Exemples |
|-----------------|-------------------|----------|
| Très élevé | 3 | Ransomware, vol de données patients, compromission IoMT |
| Élevé | 4 | Panne serveur, accès non autorisé, erreur humaine, coupure électrique |
| Moyen | 1 | Attaque DDoS |

### 7. Recommandations prioritaires

1. **Mise à jour et patching** de tous les systèmes, en priorité les systèmes critiques (DPI, PACS)
2. **Segmentation réseau** pour isoler les dispositifs médicaux, le réseau administratif et le réseau invités
3. **Déploiement du MFA** sur tous les accès aux applications critiques
4. **Chiffrement** des données patients au repos et en transit
5. **Formation et sensibilisation** obligatoire du personnel médical et IT
6. **Tests de sauvegardes** réguliers et mise en place d'un PCA/PRA
7. **Audit de sécurité** des dispositifs IoMT avec le service biomédical

### 8. Conclusion

L'analyse de risques du système hospitalier révèle des vulnérabilités critiques, notamment le manque de segmentation réseau, l'absence de MFA et le non-patchage des systèmes. Les trois scénarios de risque les plus critiques (ransomware, vol de données patients, compromission IoMT) nécessitent une action immédiate. La mise en œuvre des recommandations doit être priorisée selon la criticité des risques identifiés, en tenant compte des contraintes spécifiques au milieu hospitalier (continuité des soins, disponibilité des systèmes 24/7).


---

# TP 04 — Matrice de risques

## Objectif

Classer et prioriser les risques.

## Travail demandé

Probabilité, impact, criticité, stratégie de traitement.

## Livrable

Matrice de risques.

---

## Solution

### 1. Contexte

En prolongement du TP 03 (identification des risques d'un système hospitalier), ce TP consiste à élaborer une matrice de risques permettant de classer, prioriser et définir les stratégies de traitement pour chaque risque identifié.

### 2. Échelles d'évaluation

#### Échelle de probabilité

| Niveau | Valeur | Description |
|--------|--------|-------------|
| Très faible | 1 | Événement exceptionnel (< 1 fois tous les 10 ans) |
| Faible | 2 | Événement rare (1 fois tous les 2-5 ans) |
| Moyenne | 3 | Événement occasionnel (1 fois par an) |
| Élevée | 4 | Événement fréquent (plusieurs fois par an) |
| Très élevée | 5 | Événement très fréquent (mensuel ou plus) |

#### Échelle d'impact

| Niveau | Valeur | Description |
|--------|--------|-------------|
| Très faible | 1 | Impact négligeable, aucune conséquence notable |
| Faible | 2 | Impact limité, perturbation mineure |
| Moyen | 3 | Impact significatif, perturbation notable des opérations |
| Élevé | 4 | Impact majeur, interruption partielle des services |
| Très élevé | 5 | Impact critique, danger pour la vie des patients ou arrêt total |

### 3. Matrice de risques (Probabilité × Impact)

```
Impact →     1          2          3          4          5
Probabilité  Très       Faible     Moyen      Élevé      Très
↓            faible                                      élevé
─────────────────────────────────────────────────────────────────
5 Très       5          10         15         20         25
  élevée     (Modéré)   (Élevé)    (Élevé)    (Critique) (Critique)

4 Élevée     4          8          12         16         20
             (Faible)   (Modéré)   (Élevé)    (Critique) (Critique)

3 Moyenne    3          6          9          12         15
             (Faible)   (Modéré)   (Modéré)   (Élevé)    (Élevé)

2 Faible     2          4          6          8          10
             (Faible)   (Faible)   (Modéré)   (Modéré)   (Élevé)

1 Très       1          2          3          4          5
  faible     (Faible)   (Faible)   (Faible)   (Faible)   (Modéré)
```

#### Légende des niveaux de criticité

| Criticité | Score | Couleur | Action requise |
|-----------|-------|---------|----------------|
| **Critique** | 16-25 | 🔴 Rouge | Traitement immédiat obligatoire |
| **Élevé** | 10-15 | 🟠 Orange | Traitement prioritaire planifié |
| **Modéré** | 5-9 | 🟡 Jaune | Traitement planifié, surveillance |
| **Faible** | 1-4 | 🟢 Vert | Acceptation ou surveillance simple |

### 4. Évaluation des risques identifiés

| ID | Scénario de risque | Probabilité (1-5) | Impact (1-5) | Score (P×I) | Criticité |
|----|-------------------|-------------------|-------------|------------|-----------|
| R01 | Ransomware paralysant le SIH | 4 | 5 | **20** | 🔴 Critique |
| R02 | Vol de données patients par phishing | 4 | 5 | **20** | 🔴 Critique |
| R03 | Compromission des dispositifs IoMT | 3 | 5 | **15** | 🟠 Élevé |
| R04 | Accès non autorisé aux dossiers patients | 4 | 4 | **16** | 🔴 Critique |
| R05 | Panne serveur sans sauvegarde fonctionnelle | 3 | 4 | **12** | 🟠 Élevé |
| R06 | Erreur humaine sur la base de données | 3 | 4 | **12** | 🟠 Élevé |
| R07 | Coupure électrique prolongée | 2 | 5 | **10** | 🟠 Élevé |
| R08 | Attaque DDoS sur le réseau | 3 | 3 | **9** | 🟡 Modéré |
| R09 | Catastrophe naturelle (inondation) | 1 | 5 | **5** | 🟡 Modéré |
| R10 | Défaillance de la messagerie | 3 | 2 | **6** | 🟡 Modéré |

### 5. Positionnement dans la matrice

```
Impact →     1          2          3          4          5
Probabilité
↓
─────────────────────────────────────────────────────────────────
5 Très       .          .          .          .          .
  élevée

4 Élevée     .          .          .          R04        R01, R02
                                              (16)       (20)

3 Moyenne    .          R10        R08        R05, R06   R03
                        (6)        (9)        (12)       (15)

2 Faible     .          .          .          .          R07
                                                         (10)

1 Très       .          .          .          .          R09
  faible                                                 (5)
```

### 6. Stratégies de traitement des risques

| ID | Risque | Criticité | Stratégie | Mesures de traitement | Responsable | Délai |
|----|--------|-----------|-----------|----------------------|-------------|-------|
| R01 | Ransomware | 🔴 Critique | **Réduire** | Segmentation réseau, EDR, sauvegardes hors ligne, plan de réponse aux incidents | RSSI + DSI | 1 mois |
| R02 | Vol données (phishing) | 🔴 Critique | **Réduire** | MFA, formation anti-phishing, filtrage email avancé, DLP | RSSI + DRH | 1 mois |
| R04 | Accès non autorisé | 🔴 Critique | **Réduire** | Contrôle d'accès RBAC, MFA, journalisation, revue des droits | RSSI + DSI | 2 mois |
| R03 | Compromission IoMT | 🟠 Élevé | **Réduire** | Segmentation IoMT, inventaire, mises à jour firmware, surveillance | RSSI + Biomédical | 3 mois |
| R05 | Panne serveur | 🟠 Élevé | **Réduire** | Redondance serveurs, tests de restauration mensuels, PRA | DSI | 2 mois |
| R06 | Erreur humaine BDD | 🟠 Élevé | **Réduire** | Procédures opérationnelles, sauvegardes automatiques, formation | DSI + DRH | 2 mois |
| R07 | Coupure électrique | 🟠 Élevé | **Réduire** | Onduleurs, groupe électrogène, test mensuel, contrat maintenance | Services généraux | 3 mois |
| R08 | Attaque DDoS | 🟡 Modéré | **Transférer** | Solution anti-DDoS cloud (contrat prestataire), plan de bascule | DSI | 3 mois |
| R09 | Catastrophe naturelle | 🟡 Modéré | **Transférer** | Assurance, datacenter de secours géographiquement distant | Direction + DSI | 6 mois |
| R10 | Défaillance messagerie | 🟡 Modéré | **Accepter** | Redondance basique, canal de communication alternatif | DSI | 6 mois |

### 7. Les quatre stratégies de traitement des risques

| Stratégie | Description | Quand l'utiliser |
|-----------|-------------|------------------|
| **Éviter** | Supprimer l'activité ou la source du risque | Quand le risque est inacceptable et le coût de traitement trop élevé |
| **Réduire** | Mettre en place des contrôles pour diminuer la probabilité ou l'impact | Stratégie la plus courante, applicable à la majorité des risques |
| **Transférer** | Externaliser le risque (assurance, sous-traitance) | Quand le risque peut être géré plus efficacement par un tiers |
| **Accepter** | Assumer le risque en connaissance de cause | Quand le coût du traitement dépasse l'impact potentiel |

### 8. Suivi et révision

| Indicateur | Fréquence | Responsable |
|-----------|-----------|-------------|
| Revue de la matrice de risques | Trimestrielle | RSSI |
| Tests de sauvegardes | Mensuelle | DSI |
| Campagne de sensibilisation phishing | Trimestrielle | RSSI + DRH |
| Audit de conformité des accès | Semestrielle | Auditeur interne |
| Test du PRA/PCA | Annuelle | DSI + RSSI |

### 9. Conclusion

La matrice de risques révèle 3 risques critiques (ransomware, vol de données par phishing, accès non autorisé) nécessitant un traitement immédiat, et 4 risques élevés à traiter en priorité. La stratégie dominante est la réduction du risque par la mise en place de contrôles techniques et organisationnels. Le suivi trimestriel de la matrice permet d'ajuster les priorités en fonction de l'évolution du contexte de menaces.


---

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


---

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


---

# TP 07 — Audit GDPR

## Objectif

Vérifier la conformité d'une application mobile.

## Travail demandé

Analyse GDPR, violations, correctifs.

## Livrable

Rapport d'audit.

---

## Solution

---

# RAPPORT D'AUDIT RGPD — Application mobile « HealthTrack »

**Date de l'audit :** Février 2026  
**Auditeur :** Service Conformité — Pôle Gouvernance, Risques & Conformité  
**Application auditée :** HealthTrack v3.2 (application mobile de suivi de santé)  
**Commanditaire :** Direction Générale de HealthTrack SAS  
**Classification :** Confidentiel

---

## 1. Contexte et périmètre

### 1.1 Description de l'application

HealthTrack est une application mobile (iOS et Android) permettant aux utilisateurs de :
- Suivre leurs paramètres de santé (poids, tension, glycémie, activité physique)
- Prendre des rendez-vous médicaux
- Stocker et partager des documents médicaux (ordonnances, résultats d'analyses)
- Communiquer par messagerie avec des professionnels de santé

### 1.2 Données traitées

| Type de données | Catégorie RGPD | Volume estimé |
|----------------|---------------|---------------|
| Nom, prénom, date de naissance | Données personnelles | 500 000 utilisateurs |
| Adresse e-mail, téléphone | Données personnelles | 500 000 utilisateurs |
| Données de santé (tension, glycémie, poids) | Données sensibles (Art. 9) | 500 000 utilisateurs |
| Documents médicaux (ordonnances, analyses) | Données sensibles (Art. 9) | ~2 millions de documents |
| Données de géolocalisation | Données personnelles | Collecte continue |
| Données de paiement | Données personnelles | 150 000 utilisateurs premium |

### 1.3 Périmètre de l'audit

L'audit couvre les exigences du RGPD (Règlement UE 2016/679) applicables à l'application HealthTrack, incluant :
- Licéité du traitement et consentement
- Droits des personnes concernées
- Sécurité des données
- Transferts internationaux
- Gouvernance et documentation

---

## 2. Méthodologie d'audit

L'audit a été réalisé selon la méthodologie suivante :
1. **Revue documentaire** : politique de confidentialité, registre des traitements, analyses d'impact (AIPD)
2. **Entretiens** avec les équipes développement, juridique et sécurité
3. **Tests techniques** : analyse de l'application, des flux de données, des API
4. **Vérification terrain** : tests des droits des personnes, processus de consentement

---

## 3. Résultats de l'audit

### 3.1 Tableau de conformité

| # | Exigence RGPD | Article | Statut | Criticité |
|---|--------------|---------|--------|-----------|
| 1 | Licéité du traitement | Art. 6 | ⚠️ Non-conformité partielle | Élevée |
| 2 | Consentement pour données de santé | Art. 9 | ❌ Non-conforme | Critique |
| 3 | Information des personnes (transparence) | Art. 13-14 | ⚠️ Non-conformité partielle | Élevée |
| 4 | Droit d'accès | Art. 15 | ✅ Conforme | — |
| 5 | Droit de rectification | Art. 16 | ✅ Conforme | — |
| 6 | Droit à l'effacement | Art. 17 | ❌ Non-conforme | Critique |
| 7 | Droit à la portabilité | Art. 20 | ⚠️ Non-conformité partielle | Moyenne |
| 8 | Protection des données dès la conception (Privacy by Design) | Art. 25 | ❌ Non-conforme | Critique |
| 9 | Sécurité des données | Art. 32 | ❌ Non-conforme | Critique |
| 10 | Analyse d'Impact (AIPD) | Art. 35 | ❌ Non-conforme | Critique |
| 11 | Registre des traitements | Art. 30 | ⚠️ Non-conformité partielle | Moyenne |
| 12 | Délégué à la Protection des Données (DPO) | Art. 37-39 | ✅ Conforme | — |
| 13 | Notification de violation | Art. 33-34 | ⚠️ Non-conformité partielle | Élevée |
| 14 | Transferts internationaux | Art. 44-49 | ❌ Non-conforme | Critique |
| 15 | Sous-traitants | Art. 28 | ⚠️ Non-conformité partielle | Élevée |

### 3.2 Détail des non-conformités critiques

#### NC-01 : Consentement pour données de santé (Art. 9)

**Constat :** Le traitement des données de santé repose sur un consentement implicite lors de l'inscription. Le consentement n'est pas explicite, spécifique et granulaire comme exigé par l'Art. 9(2)(a) du RGPD.

**Preuve :** Lors de l'inscription, une seule case à cocher couvre à la fois les CGU, la politique de confidentialité et le consentement au traitement des données de santé.

**Risque :** Amende jusqu'à 20 M€ ou 4 % du CA mondial. Invalidation de la base légale de traitement.

**Recommandation :** Mettre en place un consentement explicite, séparé et granulaire pour chaque finalité de traitement des données de santé.

#### NC-02 : Droit à l'effacement (Art. 17)

**Constat :** La demande de suppression de compte ne supprime pas effectivement toutes les données personnelles. Les données de santé sont conservées dans les sauvegardes pendant 5 ans sans justification.

**Preuve :** Test réalisé avec un compte de test : après demande de suppression, les données restent accessibles via l'API interne pendant 6 mois.

**Risque :** Violation directe du droit à l'effacement. Plaintes possibles auprès de la CNIL.

**Recommandation :** Supprimer effectivement toutes les données dans un délai de 30 jours. Documenter les exceptions légales de conservation.

#### NC-03 : Privacy by Design (Art. 25)

**Constat :** La géolocalisation est activée par défaut sans nécessité pour le service principal. Les données de santé sont transmises en clair dans certains flux internes.

**Preuve :** Analyse du trafic réseau montrant des données de santé non chiffrées entre l'application et le microservice de notification.

**Risque :** Interception des données de santé en transit. Non-respect du principe de minimisation.

**Recommandation :** Désactiver la géolocalisation par défaut. Chiffrer tous les flux contenant des données de santé (TLS 1.3).

#### NC-04 : Sécurité des données (Art. 32)

**Constat :**
- Mots de passe stockés avec l'algorithme MD5 (obsolète et vulnérable)
- Pas de chiffrement des données de santé au repos dans la base de données
- Pas de limitation du nombre de tentatives de connexion (brute force possible)
- Tokens d'API sans expiration

**Preuve :** Analyse du code source et tests d'intrusion.

**Risque :** Compromission massive des comptes et des données de santé.

**Recommandation :**
- Migrer vers bcrypt ou Argon2 pour le hachage des mots de passe
- Chiffrer les données de santé au repos (AES-256)
- Limiter les tentatives de connexion (blocage après 5 échecs)
- Définir une expiration des tokens (max 24 h)

#### NC-05 : Absence d'AIPD (Art. 35)

**Constat :** Aucune Analyse d'Impact relative à la Protection des Données (AIPD) n'a été réalisée, alors que le traitement à grande échelle de données de santé l'exige obligatoirement.

**Preuve :** Absence de document AIPD dans la documentation du projet.

**Risque :** Non-conformité flagrante, aggravant toute sanction en cas de violation.

**Recommandation :** Réaliser une AIPD complète selon la méthodologie de la CNIL (PIA) avant toute évolution de l'application.

#### NC-06 : Transferts internationaux (Art. 44-49)

**Constat :** Les données sont hébergées chez un fournisseur cloud américain sans garanties appropriées (pas de Clauses Contractuelles Types à jour, pas d'évaluation de l'impact du transfert post-Schrems II).

**Preuve :** Contrat d'hébergement avec AWS US-East sans CCT ni mécanisme de transfert conforme.

**Risque :** Transfert illégal de données de santé hors UE. Amende majeure.

**Recommandation :** Migrer vers un hébergement en UE (AWS Frankfurt ou OVH) ou mettre en place des CCT avec mesures complémentaires.

---

## 4. Plan d'actions correctives

| Priorité | Action | Non-conformité | Responsable | Délai |
|----------|--------|---------------|-------------|-------|
| 1 — Urgente | Chiffrement des données de santé en transit et au repos | NC-03, NC-04 | CTO | 1 mois |
| 2 — Urgente | Migration du hachage des mots de passe vers Argon2 | NC-04 | Équipe Dev | 1 mois |
| 3 — Urgente | Mise en place du consentement granulaire | NC-01 | Équipe Produit + Juridique | 2 mois |
| 4 — Élevée | Réalisation de l'AIPD | NC-05 | DPO | 2 mois |
| 5 — Élevée | Migration hébergement vers UE | NC-06 | CTO + DSI | 3 mois |
| 6 — Élevée | Correction du processus de suppression des données | NC-02 | Équipe Dev | 2 mois |
| 7 — Moyenne | Mise à jour du registre des traitements | #11 | DPO | 1 mois |
| 8 — Moyenne | Implémentation de la portabilité au format standard | #7 | Équipe Dev | 3 mois |
| 9 — Moyenne | Mise à jour des contrats sous-traitants (Art. 28) | #15 | Juridique | 2 mois |
| 10 — Standard | Formalisation de la procédure de notification de violation | #13 | DPO + RSSI | 1 mois |

---

## 5. Conclusion

L'audit RGPD de l'application HealthTrack révèle **6 non-conformités critiques** et **6 non-conformités partielles** sur les 15 exigences auditées. Le taux de conformité global est de **20 %** (3 exigences conformes sur 15).

Les non-conformités les plus graves concernent :
- La sécurité des données de santé (stockage en clair, hachage MD5)
- L'absence d'AIPD obligatoire
- Le transfert non conforme de données hors UE
- Le consentement non explicite pour les données de santé

**Le niveau de risque réglementaire est CRITIQUE.** L'entreprise s'expose à une amende pouvant atteindre 20 millions d'euros ou 4 % du CA mondial, ainsi qu'à une mise en demeure de la CNIL avec obligation de mise en conformité sous astreinte.

La mise en œuvre immédiate du plan d'actions correctives est impérative.

---

**Fait à Paris, le __ février 2026**

**L'auditeur :** ________________  
**Le DPO :** ________________


---

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


---

# TP 09 — Programme de conformité

## Objectif

Construire un programme GRC.

## Travail demandé

Stratégie, contrôles, indicateurs.

## Livrable

Plan stratégique 6 pages.

---

## Solution

---

# PROGRAMME DE CONFORMITÉ GRC (Gouvernance, Risques, Conformité)

**Entreprise :** FinanceGuard SA — Société de services financiers  
**Effectif :** 800 employés  
**Date :** Février 2026  
**Version :** 1.0  
**Classification :** Confidentiel — Diffusion restreinte  
**Approuvé par :** Comité Exécutif (COMEX)

---

## Table des matières

1. [Résumé exécutif](#1-résumé-exécutif)
2. [Contexte et enjeux](#2-contexte-et-enjeux)
3. [Cadre de gouvernance](#3-cadre-de-gouvernance)
4. [Stratégie de gestion des risques](#4-stratégie-de-gestion-des-risques)
5. [Programme de conformité réglementaire](#5-programme-de-conformité-réglementaire)
6. [Contrôles de sécurité](#6-contrôles-de-sécurité)
7. [Indicateurs de performance (KPI/KRI)](#7-indicateurs-de-performance-kpikri)
8. [Feuille de route et planning](#8-feuille-de-route-et-planning)
9. [Budget et ressources](#9-budget-et-ressources)
10. [Conclusion](#10-conclusion)

---

## 1. Résumé exécutif

FinanceGuard SA, en tant qu'acteur du secteur financier, est soumise à un environnement réglementaire complexe et en constante évolution. Le présent programme GRC définit une approche structurée et intégrée de la gouvernance, de la gestion des risques et de la conformité. Il vise à :

- **Protéger** les actifs informationnels et les données clients
- **Garantir** la conformité aux réglementations en vigueur (RGPD, DORA, NIS 2, LPM)
- **Réduire** l'exposition aux risques cyber et opérationnels
- **Démontrer** la maturité sécuritaire auprès des régulateurs et des clients
- **Optimiser** les investissements sécurité par une approche basée sur les risques

---

## 2. Contexte et enjeux

### 2.1 Contexte réglementaire

| Réglementation | Périmètre | Échéance / Statut |
|----------------|-----------|-------------------|
| **RGPD** (Règlement UE 2016/679) | Protection des données personnelles des clients et employés | En vigueur, conformité continue |
| **DORA** (Digital Operational Resilience Act) | Résilience opérationnelle numérique du secteur financier | Applicable janvier 2025 |
| **NIS 2** (Directive UE 2022/2555) | Sécurité des réseaux et systèmes d'information | Transposition nationale en cours |
| **LPM** (Loi de Programmation Militaire) | Opérateurs d'importance vitale (OIV) | En vigueur |
| **Bâle III / Pilier 2** | Risques opérationnels et contrôle interne | En vigueur |
| **ACPR** (Autorité de Contrôle Prudentiel et de Résolution) | Supervision bancaire et financière | Contrôles réguliers |

### 2.2 Enjeux stratégiques

| Enjeu | Description | Impact |
|-------|-------------|--------|
| Sanctions financières | Amendes réglementaires (RGPD : 4 % CA, DORA : sanctions pénales) | Très élevé |
| Confiance des clients | Les clients attendent un haut niveau de protection de leurs données | Élevé |
| Continuité d'activité | Toute interruption de service affecte directement les revenus | Très élevé |
| Avantage concurrentiel | La maturité GRC est un différenciateur sur le marché | Moyen |
| Responsabilité des dirigeants | DORA et NIS 2 engagent la responsabilité personnelle des dirigeants | Élevé |

---

## 3. Cadre de gouvernance

### 3.1 Organisation GRC

```
                ┌──────────────────────┐
                │       COMEX          │
                │ (Validation          │
                │  stratégique)        │
                └──────────┬───────────┘
                           │
                ┌──────────▼───────────┐
                │   Comité GRC         │
                │ (Pilotage mensuel)   │
                │ RSSI + DPO + Dir.    │
                │ Risques + Dir.       │
                │ Conformité + DSI     │
                └──────────┬───────────┘
                           │
        ┌──────────────────┼──────────────────┐
        │                  │                  │
┌───────▼───────┐  ┌───────▼───────┐  ┌───────▼───────┐
│ Gouvernance   │  │  Gestion des  │  │  Conformité   │
│ Sécurité      │  │  Risques      │  │               │
│               │  │               │  │               │
│ • RSSI        │  │ • Dir. Risques│  │ • Dir.        │
│ • SOC Manager │  │ • Analystes   │  │   Conformité  │
│ • Architecte  │  │   risques     │  │ • DPO         │
│   sécurité    │  │               │  │ • Auditeurs   │
│ • Ingénieurs  │  │               │  │   internes    │
│   sécurité    │  │               │  │               │
└───────────────┘  └───────────────┘  └───────────────┘
```

### 3.2 Rôles et responsabilités

| Rôle | Responsabilités clés |
|------|---------------------|
| **COMEX** | Valide la stratégie GRC, alloue le budget, porte la responsabilité ultime |
| **Comité GRC** | Pilote le programme, arbitre les décisions, suit les indicateurs |
| **RSSI** | Définit et met en œuvre la stratégie de sécurité de l'information |
| **Directeur des Risques** | Pilote le processus d'analyse et de traitement des risques |
| **Directeur de la Conformité** | Assure la veille réglementaire et le suivi de la conformité |
| **DPO** | Garantit la conformité RGPD et la protection des données personnelles |
| **Auditeurs internes** | Réalisent les audits de conformité et de sécurité |
| **SOC Manager** | Supervise la détection et la réponse aux incidents |

### 3.3 Comités et instances

| Instance | Composition | Fréquence | Missions |
|----------|------------|-----------|----------|
| Comité GRC | RSSI, Dir. Risques, Dir. Conformité, DPO, DSI | Mensuelle | Pilotage du programme, décisions |
| Comité de sécurité opérationnelle | RSSI, SOC Manager, Ingénieurs sécurité | Hebdomadaire | Suivi opérationnel, incidents |
| Revue de direction (COMEX) | COMEX + RSSI | Trimestrielle | Reporting stratégique, budget |
| Comité de crise | Direction + RSSI + Communication + Juridique | Ad hoc | Gestion des incidents majeurs |

---

## 4. Stratégie de gestion des risques

### 4.1 Méthodologie

La gestion des risques s'appuie sur la méthodologie **EBIOS Risk Manager** de l'ANSSI, complétée par les exigences ISO 27005 et le cadre NIST CSF 2.0.

### 4.2 Processus de gestion des risques

| Phase | Description | Fréquence |
|-------|-------------|-----------|
| 1. Identification | Inventaire des actifs, identification des menaces et vulnérabilités | Continue + revue annuelle |
| 2. Analyse | Évaluation de la probabilité et de l'impact (matrice 5×5) | Trimestrielle |
| 3. Évaluation | Classification et priorisation des risques | Trimestrielle |
| 4. Traitement | Choix de la stratégie (réduire, transférer, éviter, accepter) | Selon criticité |
| 5. Surveillance | Suivi des indicateurs de risques (KRI) et réévaluation | Continue |
| 6. Communication | Reporting au Comité GRC et au COMEX | Mensuelle / Trimestrielle |

### 4.3 Appétence au risque

| Catégorie de risque | Niveau d'appétence | Seuil d'acceptation |
|--------------------|-------------------|---------------------|
| Risque cyber (données clients) | Très faible | Score ≤ 4 (matrice 5×5) |
| Risque de conformité réglementaire | Très faible | Score ≤ 4 |
| Risque opérationnel (disponibilité) | Faible | Score ≤ 6 |
| Risque de réputation | Très faible | Score ≤ 4 |
| Risque financier (fraude) | Très faible | Score ≤ 4 |

### 4.4 Cartographie des risques majeurs

| # | Risque | Probabilité | Impact | Score | Stratégie |
|---|--------|------------|--------|-------|-----------|
| R1 | Cyberattaque ciblée (APT) | 4 | 5 | 20 | Réduire |
| R2 | Fuite de données clients | 3 | 5 | 15 | Réduire |
| R3 | Non-conformité DORA | 3 | 4 | 12 | Réduire |
| R4 | Indisponibilité des services critiques | 3 | 5 | 15 | Réduire |
| R5 | Fraude interne | 2 | 4 | 8 | Réduire + Transférer |
| R6 | Défaillance d'un prestataire critique | 3 | 4 | 12 | Transférer + Réduire |
| R7 | Non-conformité RGPD | 3 | 4 | 12 | Réduire |

---

## 5. Programme de conformité réglementaire

### 5.1 Matrice de conformité

| Réglementation | Exigences clés | État actuel | Actions requises | Échéance |
|----------------|---------------|-------------|-----------------|----------|
| **RGPD** | Registre des traitements, AIPD, droits des personnes, notification violations | 70 % conforme | Compléter les AIPD, automatiser les droits | Continu |
| **DORA** | Tests de résilience, gestion des risques IT, surveillance des prestataires | 40 % conforme | Programme de tests, contrats prestataires | Q2 2026 |
| **NIS 2** | Gestion des risques, notification d'incidents, sécurité de la chaîne d'approvisionnement | 50 % conforme | Cartographie prestataires, procédures | Q3 2026 |
| **LPM** | Sécurité des SIIV, notification ANSSI, audits | 60 % conforme | Audit SIIV, homologation | Q2 2026 |
| **ACPR** | Contrôle interne, continuité d'activité, sécurité IT | 65 % conforme | Renforcer PCA, reporting | Continu |

### 5.2 Veille réglementaire

| Activité | Responsable | Fréquence |
|----------|------------|-----------|
| Veille légale et réglementaire | Dir. Conformité | Continue |
| Analyse d'impact des nouvelles réglementations | Comité GRC | Ad hoc |
| Mise à jour de la matrice de conformité | Dir. Conformité | Trimestrielle |
| Rapport de conformité au COMEX | Dir. Conformité + DPO | Trimestrielle |

---

## 6. Contrôles de sécurité

### 6.1 Cadre de contrôles

Les contrôles sont organisés selon les 5 fonctions du cadre NIST CSF 2.0 :

#### IDENTIFIER (ID)

| # | Contrôle | Type | Responsable | Fréquence |
|---|----------|------|-------------|-----------|
| ID-1 | Inventaire des actifs et classification | Préventif | DSI | Continue |
| ID-2 | Analyse de risques EBIOS RM | Préventif | Dir. Risques | Annuelle + ad hoc |
| ID-3 | Cartographie des flux de données | Préventif | Architecte sécurité | Semestrielle |
| ID-4 | Évaluation des prestataires | Préventif | Dir. Conformité | Annuelle |

#### PROTÉGER (PR)

| # | Contrôle | Type | Responsable | Fréquence |
|---|----------|------|-------------|-----------|
| PR-1 | Gestion des identités et accès (IAM) | Préventif | DSI | Continue |
| PR-2 | MFA sur tous les accès sensibles | Préventif | DSI | Continue |
| PR-3 | Chiffrement des données (repos + transit) | Préventif | Architecte sécurité | Continue |
| PR-4 | Gestion des correctifs | Préventif | DSI | Mensuelle |
| PR-5 | Formation et sensibilisation | Préventif | RSSI + RH | Trimestrielle |
| PR-6 | Segmentation réseau | Préventif | DSI | Continue |

#### DÉTECTER (DE)

| # | Contrôle | Type | Responsable | Fréquence |
|---|----------|------|-------------|-----------|
| DE-1 | SOC 24/7 avec SIEM | Détectif | SOC Manager | Continue |
| DE-2 | EDR/XDR sur tous les endpoints | Détectif | SOC Manager | Continue |
| DE-3 | Scan de vulnérabilités | Détectif | Ingénieurs sécurité | Mensuelle |
| DE-4 | Tests d'intrusion | Détectif | Prestataire PASSI | Annuelle |
| DE-5 | Surveillance des fuites de données (Dark Web) | Détectif | Threat Intelligence | Continue |

#### RÉPONDRE (RS)

| # | Contrôle | Type | Responsable | Fréquence |
|---|----------|------|-------------|-----------|
| RS-1 | Procédure de réponse aux incidents | Correctif | RSSI | Ad hoc |
| RS-2 | Exercices de simulation de crise | Correctif | RSSI + Direction | Semestrielle |
| RS-3 | Communication de crise | Correctif | Direction Communication | Ad hoc |
| RS-4 | Analyse forensique | Correctif | SOC / Prestataire | Ad hoc |

#### RÉCUPÉRER (RC)

| # | Contrôle | Type | Responsable | Fréquence |
|---|----------|------|-------------|-----------|
| RC-1 | PCA (Plan de Continuité d'Activité) | Correctif | DSI + Métiers | Continue |
| RC-2 | PRA (Plan de Reprise d'Activité) | Correctif | DSI | Continue |
| RC-3 | Sauvegardes 3-2-1 + tests de restauration | Correctif | DSI | Mensuelle |
| RC-4 | Tests de bascule datacenter | Correctif | DSI | Annuelle |

---

## 7. Indicateurs de performance (KPI/KRI)

### 7.1 KPI — Indicateurs de performance

| # | Indicateur | Cible | Fréquence de mesure | Responsable |
|---|-----------|-------|--------------------|--------------| 
| KPI-1 | Taux de conformité réglementaire global | ≥ 90 % | Trimestrielle | Dir. Conformité |
| KPI-2 | Taux de disponibilité des services critiques | ≥ 99,9 % | Mensuelle | DSI |
| KPI-3 | Taux de correctifs critiques appliqués sous 30 jours | ≥ 95 % | Mensuelle | DSI |
| KPI-4 | Taux de participation aux formations sécurité | 100 % | Trimestrielle | RSSI + RH |
| KPI-5 | Délai moyen de résolution des incidents (MTTR) | < 4 heures (critique) | Mensuelle | SOC Manager |
| KPI-6 | Nombre de non-conformités audit non résolues | 0 (critiques) | Trimestrielle | Dir. Conformité |
| KPI-7 | Taux de réussite des tests PRA | 100 % | Annuelle | DSI |
| KPI-8 | Taux de couverture de l'inventaire des actifs | 100 % | Semestrielle | DSI |

### 7.2 KRI — Indicateurs de risques

| # | Indicateur | Seuil d'alerte | Seuil critique | Fréquence | Responsable |
|---|-----------|---------------|---------------|-----------|-------------|
| KRI-1 | Nombre de vulnérabilités critiques non corrigées | > 5 | > 10 | Hebdomadaire | Ingénieurs sécurité |
| KRI-2 | Nombre d'incidents de sécurité par mois | > 10 | > 25 | Mensuelle | SOC Manager |
| KRI-3 | Délai moyen de détection (MTTD) | > 1 h | > 4 h | Mensuelle | SOC Manager |
| KRI-4 | Nombre de tentatives de phishing réussies | > 5 % | > 15 % | Trimestrielle | RSSI |
| KRI-5 | Nombre de comptes à privilèges non revus | > 0 | > 5 | Trimestrielle | DSI |
| KRI-6 | Taux de prestataires non évalués | > 10 % | > 25 % | Semestrielle | Dir. Conformité |

### 7.3 Tableau de bord GRC

| Vue | Destinataire | Fréquence | Contenu |
|-----|-------------|-----------|---------|
| Tableau de bord stratégique | COMEX | Trimestrielle | KPI/KRI consolidés, budget, risques majeurs |
| Tableau de bord tactique | Comité GRC | Mensuelle | Détail des KPI/KRI, plans d'actions |
| Tableau de bord opérationnel | Équipes sécurité | Hebdomadaire | Incidents, vulnérabilités, alertes |

---

## 8. Feuille de route et planning

### Phase 1 : Fondations (Q1 2026 — Mois 1-3)

| Action | Livrable | Responsable |
|--------|---------|-------------|
| Validation du programme GRC par le COMEX | Programme approuvé | RSSI + Dir. Conformité |
| Constitution de l'équipe GRC | Recrutements effectués | RH + RSSI |
| Cartographie des risques initiale (EBIOS RM) | Cartographie des risques | Dir. Risques |
| Inventaire exhaustif des actifs | Registre des actifs | DSI |
| Audit de conformité initial (RGPD, DORA, NIS 2) | Rapport d'audit | Dir. Conformité |

### Phase 2 : Déploiement (Q2-Q3 2026 — Mois 4-9)

| Action | Livrable | Responsable |
|--------|---------|-------------|
| Déploiement SIEM et SOC 24/7 | SOC opérationnel | SOC Manager |
| Mise en place IAM et MFA | Solution IAM déployée | DSI |
| Rédaction et déploiement des politiques de sécurité | PSSI + politiques spécifiques | RSSI |
| Programme de sensibilisation (phase 1) | Formations déployées | RSSI + RH |
| Mise en conformité DORA (tests de résilience) | Rapport de tests | DSI + RSSI |
| AIPD et registre des traitements complet | Documents RGPD | DPO |

### Phase 3 : Optimisation (Q4 2026 — Mois 10-12)

| Action | Livrable | Responsable |
|--------|---------|-------------|
| Audit interne de vérification | Rapport d'audit | Auditeurs internes |
| Préparation certification ISO 27001 | Dossier de certification | RSSI |
| Tests PCA/PRA et exercice de crise | Rapports de test | DSI + RSSI |
| Tableau de bord GRC automatisé | Dashboard opérationnel | Dir. Risques |
| Bilan annuel et ajustement du programme | Rapport annuel | Comité GRC |

---

## 9. Budget et ressources

### 9.1 Budget annuel estimé

| Poste | Budget estimé | % du total |
|-------|--------------|-----------|
| Ressources humaines (équipe GRC : 8 ETP) | 640 000 € | 40 % |
| Solutions techniques (SIEM, EDR, IAM, DLP) | 400 000 € | 25 % |
| Audits et tests d'intrusion externes | 160 000 € | 10 % |
| Formation et sensibilisation | 80 000 € | 5 % |
| Conseil et accompagnement (cabinets spécialisés) | 160 000 € | 10 % |
| Certification ISO 27001 | 80 000 € | 5 % |
| Divers et imprévus | 80 000 € | 5 % |
| **Total** | **1 600 000 €** | **100 %** |

### 9.2 Retour sur investissement (ROI)

| Élément | Estimation |
|---------|-----------|
| Coût moyen d'une violation de données (secteur financier) | 4,5 M€ |
| Amende RGPD potentielle (4 % CA) | Plusieurs millions € |
| Coût d'indisponibilité (par heure) | 50 000 - 200 000 € |
| **ROI estimé du programme GRC** | **3 à 5 fois l'investissement** |

---

## 10. Conclusion

Le programme GRC de FinanceGuard SA établit un cadre structuré et intégré pour la gouvernance de la sécurité, la gestion des risques et la conformité réglementaire. Il répond aux exigences croissantes du secteur financier (RGPD, DORA, NIS 2) et positionne l'entreprise sur une trajectoire d'amélioration continue.

Les facteurs clés de succès sont :
1. **L'engagement de la direction** : le soutien du COMEX est indispensable
2. **L'approche par les risques** : les investissements sont priorisés selon la criticité
3. **La mesure continue** : les KPI/KRI permettent de piloter et d'ajuster le programme
4. **La culture sécurité** : la sensibilisation de tous les collaborateurs est un pilier du programme

Le suivi trimestriel par le Comité GRC et le reporting au COMEX garantissent le pilotage efficace du programme et l'atteinte des objectifs fixés.

---

**Document approuvé par :**

| Nom | Fonction | Date | Signature |
|-----|----------|------|-----------|
| ________________ | Directeur Général | __/__/2026 | ____________ |
| ________________ | RSSI | __/__/2026 | ____________ |
| ________________ | Directeur Conformité | __/__/2026 | ____________ |
| ________________ | DPO | __/__/2026 | ____________ |


---

# TP 10 — Gestion d'incident et PCA/PRA

## Objectif

Gérer un ransomware.

## Travail demandé

Plan d'urgence, PCA, PRA, communication de crise.

## Livrable

Dossier complet.

---

## Solution

---

# DOSSIER DE GESTION D'INCIDENT RANSOMWARE — PCA/PRA ET COMMUNICATION DE CRISE

**Entreprise :** IndustrieTech SA — Entreprise industrielle (500 employés)  
**Date :** Février 2026  
**Scénario :** Attaque ransomware « BlackCrypt » chiffrant les systèmes de production  
**Classification :** Confidentiel — Diffusion restreinte au comité de crise

---

## PARTIE 1 : PLAN D'URGENCE — RÉPONSE À L'INCIDENT RANSOMWARE

### 1.1 Chronologie de l'incident

| Heure | Événement |
|-------|-----------|
| J0 — 02h15 | Le ransomware BlackCrypt s'exécute via un e-mail de phishing ouvert par un employé la veille |
| J0 — 02h15-05h30 | Le malware se propage latéralement sur le réseau non segmenté, chiffre les fichiers |
| J0 — 06h00 | L'équipe du matin découvre les systèmes inaccessibles, écrans affichant la demande de rançon |
| J0 — 06h15 | Le responsable IT alerte le RSSI |
| J0 — 06h30 | Activation du comité de crise |

### 1.2 Activation du comité de crise

| Rôle | Nom / Fonction | Responsabilités en crise |
|------|---------------|------------------------|
| Directeur de crise | Directeur Général | Décisions stratégiques, communication externe |
| Coordinateur technique | RSSI | Pilotage de la réponse technique |
| Responsable IT | DSI | Exécution des actions techniques |
| Responsable juridique | Directeur Juridique | Obligations légales, CNIL, plainte |
| Responsable communication | Dir. Communication | Communication interne et externe |
| Responsable métier | Dir. Production | Continuité des opérations de production |
| DPO | Délégué à la Protection des Données | Évaluation de l'impact sur les données personnelles |

### 1.3 Procédure de réponse immédiate (0-4 heures)

| # | Action | Responsable | Délai | Statut |
|---|--------|-------------|-------|--------|
| 1 | **Isoler le réseau** : déconnecter le réseau d'Internet, isoler les segments affectés | DSI | Immédiat | ☐ |
| 2 | **Préserver les preuves** : ne PAS redémarrer les machines, capturer les logs, images disque | RSSI | 1 h | ☐ |
| 3 | **Identifier le périmètre** : inventorier les systèmes chiffrés vs. épargnés | DSI + RSSI | 2 h | ☐ |
| 4 | **Identifier le ransomware** : analyser la note de rançon, les extensions de fichiers, les IoC | RSSI | 2 h | ☐ |
| 5 | **Évaluer les sauvegardes** : vérifier l'intégrité des sauvegardes (hors ligne / hors site) | DSI | 2 h | ☐ |
| 6 | **Notifier les autorités** : dépôt de plainte (police/gendarmerie), notification ANSSI | Dir. Juridique | 4 h | ☐ |
| 7 | **Évaluer l'impact données personnelles** : déterminer si notification CNIL requise | DPO | 4 h | ☐ |
| 8 | **Activer le prestataire incident response** : mobiliser le CERT/CSIRT externe | RSSI | 1 h | ☐ |

### 1.4 Décision sur la rançon

| Option | Analyse | Décision recommandée |
|--------|---------|---------------------|
| Payer la rançon | ❌ Aucune garantie de récupération, finance le crime, expose à de futures attaques | **NE PAS PAYER** |
| Restaurer depuis les sauvegardes | ✅ Solution privilégiée si sauvegardes intègres et récentes | **RECOMMANDÉ** |
| Décrypteur disponible | 🔍 Vérifier sur nomoreransom.org si un outil de décryptage existe | Vérifier immédiatement |

### 1.5 Phase de confinement et éradication (4-48 heures)

| # | Action | Responsable | Délai |
|---|--------|-------------|-------|
| 1 | Identifier le vecteur d'infection initial (e-mail de phishing) | RSSI + CERT | 8 h |
| 2 | Bloquer les IoC (adresses IP, domaines, hash) sur le pare-feu et l'EDR | DSI | 4 h |
| 3 | Réinitialiser tous les mots de passe (Active Directory, comptes à privilèges en priorité) | DSI | 8 h |
| 4 | Scanner tous les systèmes non chiffrés pour détecter la présence dormante du malware | RSSI | 24 h |
| 5 | Isoler et reconstruire les systèmes compromis (réinstallation propre) | DSI | 48 h |
| 6 | Analyser les journaux pour déterminer l'étendue de l'exfiltration éventuelle | RSSI + CERT | 48 h |

---

## PARTIE 2 : PLAN DE CONTINUITÉ D'ACTIVITÉ (PCA)

### 2.1 Objectifs du PCA

| Objectif | Description |
|----------|-------------|
| Maintenir les activités critiques | Assurer la continuité de la production et des services essentiels |
| Protéger les employés | Garantir la sécurité et l'information du personnel |
| Limiter les pertes financières | Minimiser l'impact économique de l'interruption |
| Préserver la relation clients | Maintenir la communication et les engagements contractuels |

### 2.2 Classification des processus métier

| Processus | Criticité | RTO (Recovery Time Objective) | RPO (Recovery Point Objective) | Mode dégradé |
|-----------|-----------|------|------|--------------|
| Production industrielle | Critique | 24 h | 4 h | Basculement en mode manuel |
| Système ERP (commandes, facturation) | Critique | 8 h | 1 h | Saisie manuelle sur formulaires papier |
| Messagerie et communication | Élevée | 4 h | 1 h | Téléphones mobiles personnels, messagerie alternative |
| Gestion des stocks | Élevée | 24 h | 4 h | Inventaire papier |
| Paie et RH | Moyenne | 72 h | 24 h | Report de traitement |
| Site web corporate | Faible | 1 semaine | 24 h | Page d'information minimale |

### 2.3 Mesures de continuité pendant l'incident

| Domaine | Mesure de continuité | Responsable |
|---------|---------------------|-------------|
| Production | Passage en mode de commande manuelle des automates (si non chiffrés) | Dir. Production |
| Commandes clients | Réception et traitement des commandes par téléphone et e-mail alternatif | Dir. Commercial |
| Communication interne | Canal de communication de crise via messagerie Signal (groupe pré-configuré) | Dir. Communication |
| Communication externe | Ligne téléphonique dédiée pour les clients, communiqué de presse | Dir. Communication |
| Paie | Versement des salaires par virement manuel si nécessaire | Dir. RH + DAF |
| Logistique | Coordination par téléphone avec les transporteurs | Dir. Logistique |

### 2.4 Ressources nécessaires pour le PCA

| Ressource | Description | Statut |
|-----------|-------------|--------|
| Salle de crise | Salle de réunion dédiée avec téléphone, accès Internet indépendant | ☐ Activée |
| Postes de travail de secours | 20 laptops pré-configurés stockés hors du réseau principal | ☐ Déployés |
| Réseau de secours | Connexion 4G/5G indépendante pour les communications critiques | ☐ Activé |
| Documentation papier | Procédures d'urgence, listes de contacts, plans réseau | ☐ Distribuée |
| Prestataire IT externe | Contrat d'assistance prioritaire (SLA 4 h) | ☐ Contacté |

---

## PARTIE 3 : PLAN DE REPRISE D'ACTIVITÉ (PRA)

### 3.1 Stratégie de reprise

| Phase | Description | Durée estimée | Priorité |
|-------|-------------|--------------|----------|
| Phase 1 | Reprise de l'infrastructure de base (Active Directory, DNS, DHCP) | 4-8 h | Critique |
| Phase 2 | Reprise des systèmes de production (SCADA, automates) | 8-24 h | Critique |
| Phase 3 | Reprise de l'ERP et des applications métier | 24-48 h | Élevée |
| Phase 4 | Reprise de la messagerie et des outils collaboratifs | 24-48 h | Élevée |
| Phase 5 | Reprise des systèmes secondaires (site web, outils internes) | 48-72 h | Moyenne |
| Phase 6 | Retour à la normale complet | 1-2 semaines | Standard |

### 3.2 Procédure de restauration

| # | Étape | Actions | Responsable | Critères de validation |
|---|-------|---------|-------------|----------------------|
| 1 | Préparer l'infrastructure propre | Réinstaller les serveurs depuis des images propres, reconfigurer le réseau avec segmentation | DSI | Serveurs opérationnels, réseau segmenté |
| 2 | Restaurer Active Directory | Restaurer depuis la sauvegarde hors site la plus récente validée | DSI | Authentification fonctionnelle |
| 3 | Vérifier les sauvegardes | Scanner les sauvegardes pour s'assurer qu'elles ne contiennent pas le ransomware | RSSI | Sauvegardes certifiées propres |
| 4 | Restaurer les systèmes critiques | ERP, systèmes de production, base de données | DSI | Applications fonctionnelles |
| 5 | Tester les systèmes restaurés | Tests fonctionnels complets avant remise en production | DSI + Métiers | Tests validés |
| 6 | Reconnecter progressivement | Rétablir la connectivité Internet et les accès distants | DSI + RSSI | Monitoring actif, pas d'anomalie |
| 7 | Déployer les correctifs de sécurité | Patcher tous les systèmes, déployer EDR, renforcer MFA | DSI + RSSI | 100 % des systèmes patchés |

### 3.3 Architecture de sauvegarde cible (règle 3-2-1-1)

```
┌──────────────────────────────────────────────────┐
│            Politique de sauvegarde 3-2-1-1        │
│                                                    │
│  3 copies des données                              │
│  │                                                 │
│  ├── Copie 1 : Production (données en ligne)       │
│  │                                                 │
│  ├── Copie 2 : Sauvegarde locale (NAS dédié,       │
│  │             réseau isolé, chiffrée)              │
│  │                                                 │
│  ├── Copie 3 : Sauvegarde hors site                │
│  │             (datacenter distant ou cloud         │
│  │             souverain, chiffrée)                 │
│  │                                                 │
│  └── 1 copie immuable (air-gap)                    │
│       (bandes LTO stockées en coffre-fort,          │
│       non connectées au réseau)                     │
│                                                    │
│  2 supports différents (disque + bande)             │
│  1 copie hors site                                  │
│  1 copie immuable                                   │
└──────────────────────────────────────────────────┘
```

### 3.4 Tests du PRA

| Test | Fréquence | Description | Critère de succès |
|------|-----------|-------------|-------------------|
| Test de restauration unitaire | Mensuel | Restauration d'un fichier/base de données | Données restaurées avec intégrité |
| Test de restauration serveur | Trimestriel | Restauration complète d'un serveur critique | Serveur opérationnel dans le RTO |
| Exercice de bascule | Annuel | Bascule complète vers le site de secours | Reprise des services dans le RTO global |
| Exercice de crise | Semestriel | Simulation de scénario d'attaque de bout en bout | Comité de crise opérationnel, PCA activé |

---

## PARTIE 4 : COMMUNICATION DE CRISE

### 4.1 Principes de communication

| Principe | Description |
|----------|-------------|
| **Transparence** | Communiquer de manière honnête et factuelle |
| **Rapidité** | Première communication dans les 2 heures suivant l'activation de la crise |
| **Cohérence** | Un seul porte-parole, messages validés par le comité de crise |
| **Empathie** | Reconnaître l'impact sur les personnes concernées |
| **Régularité** | Points d'information réguliers (toutes les 4 à 8 heures en phase aiguë) |

### 4.2 Plan de communication

#### Communication interne

| Destinataire | Canal | Message clé | Timing |
|-------------|-------|-------------|--------|
| Tous les employés | Signal (groupe crise) + affichage | « Incident de sécurité en cours. Déconnectez vos postes. Ne branchez aucune clé USB. Attendez les instructions. » | J0 + 1 h |
| Managers | Conférence téléphonique | Briefing détaillé, instructions pour leurs équipes, mode dégradé | J0 + 2 h |
| Tous les employés | E-mail alternatif + réunion | Point de situation, consignes de travail en mode dégradé | J0 + 4 h |
| Tous les employés | Mise à jour quotidienne | Avancement de la reprise, actions attendues | Quotidien |

#### Communication externe

| Destinataire | Canal | Message clé | Timing |
|-------------|-------|-------------|--------|
| Clients majeurs | Appel téléphonique (Dir. Commercial) | « Incident technique en cours, vos données sont protégées, délais possibles sur les livraisons » | J0 + 4 h |
| Ensemble des clients | E-mail + site web | Communiqué factuel, mesures prises, point de contact dédié | J0 + 8 h |
| Fournisseurs | E-mail + téléphone | Information sur les perturbations possibles des commandes | J0 + 8 h |
| Presse (si nécessaire) | Communiqué de presse | Déclaration factuelle, pas de spéculation, renvoi vers le porte-parole | J0 + 24 h |
| CNIL | Formulaire en ligne | Notification de violation de données si données personnelles affectées | < 72 h (Art. 33 RGPD) |
| ANSSI | Formulaire de signalement | Déclaration d'incident de sécurité | < 24 h |
| Assureur cyber | Appel + e-mail | Déclaration de sinistre, demande d'activation de la couverture | J0 + 4 h |

### 4.3 Modèle de communiqué externe

> **IndustrieTech SA — Communiqué du [date]**
> 
> IndustrieTech SA a été victime d'un incident de sécurité informatique le [date]. Dès la détection de l'incident, l'entreprise a immédiatement activé son plan de réponse et mobilisé des experts en cybersécurité.
> 
> **Ce que nous savons :** Un logiciel malveillant a affecté une partie de nos systèmes informatiques. Nos équipes de production ont basculé en mode de fonctionnement alternatif pour maintenir nos engagements.
> 
> **Ce que nous faisons :** Nous travaillons avec des experts en cybersécurité et les autorités compétentes pour analyser l'incident, sécuriser nos systèmes et rétablir un fonctionnement normal dans les meilleurs délais.
> 
> **Impact sur nos clients :** Des retards de livraison de [X] jours sont possibles. Nous contacterons individuellement chaque client concerné.
> 
> **Point de contact :** Pour toute question, contactez notre ligne dédiée au [numéro] ou par e-mail à [adresse].
> 
> Nous nous engageons à communiquer de manière transparente tout au long de cet événement.

### 4.4 Post-incident : retour d'expérience (RETEX)

| Activité | Délai | Responsable | Livrable |
|----------|-------|-------------|----------|
| Réunion RETEX technique | J+7 | RSSI | Rapport technique d'incident |
| Réunion RETEX managériale | J+14 | Dir. Général | Rapport de crise |
| Plan d'amélioration | J+30 | RSSI + DSI | Plan d'actions correctives |
| Communication finale aux parties prenantes | J+30 | Dir. Communication | Communiqué final |
| Audit de sécurité post-incident | J+60 | Prestataire externe | Rapport d'audit |

### 4.5 Améliorations post-incident recommandées

| # | Amélioration | Priorité | Budget estimé |
|---|-------------|----------|---------------|
| 1 | Segmentation réseau (VLANs, micro-segmentation) | Critique | 30 000 € |
| 2 | Déploiement EDR/XDR sur tous les endpoints | Critique | 50 000 €/an |
| 3 | MFA sur tous les accès (utilisateurs + admin) | Critique | 15 000 €/an |
| 4 | SOC externalisé 24/7 | Élevée | 80 000 €/an |
| 5 | Solution anti-phishing avancée | Élevée | 20 000 €/an |
| 6 | Formation cybersécurité de tout le personnel | Élevée | 15 000 €/an |
| 7 | Sauvegardes immuables (3-2-1-1) | Critique | 25 000 € |
| 8 | Assurance cyber | Élevée | 30 000 €/an |

---

## CONCLUSION

Ce dossier complet de gestion d'incident ransomware couvre les quatre dimensions essentielles de la réponse :

1. **Le plan d'urgence** assure une réponse structurée et rapide dans les premières heures critiques
2. **Le PCA** garantit la continuité des activités essentielles pendant la crise
3. **Le PRA** définit la stratégie et les procédures de reprise complète des systèmes
4. **La communication de crise** protège la réputation et maintient la confiance des parties prenantes

La préparation est la clé : les exercices réguliers de simulation, les tests de sauvegardes et la formation du personnel sont indispensables pour que ces plans soient efficaces le jour où l'incident survient.

---

**Document approuvé par le comité de crise :**

| Nom | Fonction | Date | Signature |
|-----|----------|------|-----------|
| ________________ | Directeur Général | __/__/2026 | ____________ |
| ________________ | RSSI | __/__/2026 | ____________ |
| ________________ | DSI | __/__/2026 | ____________ |
| ________________ | Dir. Communication | __/__/2026 | ____________ |


---

