# ASDOWebComponent
Installation
---

Pour utiliser les composants, C/C dans votre fichier html :
```
<head>
  <script src="https://cdn.jsdelivr.net/gh/MogwaiRGod/ASDOWebComponent@main/main.js" type="module"></script>
  <script src="https://cdn.jsdelivr.net/gh/MogwaiRGod/ASDOWebComponent@main/polyfills.js" type="module"></script>
  <script src="https://cdn.jsdelivr.net/gh/MogwaiRGod/ASDOWebComponent@main/runtime.js" type="module"></script>
</head>
```

Utilisation
---
Puis pour les utiliser : 
1. Composant de signup
```
<signup-element></signup-element>
```
2. Composant de login
```
<login-element></login-element>
```
3. Bouton SSO
```
<sso-element></sso-element>
```

Exemple
---

### index.html
```
<!DOCTYPE html>
<html lang="fr">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Exemple</title>
        <!-- import des web components -->
        <script src="..\Frontend\dist\web-component-provider\main.js" type="module"></script>
        <script src="..\Frontend\dist\web-component-provider\polyfills.js" type="module"></script>
        <script src="..\Frontend\dist\web-component-provider\runtime.js" type="module"></script>
    </head>

    <body>
        <style>
            #to-signup, #signup, #sso {
                display: none;
            }
        </style>

        <signup-element id="signup"></signup-element>
        <login-element id="login"></login-element>
        <a href="#" id="to-signup">Pas encore inscrit ? Inscrivez-vous ici</a>
        <sso-element id="sso"></sso-element>

        <script>
            const signupPopup = document.getElementById("signup");
            const loginPopup = document.getElementById("login");
            const ssoPopup = document.getElementById("sso");
            const toSignup = document.getElementById("to-signup");

            if(localStorage.getItem("authToken") == null ) {
                toSignup.style.display = "block";

                toSignup.addEventListener("click", () => {
                    toSignup.style.display = "none";
                    loginPopup.style.display = "none";
                    signupPopup.style.display = "block";
                })
            } else {
                ssoPopup.style.display = "block";
            }
        </script>
    </body>
</html>
```
