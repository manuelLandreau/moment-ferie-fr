Moment-ferie-fr  [![Build Status](https://travis-ci.org/DepthFrance/moment-ferie-fr.svg?branch=master)](https://travis-ci.org/DepthFrance/moment-ferie-fr)
==================================================

Plug-in [Moment.js][1] jours feriés en France


exemple utilisation:
-----------

    var day = moment("9-6-2014", "DD-MM-YYYY");

    console.log( day.isFerie() );  // boolean
    console.log( day.getFerie() ); // string, 'Pentecôte'

    console.log( day.getFerieList() ); // array, liste jours feriés de l'année de day
    console.log( moment().getFerieList(2018) );  // array, liste jours feriés de l'année 2018

    console.log( day.lundiDePaques() ); // momentObj, jour de paques de l'année de day
    console.log( moment().lundiDePaques(2018) ); // momentObj, jour de paques de l'année 2018

    /*
    idem pour:

      day.paques();
      day.lundiDePaques();
      day.ascension();
      day.pentecote();

      day.jourDeLAn();
      day.feteDuTravail();
      day.victoireDeAllies();
      day.feteNationale();
      day.assomption();
      day.toussaint();
      day.armistice();
      day.noel();
    */

Particularité sur les jours fériés
-----------
    var saintEtienne = moment("26-12-2020", "DD-MM-YYYY");

    console.log( day.isFerie() );  // boolean, false
    console.log( day.isFerie(57) );  // boolean, true (pour les départements 57, 67, 68)
    console.log( day.getFerie(57) ); // string, 'Saint-Étienne'
    console.log( day.getFerieList('2020', 57) ); // [..., { name: "Saint-Étienne", date: Date }]

    To do: 
        - Vendredi Saint (pour les communes des départements 57, 67, 68)
        - Abolition de l’esclavage :
            - Guadeloupe : 27 mai 
            - Guyane : 10 juin 
            - Martinique : 22 mai
            - Mayotte : 27 avril
            - La Réunion : 20 décembre
            - Saint Barthélemy : 9 octobre
            - Saint Martin : 27 mai
        - Autres en Guadeloupe, Martinique et Guyane :
            - le lundi gras,
            - le mardi gras,
            - le mercredi des cendres.

        Le vendredi saint, le jour des défunts et la Mi-Carême sont également fériés en Guadeloupe.


  [1]: http://momentjs.com/
