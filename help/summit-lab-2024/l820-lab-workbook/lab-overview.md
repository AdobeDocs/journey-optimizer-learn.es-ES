---
title: Manual de laboratorio - L820 - Cree momentos móviles personalizados con Adobe Journey Optimizer
description: Explore varios escenarios móviles y aprenda a implementar experiencias personalizadas para la web y dispositivos móviles con Journey Optimizer.
feature: Overview
role: User
level: Intermediate
doc-type: Tutorial
duration: 0
jira: KT-14977
thumbnail: KT-14977.jpeg
last-substantial-update: 2024-03-26T00:00:00Z
exl-id: e6d029f9-c936-427b-9d6e-4e296fd3c3ce
source-git-commit: fd50ce73503ca6b42e0171d8476ea08928ebd165
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# LIBRO DE LABORATORIO

![Adobe Summit - texto alternativo](/help/summit-lab-2024/l820-lab-workbook/assets/adobe-summit.png "Adobe Summit")

## L820: cree momentos móviles personalizados con Adobe Journey Optimizer

En este laboratorio práctico, explorará varios escenarios móviles y aprenderá a implementar experiencias personalizadas para la web y dispositivos móviles con Journey Optimizer.


>[!IMPORTANT]
>
>Absténgase de publicar fotos o capturas de pantalla de la sesión en las redes sociales.
><br>
>**Confidencialidad de Adobe**
>La información y las divulgaciones de productos compartidas hoy durante este laboratorio son Información confidencial de Adobe.
>Los participantes no podrán reproducir, utilizar, difundir ni revelar información confidencial a ninguna persona o entidad.
>Las divulgaciones de productos son solo para fines informativos, no son una garantía de ninguna función o funcionalidad futura y están sujetas a cambios en cualquier momento. Como tal, dichas funciones o funcionalidades del producto no forman parte del acuerdo con Adobe ni se comprometen con usted de ninguna otra manera.
><br>
>**Descargo de responsabilidad**
>Adobe le proporciona acceso anticipado a las funciones, que aprovechan la tecnología de IA generativa. Tenga en cuenta que estas funciones aún están en desarrollo y pueden producir respuestas inesperadas o inexactas. Agradecemos sus comentarios ya que lanzamos esta función al mercado.


### Puntos clave

* Comprenda la variedad de experiencias móviles compatibles.
* Configure una campaña push.
* Obtenga información sobre cómo configurar campañas móviles en la aplicación.
* Configurar mensajes web en la aplicación.
* Pruebe sus propios escenarios personalizados.

### Requisitos previos

* Conozca el número de asiento: Puede encontrar el número de asiento en la parte superior del escritorio de la máquina del laboratorio:

![Número de puestos](/help/summit-lab-2024/l820-lab-workbook/assets/locate-seat-number.png)
Necesita acceso a:

* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"}: los detalles de inicio de sesión se proporcionan durante los ejercicios.
* [Sitio web de Fréscopa](https://dsn.adobe.com/p/adobe-summit-2024?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsImlzc3VlciI6InNoYXJlZC1saW5rIiwiYXJnb24iOnsiYWNjZXNzIjoicmVhZC1wcm9qZWN0IiwicHJvamVjdElkIjoiYWRvYmUtc3VtbWl0LTIwMjQifSwiaWF0IjoxNzEwNTI0MTIwLCJleHAiOjE3MTIzMzg1MjB9.q2uGVst6HjJw8SCWl-3pViNzepkdGnNCvGqZnbbkTsY){target="_blank"}


### Comprender el caso de uso

Fréscopa, una empresa dinámica e innovadora, se especializa en revolucionar la experiencia del café a través de su combinación única de servicios de suscripción de café y una amplia gama de productos relacionados con el café disponibles en su sitio web y aplicación móvil. Con un compromiso de ofrecer calidad y sabor excepcionales, Fréscopa atiende a los entusiastas del café que buscan comodidad y opciones de primera calidad.

El corazón del negocio de Fréscopa radica en sus servicios de suscripción de café, proporcionando a los clientes una selección seleccionada de granos de alta calidad entregados directamente a su puerta. Este enfoque personalizado garantiza que los amantes del café puedan disfrutar de una experiencia fresca y deliciosa adaptada a sus preferencias.

Como complemento a sus servicios de suscripción, el sitio web y la aplicación móvil de Fréscopa ofrecen una amplia gama de productos relacionados con el café, lo que permite a los clientes explorar y mejorar sus rituales de café. Fréscopa ofrece desde equipos de elaboración de cerveza hasta accesorios artesanales, una tienda de todo tipo para los aficionados al café que buscan calidad y comodidad.

El compromiso de Fréscopa con la excelencia se extiende más allá de sus productos, ya que la empresa se dedica a crear un recorrido de cliente agradable y sin fisuras. La combinación de tecnologías innovadoras y un enfoque centrado en el cliente posiciona a Fréscopa en la vanguardia de la industria del café en evolución. En esencia, Fréscopa encarna la fusión de la pasión y la tecnología, redefiniendo la forma en que los individuos experimentan y disfrutan su café. Con un enfoque en la calidad, conveniencia y ofertas personalizadas, Fréscopa invita a los entusiastas del café a embarcarse en un recorrido de sabor, entregado a la puerta de su casa.
