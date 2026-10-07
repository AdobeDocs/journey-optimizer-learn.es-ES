---
title: Cree ofertas para probar la toma de decisiones y la clasificación dinámicas.
description: Un elemento de oferta de Decisioning representa un único fragmento de contenido personalizado, como un mensaje, una imagen, una promoción o una recomendación, que se puede entregar a un usuario en función de reglas y condiciones definidas.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18258
exl-id: ee940654-6c6c-42d2-8c33-e0b1dfa5c3ed
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
source-wordcount: '155'
ht-degree: 0%
---
# Cree ofertas para probar la toma de decisiones y la clasificación dinámicas

Estas ofertas están diseñadas para probar la toma de decisiones dinámica y la clasificación en función de entradas contextuales en tiempo real (como la temperatura), pasadas a través de Adobe Web SDK (alloy(&quot;sendEvent&quot;)).

Antes de crear las ofertas, el esquema del elemento de oferta se amplió para incluir un nuevo campo: offerText

![offer-schema](assets/offer-schema.png).

Cree las 3 ofertas siguientes


## Oferta de clima cálido (Etiqueta:hot)

El texto de oferta para ofertas de clima cálido

```html
<div data-tags="weather hot skincare sunscreen" style="border: 1px solid #e0e0e0; padding: 1.5rem; border-radius: 10px; background-color: #fff3e0;">   <h2 style="color: #e65100;">Protect Your Skin This Summer</h2>   <p>High temperatures mean high UV risk. Get <strong>20% off</strong> our dermatologist-recommended sunscreens and skin protection kits.</p>   <p>Offer valid this week only for areas with temperatures over 90°F.</p> <button  class="ajo-cta"> Shop Sunscreen</button>   </div>
```


## Oferta de clima suave(Etiqueta:spring)

El texto de la oferta para el clima templado

```html
<div class="offer-content" style="text-align: center; padding: 1rem;">   <img     src="https://raw.githubusercontent.com/gbedekar489/gbedekar489.github.io/c857d12d92603daa50e9f707db0ba6ee87372eec/weather/spring.jpeg"     alt="Spring gardening scene"     style="width: 100%; max-width: 450px; border-radius: 12px; margin-bottom: 1rem;"   >   <h2>Grow More Than Just Flowers 🌿</h2>   <p>     Spring is here, and it's the perfect time to cultivate your garden — and your savings!     Enjoy <strong>$50 off</strong> when you spend $250 or more on gardening tools, seeds, and accessories.   </p>   <p><strong>Promo Code:</strong> <code>GROWSPRING</code></p>   <p><em>Offer valid through May 31. Let your garden — and your wallet — thrive.</em></p> <button  class="ajo-cta"> YES,I want this offer</button> </div>
```

## Oferta de tiempo frío (Etiqueta:cold)

El texto de la oferta para la oferta de tiempo frío

```html
<div class="offer-content" style="text-align: center; padding: 1rem;">   <img src="https://raw.githubusercontent.com/gbedekar489/gbedekar489.github.io/main/weather/pexels-romanp-16170.jpg"         alt="Winter clothing"         style="width: 100%; max-width: 400px; border-radius: 12px; margin-bottom: 1rem;">   <h2>Cold Weather, Hot Deals 🧤</h2>   <p>Stay warm in style with our exclusive <strong>25% off</strong> winter outerwear. From puffer jackets to wool scarves, find the perfect layers to beat the chill.</p>   <p><strong>Use code:</strong> <code>WINTER25</code> at checkout</p>   <p><em>Limited time offer. While supplies last.</em></p><button  class="ajo-cta"> Shop Sunscreen</button> </div>
```

### Crear colección

Vaya a **_Decisioning -> Catalogs ->Collection->Create collection_**
Asigne un nombre a la colección **Ofertas relacionadas con el tiempo**

Agrupe estas ofertas en esta colección mediante el generador de reglas.

