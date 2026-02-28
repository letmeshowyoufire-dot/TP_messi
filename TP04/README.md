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
