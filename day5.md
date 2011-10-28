# ActiveDaily #5

Vous avez envie de poser des questions à vos chaines de caractères ? StringInquirer est fait pour cela.

     require 'active_support/all'

     chuck = "norris".inquiry # équivalent a ActiveSupport::StringInquirer.new("norris")
     chuck.norris? # true
     chuck.other? # false

Vous savez désormais comment fonctionne l'interrogation de la *production?*.
