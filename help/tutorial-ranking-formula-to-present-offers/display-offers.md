---
title: Crear una página Web para probar la solución
description: Página web para probar las ofertas personalizadas entregadas mediante la toma de decisiones.
role: User
level: Beginner
doc-type: Tutorial
feature: Decisioning
last-substantial-update: 2025-05-31T00:00:00.000Z
jira: KT-18188
recommendations: noDisplay, noCatalog
exl-id: 6b1eec78-153c-4ea5-acfe-2dcc6f1e6078
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: a984631b-2bae-4860-9b15-69c41a799dcb
    internal-label: APIs and SDKs
subfeature_v2:
  - id: a7a194a0-75e2-4913-8a83-14714fbf68e6
    internal-label: Decisioning API
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%
---
# Crear una página Web para probar la solución

Esta aplicación de ejemplo simula un flujo de inicio de sesión en el mundo real en el que las credenciales de usuario se validan en el servidor antes de que el ID de CRM se envíe a Adobe Experience Platform (AEP). Un servidor Node.js local se utiliza para servir de forma segura las páginas web, gestionar la lógica de autenticación básica y evitar restricciones del explorador (como el acceso bloqueado a archivos locales o la falta de encabezados CORS) que podrían interferir con la funcionalidad de Adobe Launch o Web SDK. Esta configuración garantiza que la experiencia esté más cerca de un entorno de producción real.

Las ofertas personalizadas solo se muestran después de que el usuario inicie sesión, momento en el que se completa la vinculación de identidad entre el ID de CRM del usuario y el ECID (Experience Cloud ID). Esta vinculación de identidad garantiza que Adobe Journey Optimizer (AJO) pueda reconocer el perfil con precisión y devolver ofertas segmentadas.

Después de iniciar sesión correctamente, se envía una solicitud de personalización a AJO para recuperar las ofertas disponibles para el usuario. Estas ofertas se devuelven como fragmentos de HTML, cada uno incrustado con un atributo de etiquetas de datos como, por ejemplo, data-tags=&quot;ajo offer-holiday-based-cd zip-92128 revenue-high&quot;, que incluye el nombre de la oferta y detalles de segmentación como el código postal y el nivel de ingresos.

A continuación, JavaScript analiza estos bloques de HTML y envuelve cada uno dentro de un contenedor de elemento de carrusel. Los elementos se organizan horizontalmente dentro de una pista de carrusel, lo que permite la navegación deslizable. Los botones Anterior y Siguiente (◀ y ▶) permiten a los usuarios voltear las ofertas personalizadas de una en una.

Esta configuración proporciona una experiencia adaptable que garantiza que cada usuario vea ofertas relevantes para su perfil financiero, solo después de que su identidad se haya vinculado de forma segura entre plataformas.

## Probar esta solución

* Cree una carpeta denominada fórmula de clasificación dentro del proyecto Node.js existente.

* Descomprima los [archivos proporcionados en esta carpeta de fórmula de clasificación.](assets/ranking-formula.zip)

* Para ejecutar la aplicación, navegue hasta la carpeta e inicie el servidor:
  * `cd ranking-formula`

  * `node server.js`


* Abra el explorador y vaya a http://localhost:3000/formula.html.

* Iniciar sesión con alice/pass123

Dado que Alice reside en el código postal 92128, se muestran ofertas adaptadas a esa ubicación.
