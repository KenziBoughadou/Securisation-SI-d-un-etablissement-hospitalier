# Sécurisation SI d’un établissement hospitalier

Bienvenue sur ce dépôt dédié à un projet complet de sécurisation du système d'information (SI) d’un établissement hospitalier, réalisé dans le cadre de mon MSc Cybersécurité & Management.

---

## 🏥 Contexte du projet

Les hôpitaux sont aujourd’hui des cibles privilégiées des cyberattaques : données médicales, continuité des soins, conformité réglementaire… La moindre faille peut avoir des conséquences humaines et économiques majeures.

Ce projet, mené avec Hugo Grillet, visait à :
- Auditer en profondeur un SI hospitalier existant,
- Formaliser les besoins de sécurité métiers et réglementaires (RGPD, HDS, ISO 27001/27799),
- Définir et documenter une architecture technique résiliente,
- Élaborer les procédures clés (PCA, PRA, PSSI) et les plans d’amélioration continue,
- Mettre en œuvre une véritable gouvernance SSI à l’échelle de l’établissement.

---

## 🔍 Démarche & Audit technique

### 1. Cartographie & état des lieux

- **Inventaire matériel et logiciel** : serveurs (Windows Server 2022, Debian), postes clients, équipements réseau.
- **Pare-feu** : OPNSense déployé pour la segmentation VLAN, filtrage, VPN, IDS/IPS.
- **Supervision** : Zabbix (monitoring infra, alerting) & Wazuh (SIEM, détection d’incidents, corrélation de logs).
- **Gestion des accès** : Active Directory, politiques de comptes et de groupes, MFA envisagé pour les accès sensibles.
- **Sauvegarde & PRA** : NAS local + réplication cloud certifiée HDS, procédures de restauration testées.

### 2. Analyse des risques

- **Vulnérabilités identifiées** : serveurs obsolètes, patch management irrégulier, MFA absent, segmentation incomplète, mots de passe faibles, faible sensibilisation du personnel.
- **Menaces principales** : ransomware (impact métier), sinistre physique, compromission externe, erreurs humaines.
- **Conformité** : cartographie des écarts RGPD, obligations HDS, exigences ISO 27001/27799.

---

## 🛡️ Architecture technique proposée

### Segmentation et isolation

- **VLAN par usage** (médecins, administratifs, patients, supervision)
- **DMZ** pour les services exposés
- **Pare-feu OPNSense** pour le filtrage, le NAT, l’IDS/IPS (Snort/Suricata)
- **Contrôle des flux inter-VLAN** strict

### Systèmes & sécurité

- **Active Directory** redondé (2 contrôleurs), GPO adaptées, gestion fine des droits
- **Serveurs Linux** dédiés pour la supervision (Zabbix, Wazuh) et les bases de données médicales
- **Sauvegardes automatisées** : NAS, cloud certifié HDS, restauration testée tous les trimestres

### Supervision & détection

- **Zabbix** : monitoring de la disponibilité, alertes mails en cas de défaillance critique
- **Wazuh** : collecte et corrélation de logs, alertes SIEM, détection d’événements suspects, reporting régulier

### Procédures & gouvernance

- **Plan de Continuité d’Activité (PCA)** : maintien des services critiques (accès DMP, laboratoire, communication interne)
- **Plan de Reprise d’Activité (PRA)** : restauration priorisée, tests réguliers, documentation pas-à-pas
- **Politique de Sécurité du SI (PSSI)** : règles d’accès, gestion des incidents, formation/sensibilisation du personnel, sanctions, revue annuelle

---

## 📄 Livrables du projet

- [Cahier des charges (PDF)](https://github.com/KenziBoughadou/Securisation-SI-d-un-etablissement-hospitalier/raw/main/ProjetSSI%20-%20Cahier%20des%20charges.pdf)  
  > Audit initial, cartographie, identification des besoins métiers, techniques et réglementaires.

- [Plan de Continuité et de Reprise d’Activité – PCA/PRA (PDF)](https://github.com/KenziBoughadou/Securisation-SI-d-un-etablissement-hospitalier/raw/main/ProjetSSI%20-%20PCA%20PRA%20(1).pd

