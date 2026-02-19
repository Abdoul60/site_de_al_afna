# 🚀 Al-Afna - Solutions Numériques

## 📌 Présentation

**Al-Afna** est une agence numérique basée à Niamey, Niger, spécialisée dans :

- 🌐 Développement Web moderne
- 📱 Applications Mobiles (iOS, Android)
- 📊 Analyse de Données
- 💼 Consulting en Transformation Digitale
- 📈 Stratégies Numériques

---

## 🎯 À Propos du Projet

Ce dépôt contient le **site web officiel d'Al-Afna** avec :

- ✨ Design moderne et responsive
- 🔒 Sécurité HTTPS
- 📈 SEO optimisé (métadonnées, Open Graph, sitemap)
- 📊 Google Analytics intégré
- ⚖️ Politique de Confidentialité et Mentions Légales
- 🛡️ Respect du RGPD

---

## 📂 Structure du Projet

```
site al-afna/
├── index.html                    # Page d'accueil principale
├── afna2.html                    # Version alternative (non utilisiée)
├── confidentialite.html          # Politique de confidentialité
├── mentions-legales.html         # Mentions légales
├── afna.css                      # Styles CSS
├── robots.txt                    # Fichier pour les moteurs de recherche
├── sitemap.xml                   # Plan du site
├── _config.yml                   # Configuration Jekyll (GitHub Pages)
├── _headers                      # En-têtes HTTP de sécurité
├── .gitignore                    # Fichiers à ignorer par Git
├── package.json                  # Dépendances et scripts npm
├── DEPLOYMENT.md                 # Guide complet de déploiement
├── SECURITY.md                   # Détails de sécurité
├── README.md                     # Ce fichier
├── favicon/                      # Icônes et manifest
│   ├── favicon.svg
│   ├── favicon.ico
│   ├── favicon-96x96.png
│   ├── apple-touch-icon.png
│   └── site.webmanifest
├── photo/                        # Images (équipe, portiflio, etc.)
│   ├── matop.png
│   ├── razak.png
│   ├── alas.jpeg
│   └── ...
└── video/                        # Vidéos de fond
    ├── afna.mp4
    ├── apropos.mp4
    └── ...
```

---

## 🚀 Démarrage Rapide

### Option 1 : Lecture Locale

```bash
# Cloner le dépôt
git clone https://github.com/USERNAME/al-afna.git
cd al-afna

# Démarrer un serveur local (Node.js requis)
npm install
npm start

# Ouvrir dans le navigateur
# → http://localhost:8000
```

### Option 2 : Directement sur GitHub Pages

Accédez à : `https://al-afna.com`

---

## 🔧 Configuration

### 1. Google Analytics

Remplacez `G-XXXXXXXXXX` par votre **Measurement ID** Google Analytics :

```html
<!-- Dans index.html, confidentialite.html, mentions-legales.html -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-VOTRE_ID"></script>
```

### 2. Formulaire de Contact

Utilisez **Formspree** pour sécuriser l'envoi d'emails :

