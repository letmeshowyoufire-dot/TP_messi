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
