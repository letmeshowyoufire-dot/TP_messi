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
