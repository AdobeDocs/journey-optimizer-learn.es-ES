---
title: Creación de ofertas basadas en la ubicación con segmentación por código postal
description: Un elemento de oferta de Decisioning representa un único fragmento de contenido personalizado, como un mensaje, una imagen, una promoción o una recomendación, que se puede entregar a un usuario en función de reglas y condiciones definidas.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00Z
jira: KT-18188
source-git-commit: 58d2964644bc199b9db212040676d87d54f767b9
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 0%

---


# Creación de ofertas basadas en la ubicación con segmentación por código postal

Antes de crear las ofertas, el esquema del elemento de oferta se amplió para incluir un nuevo campo: zipcode. Este campo personalizado permite etiquetar explícitamente cada oferta con su código postal de destinatario, lo que permite un filtrado y una clasificación basados en la ubicación durante la toma de decisiones.

Con el esquema actualizado, se crearon dos ofertas personalizadas:

* Oferta 1: &quot;Planes flexibles de inversión para Mira Mesa (92126)&quot;
Adaptada a los jóvenes profesionales y a los residentes de 92126, esta oferta promueve opciones de inversión flexibles como los fondos cotizados y los fondos mutuos destinados al crecimiento a largo plazo. El campo código postal está establecido en 92126.

* Oferta 2: &quot;CD de alto rendimiento para Rancho Bernardo (92128)&quot;
Segmentando a individuos financieramente estables y listos para la jubilación en 92128, esta oferta cuenta con certificados de depósito (CD) de alto rendimiento con retornos garantizados. El campo código postal está establecido en 92128.

Estas ofertas ahora se enriquecen con los metadatos de ubicación, lo que las hace aptas para la selección dinámica y la clasificación basada en los códigos postales del perfil del usuario en pasos posteriores.

La siguiente captura de pantalla muestra los atributos personalizados agregados al esquema de elementos de oferta.

![ofertas-metadatos](assets/offers-meta-data.png)


## Oferta para 92126

El texto de oferta para ofertas en 92126 código postal

```html
<div style="max-width: 600px; margin: 2rem auto; padding: 1.5rem; border: 1px solid #ddd; border-radius: 12px; font-family: Arial, sans-serif; background-color: #f9f9f9; box-shadow: 0 4px 12px rgba(0,0,0,0.05);">   <h2 style="color: #1a237e; font-size: 1.5rem; margin-bottom: 0.5rem;">     Boost Your Financial Game with Smart Investment Options   </h2>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     In Mira Mesa (92126), ambition meets opportunity. Whether you're building wealth or just getting started, our     <strong>diversified investment plans</strong> — including <strong>tech-focused ETFs</strong> and     <strong>flexible mutual funds</strong> — are designed to grow with your goals.   </p>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     Enjoy expert guidance, low fees, and strategies built for busy professionals who want more from their money — without the hassle.   </p>   <a href="#start-investing" style="display: inline-block; margin-top: 1rem; background-color: #1a73e8; color: white; padding: 0.75rem 1.25rem; border-radius: 8px; text-decoration: none; font-weight: bold;">     Start Investing Smarter   </a> </div>
```


## Oferta para 92128

El texto de oferta para ofertas en 92128 código postal

```html
<div style="max-width: 600px; margin: 2rem auto; padding: 1.5rem; border: 1px solid #ddd; border-radius: 12px; font-family: Arial, sans-serif; background-color: #fdfdfd; box-shadow: 0 4px 12px rgba(0,0,0,0.05);">   <h2 style="color: #1a237e; font-size: 1.5rem; margin-bottom: 0.5rem;">     Grow Your Savings with Confidence – Exclusive CD Rates for 92128   </h2>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     Live in Rancho Bernardo? Take advantage of your financial momentum with our <strong>high-yield Certificates of Deposit</strong>, offering up to <strong>5.25% APY</strong>.     Designed for peace of mind and smart growth, our flexible CD options let you lock in guaranteed returns while enjoying the stability you deserve.   </p>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     Whether you're planning retirement or simply securing your future, this offer is tailored for residents like you.   </p>   <a href="#explore-cd-options" style="display: inline-block; margin-top: 1rem; background-color: #1a73e8; color: white; padding: 0.75rem 1.25rem; border-radius: 8px; text-decoration: none; font-weight: bold;">     Explore CD Options   </a> </div>
```

## Oferta genérica (oferta de reserva)

El texto de oferta de la oferta genérica, sin ningún código postal asociado a la oferta

```html
<div style="max-width: 600px; margin: 2rem auto; padding: 1.5rem; border: 1px solid #ddd; border-radius: 12px; font-family: Arial, sans-serif; background-color: #ffffff; box-shadow: 0 4px 12px rgba(0,0,0,0.05);">
  <h2 style="color: #1a237e; font-size: 1.5rem; margin-bottom: 0.5rem;">
    Invest Smarter: Build Wealth with Flexible Financial Plans
  </h2>
  <p style="color: #333; font-size: 1rem; line-height: 1.6;">
    Looking to take control of your financial future? Our flexible investment solutions are designed to meet a wide range of goals — from growing savings to planning for retirement.
    Choose from diversified mutual funds, ETFs, and professionally managed portfolios, all with expert guidance and minimal hassle.
  </p>
  <p style="color: #333; font-size: 1rem; line-height: 1.6;">
    Whether just starting out or optimizing an existing strategy, this offer provides the tools to invest with confidence — no matter where you live.
  </p>
  <a href="#explore-investment-plans" style="display: inline-block; margin-top: 1rem; background-color: #1a73e8; color: white; padding: 0.75rem 1.25rem; border-radius: 8px; text-decoration: none; font-weight: bold;">
    Explore Investment Plans
  </a>
</div>
```

Agrupe estas ofertas en una colección llamada **_GenericOffers_**

Las ofertas están disponibles para todos los visitantes (es decir, no hay restricciones de elegibilidad estrictas), por lo que la fórmula de clasificación se vuelve crítica para determinar qué oferta debe mostrarse en función del contexto del perfil.
Dado que las reglas de elegibilidad no filtran las ofertas, los tres se tratan como candidatos.
La estrategia de selección recupera los tres.
La fórmula de clasificación los puntúa en función de atributos de perfil (como zipcode y annualIncome) para elegir el mejor.



