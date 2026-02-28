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
