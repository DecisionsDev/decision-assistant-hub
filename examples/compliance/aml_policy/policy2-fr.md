Here is a policy in French. Keep in mind that we want to extract a decision service expressed in English from it.

# ACME CORP – Politique de Lutte contre le Blanchiment de Capitaux et le Financement du Terrorisme (France)

Cette 

---

## 1. Objet
Cette politique définit les mesures mises en place par Acme Corp pour détecter et prévenir le blanchiment de capitaux et le financement du terrorisme, conformément à la réglementation française et européenne. Elle s’applique à toutes les entités, tous les canaux et tous les types de clients.

---

## 2. Classification du risque client

| Niveau de risque  | Critères |
|-------------------|----------|
| **Standard** | Client avec identité vérifiée (KYC complet), activité domestique et transactions prévisibles cohérentes avec son profil. |
| **Élevé** | Client opérant dans un secteur à risque, effectuant fréquemment des virements internationaux, ayant un KYC incomplet ou présentant un comportement transactionnel inhabituel. |

L’équipe Conformité peut modifier ce classement en fonction des alertes, des résultats d’enquête ou de son jugement professionnel.

---

## 3. Données requises

### 3.1 Données client
- Identifiant client unique
- Type (personne physique ou personne morale)
- Statut KYC
- Statut PEP (y compris proches et associés)
- Secteur d’activité et indicateur de secteur à risque
- Niveau de risque
- Pays de résidence
- Date d’entrée en relation

### 3.2 Données compte
- Identifiant de compte unique
- Identifiant client associé
- Devise
- Statut du compte
- Date d’ouverture

### 3.3 Données transaction
- Identifiant de transaction
- Identifiant de compte associé
- Date et heure
- Sens (entrant/sortant)
- Montant et devise (plus montant converti en EUR)
- Moyen de paiement
- Canal
- Pays d’origine, de destination, pays de la banque du contrepartie
- Code objet
- Indicateur de récurrence

### 3.4 Listes de référence
- Liste de sanctions de l’UE (pays et entités)
- Liste des pays à haut risque du GAFI
- Liste des pays sous embargo

---

## 4. Surveillance des opérations

Acme Corp surveille toutes les transactions clients en temps réel et via des traitements périodiques afin d’identifier toute activité potentiellement liée au blanchiment ou au financement du terrorisme.

Tous les montants sont convertis en EUR sur la base du taux de change du jour de l’opération pour l’application des seuils. La surveillance couvre tous les moyens de paiement (virements, cartes, espèces, chèques, crypto-actifs, etc.) et tous les canaux (agence, en ligne, mobile, DAB, API).

Les situations suivantes nécessitent un examen et éventuellement une escalade :

| Scénario | Description | Action minimale |
|----------|-------------|-----------------|
| **Transactions importantes** | Toute opération ≥ 10 000 € | Revue manuelle |
| **Espèces par client occasionnel** | Opération en espèces ≥ 1 000 € par un client sans relation suivie | Alerte et vérification d’identité |
| **Structuration** | ≥ 3 opérations en 7 jours juste en dessous des seuils déclaratifs (9 000–9 999 € ou 2 900–2 999 €) avec des totaux au-dessus des seuils | Revue manuelle |
| **Mouvement rapide de fonds** | Opération entrante ≥ 5 000 € suivie d’opérations sortantes totalisant ≥ 80 % du montant entrant sous 48h sur le même compte | Revue manuelle |
| **Pays/entité sous sanctions** | Opération impliquant un pays ou une entité sur liste de sanctions UE | Blocage si légalement autorisé ; escalade immédiate |
| **Pays à haut risque** | Opération impliquant un pays à haut risque selon le GAFI | Vigilance renforcée et revue manuelle |
| **Activité sur compte dormant** | Compte inactif ≥ 180 jours avec opération ≥ 1 000 € | Revue manuelle |
| **Pic d’activité** | Volume des 7 derniers jours ≥ 3× la moyenne hebdomadaire des 8 dernières semaines | Revue manuelle |
| **Canal/moyen inhabituel** | Opération ≥ 2 000 € utilisant un moyen ou canal inhabituel pour le client | Revue manuelle |
| **Contrepartie à haut risque** | Opération ≥ 1 000 € avec contrepartie dans un secteur à risque | Revue manuelle |

Une liste blanche d’opérations récurrentes validées (ex. salaires, loyers) peut permettre de supprimer des alertes si tous les paramètres correspondent et si l’inscription sur la liste est encore valide. Chaque inscription a une date d’expiration et fait l’objet d’un contrôle périodique.

---

## 5. Gestion des alertes

- Les alertes liées aux sanctions ou embargos sont considérées comme **critiques** et traitées immédiatement.
- Les alertes impliquant des pays à haut risque ou des schémas de structuration sont considérées comme **à haut risque**.
- Les alertes sur moyens ou contreparties inhabituels sont généralement de **risque moyen**.
- Toutes les alertes, y compris celles supprimées via liste blanche, sont journalisées avec les détails du déclencheur et l’identité du réviseur.
- Les alertes supprimées doivent mentionner l’entrée de liste blanche utilisée et sa date d’expiration.

---

## 6. Escalade et déclaration

En cas de suspicion confirmée après examen :  
1. L’équipe Conformité crée ou met à jour un dossier d’enquête.  
2. Une Déclaration de soupçon est transmise à TRACFIN dans les 24 heures ouvrées.  
3. Des mesures complémentaires peuvent inclure la restriction du compte, son blocage, ou l’application d’une vigilance renforcée.

---

## 7. Conservation des données

- Les données KYC, les enregistrements de transactions et les journaux de gestion des alertes sont conservés pendant 5 ans après la fin de la relation d’affaires.  
- Les enregistrements doivent être facilement accessibles pour tout audit réglementaire.

---

## 8. Gouvernance et formation

- Formation annuelle obligatoire sur la LCB-FT pour le personnel concerné.  
- Comité Conformité trimestriel pour examiner les résultats de la surveillance, les risques émergents et l’efficacité des règles.

---