1. Créez un compte sur [Formspree.io](https://formspree.io)
2. Remplacez dans `index.html` :

```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
```

### 3. Domaine Personnalisé

Après le déploiement sur GitHub Pages, configurez votre domaine en CLI :

```bash
# Vérifier le fichier CNAME
cat CNAME
# Sortie : al-afna.com

# Puis configurez le DNS avec votre registraire
```

[Guide détaillé →](DEPLOYMENT.md)

---

## 📊 Fonctionnalités

### 🎨 Design
- Gradient bleu-violet moderniste
- Responsive design (mobile, tablette, desktop)
- Animations fluides au scroll
- Sections accessibles et bien organisées

### 📄 Sections
1. **Héro** - Présentation accrocheuse avec vidéo
2. **Services** - 4 services principaux avec icônes
3. **À Propos** - Présentation d'Al-Afna
4. **Équipe** - 5 membres de l'équipe
5. **Portfolio** - 3 projets réalisés
6. **FAQ** - Questions fréquentes interactives
7. **Technologies** - Stack tech utilisé
8. **Contact** - Formulaire de demande de devis

### ⚙️ JavaScript
- Navigation mobile fluide
- Scroll lisse vers sections
- FAQ accordéons interactifs
- Animations au scroll

---

## 🔒 Sécurité

✅ **HTTPS** - Certificat SSL gratuit (Let's Encrypt)
✅ **CSP** - Content Security Policy
✅ **RGPD** - Politique de confidentialité complète
✅ **Sanitisation** - Prévention XSS
✅ **Headers sécurisés** - X-Frame-Options, X-Content-Type-Options

[Détails complets →](SECURITY.md)

---

## 📈 SEO

✅ **Métadonnées** - Title, description, keywords
✅ **Open Graph** - Partages optimisés (réseaux sociaux)
✅ **Sitemap.xml** - Plan du site pour moteurs de recherche
✅ **Robots.txt** - Directives de crawl
✅ **Canonical URL** - Évite le contenu dupliqué

---

## 📱 Responsivité

Testé et validé sur :
- ✅ Desktop (1920px+)
- ✅ Tablet (768px)
- ✅ Mobile (375px, 414px)

Utiliser `F12` → Toggle Device Toolbar pour tester.

---

## 🧪 Tests

### Audit de Performance

```bash
# Google PageSpeed
https://pagespeed.web.dev/?url=https://al-afna.com

# GTmetrix
https://gtmetrix.com?url=https://al-afna.com
```

### Validateurs
- [HTML Validator](https://validator.w3.org/)
- [CSS Validator](https://jigsaw.w3.org/css-validator/)
- [Lighthouse](chrome://inspect)

### Sécurité
- [Mozilla Observatory](https://observatory.mozilla.org/)
- [SSL Labs](https://www.ssllabs.com/ssltest/)

---

## 📝 Modifications & Mises à Jour

### Ajouter une nouvelle section

1. Créer un `<section>` dans `index.html`
2. Ajouter les styles dans `afna.css`
3. Commiter et pousser :

```bash
git add .
git commit -m "Ajout: nouvelle section"
git push origin main
```

### Mettre à jour l'équipe

Modifiez la section `#equipe` dans `index.html` avec les photos et noms.

### Modifier les services

Éditez la grille `.services-grid` dans `index.html`.

---

## 🌐 URL Importantes

| Page | URL |
|------|-----|
| Accueil | https://al-afna.site/ |
| Confidentialité | https://al-afna.site/confidentialite.html |
| Mentions Légales | https://al-afna.site/mentions-legales.html |
| Sitemap | https://al-afna.site/sitemap.xml |
| Robots | https://al-afna.site/robots.txt |

---

## 📧 Contact

- **Email** : contactalafna@gmail.com
- **Téléphone** : +227 93 62 71 45
- **Adresse** : Niamey, Niger
- **Site** : https://al-afna.site

---

## 📜 Licence

Ce projet est sous licence **MIT**. Voir [LICENSE](LICENSE) pour les détails.

---

## 👥 Équipe

**Al-Afna** est composée de :

- **Adamou Louche A.Aziz** - CEO & Fondateur
- **Ing. Abdou Razak** - Directeur Technique
- **Mahamadou Lawali Manzo** - Lead Developer
- **Yahaya Nafiou A.Magid** - Data Analyst
- **Tec. Goumour Alassane** - Lead Developer

---

## 📚 Documentation

- [Guide de Déploiement](DEPLOYMENT.md) - Déploiement GitHub Pages complet
- [Détails de Sécurité](SECURITY.md) - Configuration HTTPS, CSP, RGPD
- [Politique de Confidentialité](confidentialite.html) - RGPD et cookies
- [Mentions Légales](mentions-legales.html) - Informations légales

---

## 🔄 Historique des Changements

### v1.0.0 (13 Février 2026)
- ✨ Lancement initial
- 🔒 Politique de confidentialité
- 📊 Google Analytics
- 🔐 Sécurité HTTPS
- 📈 SEO optimisé

---

## 🤝 Contribution

Pour contribuer :

```bash
# Créer une branche
git checkout -b feature/ma-feature

# Faire des changements
git add .
git commit -m "Ajout: description"

# Pousser
git push origin feature/ma-feature

# Créer une Pull Request
```

---

## 🐛 Signaler un Bug

Créez une issue sur GitHub ou contactez : contactalafna@gmail.com

---

## 📞 Support

Pour toute question ou assistance :
- 📧 Email : contactalafna@gmail.com
- 📱 Appel : +227 93 62 71 45
- 🌐 Site : https://al-afna.com

---

**Merci d'utiliser Al-Afna ! 🙏**

*Transformez votre business avec nos solutions numériques innovantes.*

---

**Dernière mise à jour** : 13 Février 2026
