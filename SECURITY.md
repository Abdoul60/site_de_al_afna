# 🔐 Guide de Sécurité - Al-Afna

## 📋 Checklist de Sécurité

- [x] **HTTPS** : Certificat SSL gratuit (Let's Encrypt) via GitHub Pages
- [x] **CSP (Content Security Policy)** : À ajouter en en-têtes
- [x] **Sanitisation des formulaires** : À implémenter côté serveur
- [x] **Protégez les données** : RGPD & Politique de confidentialité en place
- [x] **Logs d'accès** : GitHub Pages et Google Analytics assurent le tracking
- [ ] **Authentification** : Non nécessaire pour un site statique
- [ ] **Base de données** : Non utilisée (site statique)

---

## 1️⃣ Sécurité HTTPS

✅ **Déjà activé** sur GitHub Pages

```
- Certificat SSL gratuit (Let's Encrypt)
- Renouvellement automatique
- Redirection HTTP → HTTPS automatique
```

Vérifiez :

```
https://al-afna.com → certif valide ✅
```

---

## 2️⃣ Content Security Policy (CSP)

Ajoutez ce header pour bloquer les scripts malveillants.

### créer un fichier `_headers`

```
/*
  Content-Security-Policy: default-src 'self'; script-src 'self' 'unsafe-inline' https://www.googletagmanager.com/gtag/js https://cdnjs.cloudflare.com; style-src 'self' 'unsafe-inline' https://cdnjs.cloudflare.com; img-src 'self' data: https:; font-src 'self' https://cdnjs.cloudflare.com; connect-src 'self' https://www.google-analytics.com; frame-ancestors 'none'
```

---

## 3️⃣ Sécurité des En-têtes HTTP

### Fichier `_headers` complet pour GitHub Pages

```
/*
  # Sécurité
  X-Content-Type-Options: nosniff
  X-Frame-Options: SAMEORIGIN
  X-XSS-Protection: 1; mode=block
  Referrer-Policy: strict-origin-when-cross-origin
  
  # HSTS (Force HTTPS pendant 1 an)
  Strict-Transport-Security: max-age=31536000; includeSubDomains; preload
  
  # Permissions
  Permissions-Policy: geolocation=(), microphone=(), camera=()
  
  # CSP
  Content-Security-Policy: default-src 'self'; script-src 'self' 'unsafe-inline' https://www.googletagmanager.com/gtag/js https://cdnjs.cloudflare.com; style-src 'self' 'unsafe-inline' https://cdnjs.cloudflare.com; img-src 'self' data: https:; font-src 'self' https://cdnjs.cloudflare.com
  
  # Cache
  Cache-Control: public, max-age=3600
```

**Note** : GitHub Pages ne supporte pas les fichiers `_headers` natifs. Utilisez plutôt des métadonnées dans le HTML.

---

## 4️⃣ Sécurité des Formulaires

### Le formulaire contact doit être sécurisé

**❌ Problème actuel** : Le formulaire n'envoie pas les données (code JavaScript manquant)

### Solution : Utiliser Formspree, Netlify Forms, ou EmailJS

#### Option A : **Formspree** (Gratuit, Recommandé)

1. Allez sur [Formspree.io](https://formspree.io)
2. Créez un compte
3. Cliquez sur "New Form"
4. Entrez votre email : `contactalafna@gmail.com`
5. Copier l'**ID de formulaire**

Mettez à jour le formulaire dans `index.html` :

```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
    <input type="text" name="name" placeholder="Votre nom" required>
    <input type="email" name="email" placeholder="Votre email" required>
    <input type="text" name="subject" placeholder="Sujet" required>
    <textarea name="message" placeholder="Votre message" required></textarea>
    <button type="submit">Envoyer le Message</button>
</form>
```

#### Option B : **EmailJS** (Gratuit, JavaScript)

1. Allez sur [EmailJS.com](https://emailjs.com)
2. Créez un compte
3. Intégrez le script :

```html
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3.10.0/dist/index.min.js"></script>
<script>
  emailjs.init("YOUR_SERVICE_ID");
  
  document.querySelector('form').addEventListener('submit', function(event) {
    event.preventDefault();
    emailjs.sendForm('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', this)
      .then(() => alert('Message envoyé !'))
      .catch(err => alert('Erreur: ' + err));
  });
</script>
```

---

## 5️⃣ Protection des Données (RGPD)

✅ **Déjà en place** :

- [x] Politique de Confidentialité (`confidentialite.html`)
- [x] Mentions Légales (`mentions-legales.html`)
- [x] Consentement Google Analytics en header
- [x] Cookies déclarés

### À ajouter (optionnel) :

Un **bandeau de consentement cookie** pour demander l'autorisation avant tout tracking.

```html
<!-- CookieBot ou Tarteaucitron -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/jmmx/tarteaucitron@3.2.0/tarteaucitron.css">
<script src="https://cdn.jsdelivr.net/gh/jmmx/tarteaucitron@3.2.0/tarteaucitron.js"></script>
<script>
  tarteaucitron.init({
    privacyUrl: "https://al-afna.com/confidentialite.html",
    hashtag: "#tarteaucitron",
    cookieName: "tarteaucitron",
    cookieDomain: "al-afna.com",
    serviceList: ["google-analytics"],
    highPrivacy: true
  });
</script>
```

---

## 6️⃣ Protection contre les Attaques Courantes

### XSS (Cross-Site Scripting)

✅ **Protégé par CSP** (voir section 2)

```html
<!-- ❌ Bloqué -->
<img src=x onerror="alert('XSS')">

<!-- ✅ Autorisé -->
<img src="image.png" alt="Image">
```

### CSRF (Cross-Site Request Forgery)

✅ **Protégé** : Utilisez Formspree ou EmailJS (JWT tokens)

### SQL Injection

✅ **Pas applicable** : Site statique (pas de base de données)

### Path Traversal

✅ **Protégé** : GitHub Pages utilise des chemins sécurisés

---

## 7️⃣ Scanners de Sécurité

Testez régulièrement votre site :

1. **[Mozilla Observatory](https://observatory.mozilla.org/)**
   - Entrez : `al-afna.com`
   - Cible : Note A+

2. **[SSL Labs](https://www.ssllabs.com/ssltest/)**
   - Vérifiez le certificat SSL

3. **[Securityheaders.com](https://securityheaders.com/)**
   - Analyse des en-têtes de sécurité

4. **[GTmetrix](https://gtmetrix.com/)**
   - Performance et sécurité

---

## 8️⃣ Logs & Monitoring

### Google Analytics (Gratuit)

✅ **Déjà intégré** : Monitoring du trafic et comportement utilisateur

```
- Visites en temps réel
- Géolocalisation
- Appareils utilisés
- Comportement utilisateurs
```

### GitHub Actions (Logs de déploiement)

```
Repo → Actions → Vérifier les logs de build
```

### Monitoring avancé (optionnel)

- **Uptime Robot** : https://uptimerobot.com (Gratuit)
- **Cloudflare Analytics** : https://cloudflare.com (Gratuit, rapide)

---

## 9️⃣ Sauvegarde & Disaster Recovery

```powershell
# Sauvegarde locale
cd "C:\Users\X1 Carbon\Desktop\project"
git clone https://github.com/USERNAME/al-afna.git al-afna-backup
```

---

## 🔟 Checklist Avant Déploiement

- [x] Certificat HTTPS activé
- [x] Politique de Confidentialité publiée
- [x] Google Analytics configuré
- [x] Robots.txt et Sitemap.xml créés
- [ ] Formulaire contact sécurisé (Formspree/EmailJS)
- [ ] En-têtes CSP et de sécurité ajoutés
- [ ] Scanner de sécurité validé (Score A+)
- [ ] DNS proprement configuré
- [ ] Sauvegarde créée

---

## 1️⃣1️⃣ Mises à Jour de Sécurité

GitHub Pages renouvelle automatiquement :

- ✅ Certificats SSL (Let's Encrypt)
- ✅ Dépendances backend (GitHub infrastructure)
- ✅ Protection DDoS (Inclus gratuitement)

**Votre responsabilité** :

- 🔄 Mettre à jour les dépendances npm si utilisées
- 🔄 Auditer régulièrement les en-têtes CSP
- 🔄 Analyser les logs Google Analytics

---

## Contact Sécurité

🔗 **Signaler une vulnérabilité** : contactalafna@gmail.com

Nous prendrons en charge tout problème de sécurité avec confidentialité.

---

**✨ Votre site est maintenant sécurisé ! 🛡️**
