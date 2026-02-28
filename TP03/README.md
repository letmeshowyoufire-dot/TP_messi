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
