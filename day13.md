# ActiveDaily #13

Dirty vous aide a tracer les changements dans un objet.

    require 'active_model'

    class Norris
      include ActiveModel::Dirty # Chuck Norris cannot be dirty, should throw an exception

      define_attribute_methods [:first_name]
      attr_reader :first_name

      def first_name=(val)
        first_name_will_change! unless val == @first_name
        @first_name = val
      end
    end

    chuck = Norris.new
    chuck.first_name = 'plop'
    chuck.changes
    chuck.changed_attributes

Vous avez ainsi accès à quelques méthodes:

    chuck.changed? # true
    chuck.first_name_changed? # true
    chuck.first_name_was # nil

http://rubydoc.info/gems/activemodel/3.1.1/ActiveModel/Dirty

C'est le dernier ActiveDaily. Je préfère m'arrêter sur un numéro 13.

Vous avez raté:

* des choses dans ActiveModel::AttributeMethods utilisé entre autre par ActiveModel::Dirty
* ActiveSupport::Concern qui facilite l'écriture de mixins
* ActiveSupport::Inflector qui permet de transformer des mots du singulier au pluriel et d'autres truc aussi
* Hash#except, l'inverse de Hash#slice
* ActiveSupport::Notifications avec lequel je n'ai pas encore joué
