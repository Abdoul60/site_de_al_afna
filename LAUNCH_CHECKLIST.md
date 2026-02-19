# ✅ Checklist Avant Lancement - Al-Afna

Une checklist complète pour vous assurer que tout est prêt avant de déployer le site sur GitHub Pages avec votre domaine personnalisé.

---

## 📋 Préparation & Configuration

### Compte GitHub & Dépôt

- [ ] Créer un compte GitHub (si pas déjà fait)
- [ ] Créer un dépôt public nommé `al-afna` ou `al-afna.github.io`
- [ ] Cloner le dépôt localement
- [ ] Ajouter tous les fichiers du projet
- [ ] Vérifier que .gitignore est en place

### Git & Versioning

- [ ] `git config --global user.name "Votre Nom"`
- [ ] `git config --global user.email "email@example.com"`
- [ ] Premier commit : `git add .` puis `git commit -m "Initial commit"`
- [ ] Pousser vers GitHub : `git push -u origin main`
- [ ] Vérifier le dépôt sur GitHub.com

---

## 🌐 Configuration GitHub Pages

### Settings

- [ ] Aller dans **Settings** → **Pages**
- [ ] Sélectionner branche source : **main**
- [ ] Sélectionner dossier source : **/ (root)**
- [ ] Cliquer **Save**
- [ ] Attendre le premier build (5-10 minutes)
- [ ] Vérifier l'URL temporaire fournie par GitHub

### Domaine Personnalisé

- [ ] Entrer `al-afna.com` dans **Custom domain** (GitHub Pages Settings)
- [ ] Cocher **Enforce HTTPS**
- [ ] Vérifier que le fichier `CNAME` est créé automatiquement
- [ ] Configurer les DNS records chez le registraire (voir guide DEPLOYMENT.md)
- [ ] Attendre la propagation DNS (24-48h)
- [ ] Vérifier l'accès à `https://al-afna.com`

---

## 📊 Google Analytics

### Configuration GA4

- [ ] Créer un compte Google Analytics
- [ ] Créer une propriété pour `al-afna.com`
- [ ] Obtenir le **Measurement ID** (format `G-XXXXXXXXXX`)
- [ ] Copier l'ID et le conserver en sécurité

### Installation sur le Site

- [ ] Remplacer `G-XXXXXXXXXX` dans `index.html` par le vrai ID
- [ ] Remplacer `G-XXXXXXXXXX` dans `confidentialite.html` par le vrai ID
- [ ] Remplacer `G-XXXXXXXXXX` dans `mentions-legales.html` par le vrai ID
- [ ] Tester : Ouvrir le site et vérifier "Real-time" users dans GA4
- [ ] Configurer les conversions/events (optionnel)

---

## 🔗 Formulaire de Contact

### Intégration Formspree (Recommandé)

