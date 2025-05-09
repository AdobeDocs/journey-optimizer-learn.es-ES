---
title: Creación de un formulario web
description: Cree un formulario en la página de HTML que permita a los usuarios seleccionar sus preferencias de inversión
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-17923
exl-id: 20de8dec-aac8-43ed-8305-e723f82a5dd9
source-git-commit: 163edfb3367d03729d68c9339ee2af4a0fe3a1b3
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 0%

---

# Creación de un formulario web

El siguiente formulario de HTML se creó para capturar las preferencias de los usuarios
![formulario html](assets/web-form.png)

Cuando un usuario hace clic en el botón de la página web, su preferencia financiera seleccionada (como acciones, bonos o CD) se captura y se inserta en la capa de datos de Adobe. Este evento (assetClassSelection) almacena la elección del usuario en tiempo real. A continuación, Adobe Launch escucha este evento, recupera la opción de inversión seleccionada (PreferredFinancialInstrument) y puede almacenar en déclencheur acciones como enviar los datos a Adobe Experience Platform (AEP) o actualizar reglas de personalización

El siguiente JavaScript se escribió para administrar el envío del formulario

```javascript
function handleSubmission() {
  window.adobeDataLayer = window.adobeDataLayer || [];

  const selectedAssetClass = document.querySelector('input[name="assetclass"]:checked');
  const errorMessage = document.getElementById("error-message");
  const messageBox = document.getElementById("message");

  if (!selectedAssetClass) {
    errorMessage.textContent = "Please select a financial instrument.";
    messageBox.textContent = "";
    return;
  }

  errorMessage.textContent = "";

  const subscriptionEvent = {
    event: "assetClassSelection",
    xdm: {
      eventType: "assetClassSelection",
      eventID: "investment_preference_event",
      timestamp: new Date().toISOString(),
      FinancialInterest: {
        PreferredFinancialInstrument: selectedAssetClass.value
      }
    }
  };

  console.log("📩 Sending asset class data to AEP:", subscriptionEvent);
  window.adobeDataLayer.push(subscriptionEvent);

  // ✅ Show thank-you message
  messageBox.textContent = `Thank you for selecting "${selectedAssetClass.value}". We'll use this to personalize your experience.`;
}
```

[El formulario de HTML de ejemplo se proporciona como parte de este tutorial](assets/webform.zip)
