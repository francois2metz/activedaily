ActiveDaily #4

Pour générer des tokens d'accès et vérifier leur authenticité, MessageVerifier
est fait pour vous.

    require 'active_support/message_verifier'

    v = ActiveSupport::MessageVerifier.new("houhou this is a secret")
    token = v.generate(["chuck", "norris"]) # you get an unreadable string
    chuck, norris = v.verify(token)

Dans le cas d'un token qui a été modifié, la signature devient invalide, une exception est alors jeté.

    ActiveSupport::MessageVerifier::InvalidSignature

Dans un contexte Rails, vous pouvez utiliser le secret_token de l'application :

    ActiveSupport::MessageVerifier.new(Rails.configuration.secret_token)

Si vous devez encore plus protéger les données, vous pouvez utiliser MessageEncryptor qui dispose d'une API similaire.
