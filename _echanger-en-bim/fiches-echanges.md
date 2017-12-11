---
layout: default
group: fiches-echanges
title: Fiches d'échanges
description: Méthodes d'échanges point à point entre logiciels BIM
comments: false
icon: file-text-o
ordre: 1
status: publish
permalink: /echanger-en-bim/fiches-echanges/
---

# Fiches d'échanges BIM point à point

Texte d'introduction...

<div class="row">
  <div class="col-12">
    <p class="text-right"><a class="btn btn-sm btn-secondary" href="/echanger-en-bim/fiches-echanges/nouvelle/" role="button"><i class="fa fa-plus" aria-hidden="true"></i> Ajouter une fiche (éditeurs)</a></p>
  </div>
</div>

<div class="row">
  <div class="col-12">
    <table id="tablefilter" class="table">
      <thead>
        <tr>
          <th></th>
          <th>Source</th>
          <th></th>
          <th>Destination</th>
          <th>Usage-Métier</th>
          <th>Statut</th>
          <th>Mise à jour</th>
        </tr>
      </thead>
      <tbody>
        {% assign fiches_sorted = site.fiches | sort: 'destination_nom' %}
        {% for fiche in fiches_sorted %}
          <tr>
            <td><a class="btn btn-primary btn-sm" href="{{ fiche.url }}" role="button"><i class="fa fa-file-text-o" aria-hidden="true"></i> voir la fiche</a></td>              
            <td><strong>{{ fiche.source_nom }}</strong> / {{ fiche.source_version }}</td>
            <td><i class="fa fa-arrow-right" aria-hidden="true"></i></td>
            <td><strong>{{ fiche.destination_nom }}</strong> / {{ fiche.destination_version }}</td>
            <td>{{ fiche.usage_metier }}</td>
            <td>
              {% if fiche.statut == 'publiée' %}
                <span class="badge badge-success"><i class="fa fa-check-circle-o" aria-hidden="true"></i> {{ fiche.statut }}</span>
              {% endif %}
              {% if fiche.statut == 'relecture' %}
                <span class="badge badge-info"><i class="fa fa-eye" aria-hidden="true"></i> {{ fiche.statut }}</span>
              {% endif %}
              {% if fiche.statut == 'brouillon' %}
                <span class="badge badge-warning"><i class="fa fa-pencil" aria-hidden="true"></i> {{ fiche.statut }}</span>
              {% endif %}
            </td>
            <td><i class="fa fa-clock-o" aria-hidden="true"></i> {{ fiche.maj }}</td>
          </tr>
        {% endfor %}
      </tbody>
    </table>
    
  </div>
</div>
  