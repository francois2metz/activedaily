# ActiveDaily #7

OrderedOptions vous permet de setter des paramètres de config d'une manière assez facile.

    require 'active_support/ordered_options'

    options = ActiveSupport::OrderedOptions.new
    options.chuck = 'norris'
    options[:chuck] # norris

Les options dans Rails sont gérès de cette manière.
