# ActiveDaily #10

Cette semaine on se concentre sur ActiveModel, alors on installe un nouveau joyau:

    gem install activemodel

Et puis on essaie de l'inclure.

    require 'active_model' # Un underscore mais pas de /all

ActiveModel est la base d'ActiveRecord mais aussi de mongoid, tire, datamapper, redis_orm, ...

Si les callbacks d'ActiveSupport sont un peu rude, ceux d'ActiveModel sont plus sympa.

    require 'active_model'

    class Bim
      extend ActiveModel::Callbacks
      # On déclare les callbacks disponibles
      define_model_callbacks :kick

      # L'implémentation
      def kick
        run_callbacks :kick do
          puts 'BIMMMMMMMMM!'
        end
      end
    end

    class Norris < Bim
      # on rajoute les callbacks
      before_kick :before_kick
      after_kick :after_kick
      # on peut aussi utiliser around_kick :ma_methode

      def before_kick
        puts 'Be careful'
      end

      def after_kick
        puts 'KO'
      end
    end

    chuck = Norris.new
    chuck.kick # Your are KO baby

Alors n'hésitez pas a rajouter des callbacks dans vos classes.

http://rubydoc.info/gems/activemodel/3.1.1/ActiveModel/Callbacks
