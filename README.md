<div align="center">

# 🚀 TP12 - Software Supply Chain
### Harbor, SBOM, Cosign & SLSA

[![Harbor](https://img.shields.io/badge/Harbor-v2.11.0-blue?style=for-the-badge&logo=docker)](https://goharbor.io/)
[![Cosign](https://img.shields.io/badge/Cosign-v2.4.3-purple?style=for-the-badge&logo=linux)](https://docs.sigstore.dev/cosign/overview/)
[![Syft](https://img.shields.io/badge/Syft-SBOM-orange?style=for-the-badge)](https://github.com/anchore/syft)
[![Grype](https://img.shields.io/badge/Grype-Scan-red?style=for-the-badge)](https://github.com/anchore/grype)

📄 **[Télécharger le rapport complet (PDF)](rapport_tp12.pdf)**

</div>

---

## 📸 Captures d'écran

Toutes les captures sont disponibles dans le dossier [`captures/`](captures/).

### 🛠️ Partie 1 : Installer Harbor

#### 1. Extraction de Harbor
![01](captures/01_extract_harbor.png)

#### 2. Installation réussie
![02](captures/02_harbor_install.png)

#### 3. Vérification des conteneurs
![03](captures/03_docker_compose_ps.png)

#### 4. Configuration DNS (Harbor)
![04](captures/04_dns_harbor.png)

#### 5. Configuration DNS (Lab)
![05](captures/05_dns_lab.png)

#### 6. Configuration Docker
![06](captures/06_daemon_json.png)

#### 7. Test de connexion (Harbor)
![07](captures/07_curl_harbor.png)

#### 8. Test de connexion (Lab)
![08](captures/08_curl_lab.png)

#### 9. Interface Web Harbor
![09](captures/09_harbor_ui.png)

### 🛡️ Partie 2 : Projets, RBAC, scan et rétention

#### 10. Création du projet `devsecops`
![10](captures/10_create_project.png)

#### 11. Création des utilisateurs
![11](captures/11_create_users.png)

#### 12. Ajout des membres
![12](captures/12_add_members.png)

#### 13. Création du robot account
![13](captures/13_create_robot.png)

#### 14. Tag de l'image
![14](captures/14_docker_tag.png)

#### 15. Connexion avec le robot
![15](captures/15_docker_login.png)

#### 16. Push de l'image
![16](captures/16_docker_push.png)

#### 17. Vérification dans Harbor
![17](captures/17_harbor_repo.png)

#### 18. Test RBAC (refus pour audit1)
![18](captures/18_rbac_denied.png)

#### 19. Activation du scan Trivy
![19](captures/19_scan_config.png)

#### 20. Règle de rétention
![20](captures/20_retention_rule.png)

#### 21. Dry Run de la rétention
![21](captures/21_dry_run.png)

#### 22. Immutabilité des tags
![22](captures/22_immutability.png)

#### 23. Push d'une image vulnérable
![23](captures/23_push_vuln.png)

#### 24. Rapport de scan Trivy (1453 CVE)
![24](captures/24_scan_trivy.png)

### 📦 Partie 3 : SBOM avec Syft et Grype

#### 25. Génération du SBOM
![25](captures/25_syft.png)

#### 26. Analyse du SBOM (154 paquets)
![26](captures/26_sbom_analysis.png)

#### 27. Analyse avec Grype
![27](captures/27_grype.png)

### 🔏 Partie 4 : Signer et vérifier avec Cosign

#### 28. Installation de Cosign
![28](captures/28_cosign_install.png)

#### 29. Génération de la paire de clés
![29](captures/29_key_pair.png)

#### 30. Récupération du digest
![30](captures/30_digest.png)

#### 31. Signature de l'image
![31](captures/31_cosign_sign.png)

#### 32. Vérification de la signature
![32](captures/32_cosign_verify.png)

#### 33. Attestation du SBOM
![33](captures/33_cosign_attest.png)

### 🔑 Partie 5 : Keyless et provenance dans GitHub Actions

#### 34. Création du tag `v1.0.0`
![34](captures/34_github_tag.png)

#### 35. Workflow GitHub Actions
![35](captures/35_github_actions.png)

#### 36. Vérification Keyless
![36](captures/36_cosign_keyless.png)

#### 37. Vérification de l'attestation
![37](captures/37_gh_attestation.png)

---

## 🛠️ Résumé des actions

| Étape | Outil | Action |
| :--- | :--- | :--- |
| **Registre** | Harbor | Installation, projets, RBAC, robot accounts, scan Trivy, rétention, immutabilité. |
| **SBOM** | Syft | Génération de l'inventaire (SPDX et CycloneDX). |
| **Scan SBOM** | Grype | Analyse des vulnérabilités à partir du SBOM. |
| **Signature** | Cosign | Signature de l'image avec une paire de clés. |
| **Attestation** | Cosign | Attestation du SBOM (in-toto). |
| **Keyless** | GitHub Actions | Signature OIDC sans clé privée. |
| **Provenance** | GitHub Actions | Attestation SLSA de provenance. |

---

<div align="center">
  <b>Fait avec ❤️ par Arij Belaid</b>
</div>
