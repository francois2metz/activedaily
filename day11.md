ActiveDaily #11

Les observers permettent de réagir à des actions d'une autre classe. Cela permet de découpler facilement deux composants.
Dans la class Observé, il faut simplement appelé notify_observers.

    require 'active_model'

    class Norris
      include ActiveModel::Observing

      def kick
        notify_observers(:before_kick)
        puts 'BIMMMMMMMMM!'
        notify_observers(:after_kick)
      end
    end

    class NorrisObserver < ActiveModel::Observer
      def before_kick(norris)
         puts "start the video recording"
      end

      def after_kick(norris)
        puts "switch off the video recording"
      end
    end

    Norris.observers = NorrisObserver
    Norris.instantiate_observers
    chuck = Norris.new
    chuck.kick

On arrive rapidement a avoir un comportement similaire. Seule petite déconvenue, je pensais que ActiveModel::Observing se branchait sur les callbacks.

http://rubydoc.info/gems/activemodel/3.1.1/ActiveModel/Observer
http://rubydoc.info/gems/activemodel/3.1.1/ActiveModel/Observing/ClassMethods