- [ ] Créer un compte sur [Formspree.io](https://formspree.io)
- [ ] Créer un nouveau formulaire avec email `contactalafna@gmail.com`
- [ ] Copier l'**ID du formulaire**
- [ ] Dans `index.html`, remplacer `form` pour utiliser Formspree :
  ```html
  <form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
  ```
- [ ] Tester : Soumettre un message de test
- [ ] Vérifier que l'email est reçu

OU

### Intégration EmailJS (Alternative)

- [ ] Créer un compte sur [EmailJS.com](https://emailjs.com)
- [ ] Configurer un service email (Gmail, Outlook, etc.)
- [ ] Obtenir **Service ID**, **Template ID**, **User ID**
- [ ] Ajouter le script EmailJS dans `index.html`
- [ ] Tester la soumission du formulaire

---

## 🔒 Sécurité & HTTPS

### Certificat SSL

- [ ] ✅ HTTPS automatique via GitHub Pages
- [ ] ✅ Certificat Let's Encrypt gratuit
- [ ] Vérifier que le cadenas 🔒 apparaît dans le navigateur
- [ ] Tester : Accéder au site en https://al-afna.com

### En-têtes de Sécurité

- [ ] Ajouter CSP headers (dans `_headers` ou en HTML meta)
- [ ] Ajouter X-Frame-Options (SAMEORIGIN)
- [ ] Ajouter X-Content-Type-Options (nosniff)
- [ ] Tester avec [securityheaders.com](https://securityheaders.com)

---

## 📄 Pages Légales

### Politique de Confidentialité

- [ ] Vérifier le contenu de `confidentialite.html`
- [ ] Mettre à jour avec vos informations réelles si nécessaire
- [ ] Tester le lien depuis le footer de `index.html`
- [ ] Vérifier que la page est accessible et bien formatée

### Mentions Légales

- [ ] Vérifier le contenu de `mentions-legales.html`
- [ ] Vérifier que les informations d'Al-Afna sont à jour
- [ ] Tester le lien depuis le footer
- [ ] Vérifier que la page est accessible et bien formatée

### Conformité RGPD

- [ ] ✅ Politique de confidentialité intégrée
- [ ] ✅ Google Analytics mentionné et expliqué
- [ ] ✅ Droits utilisateur documentés
- [ ] Ajouter un bandeau de consentement cookies (optionnel)
- [ ] Tester les options de consentement

---

## 📈 SEO & Indexation

### Métadonnées

- [ ] ✅ Title et description optimisés dans `index.html`
- [ ] ✅ Open Graph tags présents
- [ ] ✅ Twitter Card tags présents
- [ ] ✅ Canonical URL configurée

### Plans du Site

- [ ] ✅ `sitemap.xml` créé et validé
- [ ] ✅ `robots.txt` créé et optimisé
- [ ] Tester : Accéder à `https://al-afna.com/sitemap.xml`
- [ ] Tester : Accéder à `https://al-afna.com/robots.txt`

### Google Search Console

- [ ] Aller sur [search.google.com/search-console](https://search.google.com/search-console)
- [ ] Ajouter la propriété `al-afna.com`
- [ ] Vérifier ownership (DNS ou HTML)
- [ ] Soumettre le sitemap : `https://al-afna.com/sitemap.xml`
- [ ] Attendre l'indexation (quelques jours)

---

## 🧪 Tests & Validation

### Performance

- [ ] Tester sur [PageSpeed Insights](https://pagespeed.web.dev)
- [ ] Cible : Score > 90 (mobile et desktop)
- [ ] Tester sur [GTmetrix](https://gtmetrix.com)
- [ ] Vérifier les Core Web Vitals

### W3C Validation

- [ ] Valider HTML : [validator.w3.org](https://validator.w3.org)
- [ ] Valider CSS : [jigsaw.w3.org/css-validator](https://jigsaw.w3.org/css-validator)
- [ ] Pas d'erreurs critiques

### Responsive Design

- [ ] Tester sur Chrome, Firefox, Safari, Edge
- [ ] Ouvrir DevTools (F12) et tester tous les breakpoints :
  - [ ] Mobile (375px, 414px)
  - [ ] Tablet (768px)
  - [ ] Desktop (1920px)
- [ ] Vérifier que le menu mobile fonctionne
- [ ] Vérifier que les vidéos se chargent correctement

### Liens & Navigation

- [ ] Tester tous les liens internes (#accueil, #services, etc.)
- [ ] Tester les liens externes (réseaux sociaux, partenaires)
- [ ] Vérifier que les appels à l'action (CTA) fonctionnent
- [ ] Tester le formulaire de contact end-to-end

### Accessibilité

- [ ] Tester le contraste des couleurs (WCAG AA minimum)
- [ ] Vérifier les alt-texts sur les images
- [ ] Tester la navigation au clavier (Tab, Enter)
- [ ] Audit Lighthouse (F12 → Lighthouse)

---

## 🎨 Contenu & Design

### Images et Médias

- [ ] ✅ Images présentes dans le dossier `photo/`
- [ ] ✅ Vidéos présentes dans le dossier `video/`
- [ ] Les chemins `src=""` et `href=""` sont corrects
- [ ] Les vidéos se chargent correctement (peut prendre du temps)
- [ ] Vérifier la taille des fichiers (optimisés ?)

### Contenu Textuel

- [ ] Relire tout le contenu (orthographe, grammaire)
- [ ] Vérifier que les informations de contact sont correctes
- [ ] Vérifier le email : `contactalafna@gmail.com` ✅
- [ ] Vérifier le téléphone : `+227 93 62 71 45` ✅
- [ ] Vérifier l'adresse : `Niamey, Niger` ✅

### Branding

- [ ] Logo Al-Afna correct
- [ ] Couleurs (bleu #2563eb, violet #9333ea) cohérentes
- [ ] Typos et polices lisibles
- [ ] Favicon affichée correctement

---

## 📧 Email & Notifications

### Formspree / EmailJS

- [ ] Tester l'envoi d'un email de test
- [ ] Vérifier que l'email arrive dans la boîte inbox
- [ ] Vérifier que les champs (nom, email, sujet, message) sont correctement capturés

### Google Analytics Notifications

- [ ] Configurer des alertes personnalisées (optionnel, mais recommandé)
- [ ] Example : Alerte si trafic < 10 utilisateurs/jour

---

## 🔄 Déploiement Final

### Dernier Commit

- [ ] Mettre à jour les `G-XXXXXXXXXX` avec vos vrais IDs
- [ ] Mettre à jour les formulaires si nécessaire
- [ ] Commit final : `git add . && git commit -m "Prêt pour le lancement"`
- [ ] Pousser : `git push origin main`

### Vérification GitHub Pages

- [ ] Aller dans **Actions** dans le dépôt GitHub
- [ ] Vérifier que le build GitHub Pages a réussi ✅
- [ ] Vérifier que le lien de déploiement fonctionne

### Accès Public

- [ ] Ouvrir `https://al-afna.com` dans un navigateur (attendre 24-48h pour DNS)
- [ ] Naviguer sur toutes les sections
- [ ] Cliquer sur tous les liens
- [ ] Soumettre le formulaire test
- [ ] Vérifier que Google Analytics reçoit les données

---

## 📱 Tests sur Appareils Réels

### Mobile

- [ ] Tester sur iPhone (Safari)
- [ ] Tester sur Android (Chrome)
- [ ] Vérifier le menu mobile
- [ ] Vérifier que les vidéos se lisent
- [ ] Tester le formulaire sur mobile

### Tablette

- [ ] Tester sur iPad
- [ ] Vérifier la responsivité

### Desktop

- [ ] Tester sur Windows (Edge, Chrome, Firefox)
- [ ] Tester sur Mac (Safari, Firefox)

---

## 🎯 Performance & Optimisation

### Lighthouse (DevTools)

- [ ] Ouvrir DevTools (F12)
- [ ] Aller à **Lighthouse**
- [ ] Générer un rapport
- [ ] Cibles :
  - [ ] Performance > 90
  - [ ] Accessibility > 90
  - [ ] Best Practices > 90
  - [ ] SEO > 90

### Optimisations à Faire

- [ ] Compresser les images (si lourd)
- [ ] Minifier CSS et JavaScript
- [ ] Activer la mise en cache du navigateur
- [ ] Considérer un CDN (CloudFlare, Netlify)

---

## 📞 Documentation & Support

### Documentation Créée

- [ ] ✅ `README.md` - Vue d'ensemble du projet
- [ ] ✅ `DEPLOYMENT.md` - Guide de déploiement GitHub Pages
- [ ] ✅ `SECURITY.md` - Détails de sécurité et conformité
- [ ] ✅ `ANALYTICS.md` - Guide Google Analytics complet
- [ ] ✅ `confidentialite.html` - Politique RGPD
- [ ] ✅ `mentions-legales.html` - Informations légales

### Points de Contact

- [ ] Email de contact : `contactalafna@gmail.com` ✅
- [ ] Téléphone : `+227 93 62 71 45` ✅
- [ ] Formulaire de contact fonctionnel ✅

---

## 🚀 Post-Lancement (Premiers Jours)

### Monitoring

- [ ] Vérifier Google Analytics (1-2 jours après lancement)
- [ ] Vérifier Google Search Console
- [ ] Mettre à jour les DNS si necessary
- [ ] Monitoring des erreurs (DevTools)

### Annonce du Lancement

- [ ] Partager le lien sur les réseaux sociaux
- [ ] Envoyer un email aux contacts
- [ ] Soumettre le sitemap à Google
- [ ] Considérer une annonce press release

### Maintenance

- [ ] Setup un backlog de améliorations futures
- [ ] Mettre à jour le contenu mensuellement
- [ ] Analyser le trafic mensuellement
- [ ] Répondre aux messages de contact rapidement

---

## 📊 Métriques de Succès

**Objectifs à atteindre dans les 30 jours** :

| Métrique | Cible | Status |
|----------|-------|--------|
| Utilisateurs | 100+ | [ ] |
| Sessions | 150+ | [ ] |
| Pages/Session | > 2 | [ ] |
| Taux de rebond | < 60% | [ ] |
| Durée moyenne session | > 2 min | [ ] |
| Soumissions formulaire | 5+ | [ ] |
| Lighthouse Score | > 90 | [ ] |

---

## ✨ Avant de Cliquer sur "Déployer"

**Dernière vérification** :

- [ ] Tous les liens internes fonctionnent ✅
- [ ] Tous les médias se chargent ✅
- [ ] Pas de console errors (F12 → Console) ✅
- [ ] HTTPS fonctionne ✅
- [ ] GA4 reçoit les données ✅
- [ ] Formulaire de contact fonctionne ✅
- [ ] Pages légales présentes ✅
- [ ] Responsive sur mobiles ✅
- [ ] Performances > 90 Lighthouse ✅

---

## 🎉 C'est Parti !

**Félicitations ! Votre site Al-Afna est prêt au lancement ! 🚀**

Une fois la DNS configurée (24-48h), votre site sera live sur `https://al-afna.com`.

---

## 📞 Questions ?

Contactez l'équipe Al-Afna :
- 📧 Email : contactalafna@gmail.com
- 📱 Appel : +227 93 62 71 45

---

**Dernière mise à jour** : 13 Février 2026
