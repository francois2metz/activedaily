# ActiveDaily #3

Les HashWithIndifferentAccess permettent de manipuler les clés indifféremment avec un symbole ou la clé originale.

     require 'active_support/hash_with_indifferent_access'

     h = HashWithIndifferentAccess.new # {}
     h[:chuck] = "Norris" # "Norris"
     h[:chuck] # "Norris"
     h["chuck"] # "Norris"

On me dit que c'est utilisé entre autre pour le hash *params* dans Rails.
