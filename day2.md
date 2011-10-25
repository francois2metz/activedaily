# ActiveDaily #2

ActiveSupport Duration permet de manipuler d'une manière plutôt sympathique le temps.

    require 'active_support/all' # violent mais efficace, sinon require 'active_support/core_ext/object' et require 'active_support/duration'

    1.month.ago # months, days/day, hour/hour ...
    1.month.since(2.hours.ago) # Calcul simple
    (1.month + 1.day).ago

Le calcul simple ou la configuration de date devient plus lisible.

Devise l'utilise par exemple pour configurer le délai maximum de confirmation de l'email:

    config.confirm_within = 2.days
