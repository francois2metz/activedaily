# ActiveDaily #8

Il peut être pratique de filtrer les clés d'un Hash.

    require 'active_support/core_ext/hash/slice'

    hash = Hash.new
    hash['chuck'] = 'norris'
    hash['bruce'] = 'lee'
    hash['roger'] = 'hanin' # my real idol
    hash.slice('bruce', 'roger')

D'ailleurs vous pouvez le combinez avec le HashWithIndifferentAccess.

    hash.with_indifferent_access.slice(:bruce, :roger)
