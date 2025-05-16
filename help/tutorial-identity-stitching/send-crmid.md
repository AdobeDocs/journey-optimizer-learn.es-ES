---
title: Cree la aplicación de ejemplo para imitar la actividad de inicio de sesión
description: Cree una aplicación Node.js de ejemplo para simular un flujo de inicio de sesión
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
jira: KT-18089
source-git-commit: 502cdc41b666959141ff4dfc63608cc463009811
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---


# Cree la aplicación de ejemplo para imitar la actividad de inicio de sesión

Esta aplicación de ejemplo, creada e implementada en un servidor Node.js, muestra cómo enviar un ID de CRM a Adobe Experience Platform (AEP) cuando un usuario inicia sesión. La aplicación simula un flujo de inicio de sesión en el que las credenciales de usuario se validan en el servidor. Una vez que el inicio de sesión se realiza correctamente, el ID de CRM del usuario se recupera y se inserta en adobeDataLayer, lo que activa la regla correspondiente en Adobe Experience Platform Tags (anteriormente Adobe Launch).

La función attachmentLoginHandler adjunta un detector de eventos de envío a un formulario de inicio de sesión. Al enviar el formulario, evita la acción predeterminada, valida las credenciales con el objeto de un usuario predefinido y recupera el ID de CRM si es válido. La función inserta un evento userloggedin con el ID de CRM y el estado de autenticación en adobeDataLayer, y Adobe Experience Platform Tags lo recoge para enviar los datos a Adobe Experience Platform (AEP).


```javascript
function attachLoginHandler() {
    const form = document.getElementById("loginForm");
    if (!form) return;

    form.addEventListener("submit", function(e) {
        e.preventDefault();
        const username = document.getElementById("username").value;
        const password = document.getElementById("password").value;

        if (users[username] && users[username].password === password) {
            const crmid = users[username].crmid;
            window.adobeDataLayer = window.adobeDataLayer || [];
            debugger;
            window.adobeDataLayer.push({
                event: "userloggedin",
                user: {
                    crmid: crmid,
                    authenticatedState: "authenticated"
                }
            });
        }
    });
}
```

El script de etiquetas de Adobe Experience Platform se incluye en la sección `<head>` de la página de HTML mediante una etiqueta `<script>`, normalmente de la siguiente manera:

`<script src="https://assets.adobedtm.com/b5eu4857867/4e4d84957/launch-b69e276bb9b5-development.min.js" async crossorigin="anonymous"></script>`

El script de etiquetas de AEP se obtuvo publicando una propiedad habilitada para SDK web creada en el paso anterior y copiando el código incrustado de la pestaña Entornos.


