# ActiveDaily #1

Lorsque nous utilisons rails, nous utilisons beaucoup de helpers et objets qui viennent en fait de ActiveSupport.

Alors pendant deux semaines, c'est le ActiveDaily, une astuce par jour dans les méandres de ActiveSupport.

Les exemples ont été testé avec ruby 1.9.2.

Pour bien démarrer :

    gem install activesupport i18n # Oui il faut i18n pour que activesupport fonctionne a peu près correctement
    gem install pry # pour le plaisir

Pour executer les exemples :

    pry # ou irb
    require 'active_support' # oui un underscore :(

Pour savoir si un objet est vide. C'est à dire soit false, empty, contenant seulement des espaces, ...

    require 'active_support/all' # violent mais efficace, sinon require 'active_support/core_ext/object'

    nil.blank? # true
    "".blank? # true
    "\n".blank? # true
    false.blank? # true
    [].blank? # true
    {}.blank? # true
    true.blank? # false
    "Chuck".blank? # false

Vous avez une astuce sous le coude que vous désirez partager ? Envoyez la moi et elle se retrouvera peut être dans un prochain ActiveDaily. Seule les astuces sur ActiveSupport et ActiveModel seront incluse (sauf si vous avez une bonne raison de l'inclure).
