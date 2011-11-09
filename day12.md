# ActiveDaily #12

MassAssignmentSecurity permet de protéger l'écriture de certains attributs en fonction du rôle.
MassAssignmentSecurity fournit deux facons de se protéger. Avec attr_accessible en mode whitelist ou avec attr_protected en mode blacklist.

    require 'active_model'

    class Norris
      include ActiveModel::MassAssignmentSecurity

      attr_accessible :name
      attr_accessible :name, :guns, :as => :chuck_norris

      def update(params, role=:default)
        sanitize_for_mass_assignment(params, role)
      end
    end

    chuck = Norris.new
    p chuck.update({name: 'chuck', guns: 2}) # {name: 'chuck'}
    p chuck.update({name: 'chuck', guns: 2}, :chuck_norris) # {name: 'chuck', guns: 2}

N'oubliez pas protéger vos objets de cette façon, c'est très rapide à mettre en place.

http://rubydoc.info/gems/activemodel/3.1.1/ActiveModel/MassAssignmentSecurity/ClassMethods
