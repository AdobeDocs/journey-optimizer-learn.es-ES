---
title: Crear una oferta
description: Un elemento de oferta de Decisioning representa un único fragmento de contenido personalizado, como un mensaje, una imagen, una promoción o una recomendación, que se puede entregar a un usuario en función de reglas y condiciones definidas.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-17728
exl-id: d705992a-0d47-4bb9-b3d8-b925974e64cb
source-git-commit: 82d82b3aac2bf91e259b01fd8c6b4d6065f9640a
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 1%

---

# Crear una oferta

Un elemento de oferta en AJO representa un solo fragmento de contenido personalizado. El contenido puede ser una promoción, un mensaje o una recomendación que se entrega a un usuario según la lógica de toma de decisiones.

Cuando crea un elemento de oferta en AJO, debe basarse en un [!UICONTROL Esquema de toma de decisiones]. Este esquema define la estructura y los campos disponibles en la oferta, como título, descripción, imageURL, offerText, etc.

Este esquema:

* Estandariza el modelo de contenido para todas las ofertas de una colección.

* Permite campos de personalización coherentes en todos los elementos de oferta.

* Permite que las estrategias de selección hagan coincidir reglas con contenido estructurado

## Modificación del esquema

1. Inicie sesión en Journey Optimizer.
1. Haga clic en **[!UICONTROL Toma de decisiones]** > **[!UICONTROL Catálogos]** > **[!UICONTROL Editar esquema]**.
1. Agregue un elemento de tipo `string` llamado `offerItem` como se muestra a continuación

   ![esquema de toma de decisiones](assets/offer-schema.png)

## Creación de un elemento de oferta

1. Haga clic en **[!UICONTROL Decisiones]** > **[!UICONTROL Catálogos]** > **[!UICONTROL Crear elemento]**.

1. Cree tres ofertas: `Love Stocks`, `Love Bonds` y `Love CD`.

   Para cada oferta, copie y pegue el texto de oferta correspondiente proporcionado al final de este artículo en el elemento de oferta correspondiente.

1. Etiquete las ofertas con la etiqueta creada en el paso anterior.
1. Añada la audiencia adecuada a cada oferta.
   ![idoneidad de la oferta](assets/offer-eligibility.png)
1. Apruebe las ofertas.

Oferta completada con atributos estándar y personalizados definidos:

![oferta de acciones de amor](assets/love-bonds.png)

**Oferta de existencias de amor**

```html
<div style="font-family: Arial, sans-serif; background-color: #f9f9f9; border: 1px solid #ddd; padding: 1.5rem; border-radius: 8px; max-width: 600px; margin: auto;">   <h3 style="color: #1a73e8; margin-top: 0;">📈 Open a Stock Trading Account & Get $100 in Bonus Stock</h3>   <p style="font-size: 1rem; color: #333;">     Ready to start building your portfolio? Open a new stock trading account with us and receive a      <strong>$100 bonus in stock</strong> — on us.   </p>   <ul style="padding-left: 1.25rem; color: #444;">     <li>🧾 No account minimums — start investing with as little as $1</li>     <li>📉 $0 commissions on online stock trades</li>     <li>📊 Access to powerful trading tools and real-time analytics</li>     <li>🎓 Free educational resources to help you invest confidently</li>   </ul>   <p style="color: #333;">     It's never been easier to start trading. Join thousands of investors who trust us to help them grow their wealth.   </p>   <a href="https://yourbrokerage.com/open-account"      style="display: inline-block; margin-top: 1rem; padding: 0.75rem 1.5rem; background-color: #1a73e8; color: white; text-decoration: none; border-radius: 5px; font-weight: bold;">      🚀 Open Your Account Today   </a> </div>
```

**Texto de oferta de bonos de amor**

```html
<div style="font-family: Arial, sans-serif; background-color: #f9f9f9; border: 1px solid #ddd; padding: 1.5rem; border-radius: 8px; max-width: 600px; margin: auto;">   <h3 style="color: #6c757d; margin-top: 0;">🏦 Invest in Stability: Explore Our Premium Bond Options</h3>   <p style="font-size: 1rem; color: #333;">     Looking for consistent income with lower risk? Our carefully selected bonds offer predictable returns and help balance your investment portfolio.   </p>   <ul style="padding-left: 1.25rem; color: #444;">     <li>📉 Lower volatility than stocks — ideal for income-focused investors</li>     <li>💵 Earn interest payments monthly, quarterly, or annually</li>     <li>🔍 Choose from government, municipal, or corporate bonds</li>     <li>🎁 Open a bond investment account today and receive a <strong>$50 interest credit</strong></li>   </ul>   <p style="color: #333;">     Whether you're preparing for retirement or just want a reliable stream of income, bonds offer a solid foundation for your financial strategy.   </p>   <a href="https://yourfirm.com/open-bond-account"      style="display: inline-block; margin-top: 1rem; padding: 0.75rem 1.5rem; background-color: #6c757d; color: white; text-decoration: none; border-radius: 5px; font-weight: bold;">      🧾 Open a Bond Account   </a> </div>
```

**Texto de oferta de CD de amor**

```html
<div style="font-family: Arial, sans-serif; background-color: #f9f9f9; border: 1px solid #ddd; padding: 1.5rem; border-radius: 8px; max-width: 600px; margin: auto;">   <h3 style="color: #28a745; margin-top: 0;">💰 Lock in a 5.25% APY — Open Your CD Account Today</h3>   <p style="font-size: 1rem; color: #333;">     Secure your savings with a high-yield Certificate of Deposit. For a limited time, enjoy a      <strong>guaranteed 5.25% annual percentage yield (APY)</strong> on 12-month CDs.   </p>   <ul style="padding-left: 1.25rem; color: #444;">     <li>🔒 Guaranteed returns with FDIC insurance</li>     <li>📈 Lock in today's high rates before they change</li>     <li>💼 Flexible terms from 6 to 24 months</li>     <li>🎁 Open with just $500 and get a $50 bonus</li>   </ul>   <p style="color: #333;">     Whether you're saving for a short-term goal or building a conservative income strategy, our CDs offer peace of mind and predictable growth.   </p>   <a href="https://yourbank.com/open-cd"      style="display: inline-block; margin-top: 1rem; padding: 0.75rem 1.5rem; background-color: #28a745; color: white; text-decoration: none; border-radius: 5px; font-weight: bold;">      💼 Open a CD Account   </a> </div>
```
