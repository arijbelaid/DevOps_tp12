# TP12 - Software Supply Chain (Harbor, SBOM, Cosign, SLSA)

Ce dépôt contient le rendu du TP12 portant sur la sécurisation de la chaîne d'approvisionnement logicielle.

## 📸 Captures d'écran

Toutes les captures sont disponibles dans le dossier [`captures/`](captures/).

### Partie 1 : Installer Harbor
1. **Extraction de Harbor** : `01_extract_harbor.png`
2. **Installation réussie** : `02_harbor_install.png`
3. **Vérification des conteneurs** : `03_docker_compose_ps.png`
4. **Configuration DNS (Harbor)** : `04_dns_harbor.png`
5. **Configuration DNS (Lab)** : `05_dns_lab.png`
6. **Configuration Docker (insecure-registries)** : `06_daemon_json.png`
7. **Test de connexion (Harbor)** : `07_curl_harbor.png`
8. **Test de connexion (Lab)** : `08_curl_lab.png`
9. **Interface Web Harbor** : `09_harbor_ui.png`

### Partie 2 : Projets, RBAC, scan et rétention
10. **Création du projet `devsecops`** : `10_create_project.png`
11. **Création des utilisateurs** : `11_create_users.png`
12. **Ajout des membres** : `12_add_members.png`
13. **Création du robot account** : `13_create_robot.png`
14. **Tag de l'image** : `14_docker_tag.png`
15. **Connexion avec le robot** : `15_docker_login.png`
16. **Push de l'image** : `16_docker_push.png`
17. **Vérification dans Harbor** : `17_harbor_repo.png`
18. **Test RBAC (refus pour audit1)** : `18_rbac_denied.png`
19. **Activation du scan Trivy** : `19_scan_config.png`
20. **Règle de rétention** : `20_retention_rule.png`
21. **Dry Run de la rétention** : `21_dry_run.png`
22. **Immutabilité des tags** : `22_immutability.png`
23. **Push d'une image vulnérable** : `23_push_vuln.png`
24. **Rapport de scan Trivy** : `24_scan_trivy.png`

### Partie 3 : SBOM avec Syft et Grype
25. **Génération du SBOM** : `25_syft.png`
26. **Analyse du SBOM** : `26_sbom_analysis.png`
27. **Analyse avec Grype** : `27_grype.png`

### Partie 4 : Signer et vérifier avec Cosign
28. **Installation de Cosign** : `28_cosign_install.png`
29. **Génération de la paire de clés** : `29_key_pair.png`
30. **Récupération du digest** : `30_digest.png`
31. **Signature de l'image** : `31_cosign_sign.png`
32. **Vérification de la signature** : `32_cosign_verify.png`
33. **Attestation du SBOM** : `33_cosign_attest.png`

### Partie 5 : Keyless et provenance dans GitHub Actions
34. **Création du tag `v1.0.0`** : `34_github_tag.png`
35. **Workflow GitHub Actions** : `35_github_actions.png`
36. **Vérification Keyless** : `36_cosign_keyless.png`
37. **Vérification de l'attestation** : `37_gh_attestation.png`

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
