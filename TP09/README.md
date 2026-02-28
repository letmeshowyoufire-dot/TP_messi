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
