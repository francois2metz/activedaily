# ActiveDaily #6

Les callbacks permettent de facilement rajouter des points d'entrées dans vos classes.

    require 'active_support/callbacks.rb'

    class Bim
      include ActiveSupport::Callbacks
      define_callbacks :kick

      def kick
        run_callbacks :kick do
          puts 'BIMMMMMMMMM!'
        end
      end
    end

    class Norris < Bim
      set_callback :kick, :before, do |chuck|
        puts 'Be careful'
      end

      set_callback :kick, :after do |chuck|
        puts 'KO'
      end
    end

    chuck = Norris.new
    chuck.kick # Your are KO baby

Bon dans Rails toute cette logique est utilisé dans ActiveModel, rendez vous la semaine prochaine :).
