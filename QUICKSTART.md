# ⚡ Quick Start - Déployer Al-Afna en 10 Étapes

**Vous voulez passer de zéro à hébergé en 30 minutes ?** Suivez ce guide rapide ! ⚡

---

## 1️⃣ Google Analytics (2 min)

```
1. Allez sur analytics.google.com
2. Créez une propriété : "al-afna.com"
3. Copez votre Measurement ID (G-XXXXXXXXXX)
```

Remplacez dans les 3 fichiers :
- `index.html` : ligne ~45
- `confidentialite.html` : ligne ~48
- `mentions-legales.html` : ligne ~40

---

## 2️⃣ Créer GitHub Account (3 min)

```
1. Allez à github.com
2. Sign Up
3. Créez le dépôt : "al-afna"
```

Marquez le dépôt comme **PUBLIC** ✅

---

## 3️⃣ Initialiser Git (5 min)

**Dans PowerShell** :

```powershell
cd "C:\Users\X1 Carbon\Desktop\project\site al-afna"

git init
git config user.name "Nom"
git config user.email "email@example.com"
git add .
git commit -m "Initial commit - Al-Afna launchready"
git remote add origin https://github.com/USERNAME/al-afna.git
git branch -M main
git push -u origin main
```

✅ Code maintenant sur GitHub !

---

## 4️⃣ Activer GitHub Pages (2 min)

Sur **GitHub.com** :

```
1. Allez à Settings
2. Pages
3. Branch : main
4. Folder : / (root)
5. Click Save
```

Vous verrez : `Your site is live at https://username.github.io/al-afna`

---

## 5️⃣ Configurer Domaine (5 min dans GitHub)

Sur **Settings > Pages** :

```
1. Entrez : al-afna.site
2. Cochez : Enforce HTTPS
3. Click Save
```

Un fichier `CNAME` s'ajoute automatiquement.

---

## 6️⃣ Configurer DNS (À faire chez Registraire)

Chez votre registraire de domaine (OVH, Namecheap, GoDaddy) :

### Option Simple (CNAME)

```
Host: www
Type: CNAME
Value: USERNAME.github.io
```

### Option Apex (Domaine Racine)

```
Host: @
Type: A
Value: 185.199.108.153

Host: @
Type: A
Value: 185.199.109.153

Host: @
Type: A
Value: 185.199.110.153

Host: @
Type: A
Value: 185.199.111.153
```

⏱️ **Attendre 24-48h pour propagation DNS** ⏳

---

## 7️⃣ Vérifier Déploiement (Temps réel)

**Vérifications** :

```
✅ "Real-time users" dans Google Analytics
✅ https://al-afna.site s'affiche
✅ Cadenas 🔒 pour HTTPS
✅ Aucune erreur console (F12)
```

---

## 8️⃣ Formulaire Contact (Optionnel - 3 min)

Via **Formspree.io** :

```
1. Allez sur formspree.io
2. New Form → Email: contactalafna@gmail.com
3. Copiez l'ID du formulaire
4. Dans index.html, ligne ~560 :
   action="https://formspree.io/f/YOUR_FORM_ID"
5. Commit & Push
```

---

## 9️⃣ Tester Avant Lancement

```
□ Tous les liens cliquables
□ Formulaire envoie des emails
□ Images chargées
□ Vidéos jouables
□ Mobile responsive
□ HTTPS fonctionne
□ Google Analytics reçoit des données
```

---

## 🔟 Lancement ! 🎉

```bash
# Dernier commit
git add .
git commit -m "Lancement officiel"
git push origin main

# Attendre 2-5 min pour le déploiement
# Puis vérifier : https://al-afna.com ✅
```

---

## ⏱️ Temps Total

| Étape | Temps |
|-------|-------|
| GA4 | 2 min |
| GitHub | 3 min |
| Git Init | 5 min |
| GitHub Pages | 2 min |
| DNS Config | 5 min |
| Attendre DNS | 24-48h ⏳ |
| Tester | 5 min |
| **Total** | **~30 min** |

**DNS Propagation** : 24-48h (hors contrôle, attendez juste) ⏳

---

## 🚨 Problème ? Checklist Rapide

```
❌ Site ne s'affiche pas ?
→ Attendez 5-10 min
→ Videz le cache (Ctrl+Shift+Del)
→ Vérifiez que le dépôt est PUBLIC

❌ HTTPS ne fonctionne pas ?
→ Attendez 24h
→ Vérifiez que le CNAME existe
→ Attendez la propagation DNS

❌ Google Analytics ne capture rien ?
→ Remplacez bien G-XXXXXXXXXX par votre ID
→ Ouvrez la page en INCOGNITO
→ Attendez 30sec et rafraîchissez GA

❌ Formulaire ne fonctionne pas ?
→ Avec Formspree, testez l'envoi
→ Vérifiez l'email dans spam
→ Créez le formulaire sur Formspree d'abord
```

---

## 📞 Support Rapide

- 📧 **Email** : contactalafna@gmail.com
- 📱 **Tel** : +227 93 62 71 45
- 📚 **Docs** : Voir README.md, DEPLOYMENT.md

---

## 📚 Prochaine Lecture

Après le lancement :

1. **ANALYTICS.md** - Utiliser Google Analytics
2. **SECURITY.md** - Sécurité avancée
3. **CONTRIBUTING.md** - Mettre à jour le site

---

## 🎯 Vous êtes Prêt !

Vous avez maintenant un site professionnel AL-Afna :

✅ Modern design  
✅ HTTPS sécurisé  
✅ SEO optimisé  
✅ RGPD conforme  
✅ Analytics actif  
✅ Coûts très bas (juste domaine)  

**Bon lancement ! 🚀**

---

**Questions ?** → contactalafna@gmail.com

---

**Dernière mise à jour** : 13 Février 2026
