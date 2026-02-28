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
