---
title: Crear una página Web para probar la solución
description: Página web para probar las ofertas personalizadas entregadas mediante la toma de decisiones.
role: User
level: Beginner
doc-type: Tutorial
feature: Decisioning
last-substantial-update: 2025-05-05T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-17728
exl-id: 72a67137-303d-4dfe-9b70-322c81e5fb27
source-git-commit: 82d82b3aac2bf91e259b01fd8c6b4d6065f9640a
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---

# Creación de una página web para probar la solución

Esta página web se creó para probar ofertas personalizadas entregadas a través de Adobe Journey Optimizer Decisioning. Proporciona un entorno controlado en el que se puede activar la llamada a sendEvent y procesar el contenido de oferta devuelto, lo que ayuda a validar la configuración de personalización de principio a fin y garantizar que la toma de decisiones funcione según lo esperado.

El siguiente script es responsable de recuperar y mostrar una oferta personalizada en una página web mediante Adobe Journey Optimizer.

1. Descodificar entidades de HTML:

   Hay una función de ayuda que convierte de forma segura cualquier carácter especial del contenido de la oferta en HTML legible.

1. Ejecutar personalización:

   Cuando se le llama, envía una solicitud (`sendEvent`) al Web SDK de Adobe para obtener contenido personalizado para un área específica de la página (el elemento `#ajo-offer`).

   Si se devuelve una oferta, descodifica la HTML y la inserta en la página.

   Si no se devuelve nada, registra una advertencia.

1. Espere a que SDK:

   Dado que SDK (alloy) de Adobe se carga asincrónicamente, el script espera hasta que se cargue completamente antes de realizar la solicitud.

   Comprueba la aleación cada 200 milisegundos, hasta 20 veces, para evitar errores.

1. Al cargar la página:

   Cuando la página termina de cargarse, el script inicia el proceso llamando a `waitForAlloy()`.



```javascript
< script >
    function decodeHtmlEntities(html) {
        const txt = document.createElement("textarea");
        txt.innerHTML = html;
        return txt.value;
    }


function runPersonalization() {
    console.log("🚀 Sending personalization request to AJO...");
    alloy("sendEvent", {
        renderDecisions: true,
        personalization: {
            surfaces: ["#ajo-offer"]
        }
    }).then(result => {
        console.log("🔍 Web SDK decision response:", result);

        const decision = result.propositions?.[0];
        const html = decision?.items?.[0]?.data?.content;

        const container = document.getElementById("ajo-offer");
        if (html && container) {
            const decodedHtml = decodeHtmlEntities(html);
            console.log("✅ Offer HTML content (decoded):", decodedHtml);
            container.innerHTML = decodedHtml;
        } else {
            console.warn("⚠️ No personalized offer returned.");
        }


    }).catch(error => {
        console.error("❌ sendEvent failed:", error);
    });
}

function waitForAlloy(callback, retries = 20) {
    if (typeof alloy === "function") {
        callback();
    } else if (retries > 0) {
        console.log("⌛ Waiting for Alloy...");
        setTimeout(() => waitForAlloy(callback, retries - 1), 200);
    } else {
        console.error("❌ alloy is not loaded after waiting.");
    }
}

// Trigger initial personalization on page load
document.addEventListener("DOMContentLoaded", function() {
    waitForAlloy(() => runPersonalization());
}); <
/script>
```

[La página de HTML de muestra y los recursos relacionados se pueden descargar desde aquí](assets/web-page-assets.zip)
