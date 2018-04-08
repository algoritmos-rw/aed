---
layout: page
title: TPs
permalink: /tps/
---
{% assign hoy = site.time | date: "%Y-%m-%d" %}
{% assign expiracion = site.data.cuatrimestre.fin_cuatrimestre | date: "%Y-%m-%d" %}

TPs
=======

A continuación encontrarán las entregas que iremos planteando a lo largo de la
materia.

{: .table .table-striped}
| **TP**       | **Código**      | **Fecha de entrega** |{% for tp in site.data.trabajos %}{% assign comienzo = tp.publicacion | date: "%Y-%m-%d" %}{% if hoy > comienzo and hoy < expiracion %}
|[{{tp.id}}]({{tp.enunciado_link | relative_url}}) | [{{tp.zip}}]({{tp.zip_link}}) | {{tp.entrega}}{% endif %}{% endfor %}