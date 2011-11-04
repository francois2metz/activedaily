# ActiveDaily #9

Si vous en avez assez de tester sans cesse si la variable que vous avez est nil, vous pouvez utiliser try.

    require 'active_support/core_ext/object'

    a = nil
    a.try(:size) # nil
    b = "plop"
    b.try(:size) # 4
