====================
 Animation effects
====================

.. _nativeeffects:

---------------
 Native effects
---------------

Native effects a gathered in the enumeration ``pygame_animations.Effects``:

+--------------------------+--------------------------------------------------+
|``Effects.linear``        | constant speed                                   |
+--------------------------+--------------------------------------------------+
|``Effects.sin_in``        | acceleration, from the softest to the hardest    |
|                          |                                                  |
|``Effects.square_in``     |                                                  |
|                          |                                                  |
|``Effects.cubic_in``      |                                                  |
|                          |                                                  |
|``Effects.quad_in``       |                                                  |
+--------------------------+--------------------------------------------------+
|``Effects.sin_out``       | decceleration, from the softest to the hardest   |
|                          |                                                  |
|``Effects.square_out``    |                                                  |
|                          |                                                  |
|``Effects.cubic_out``     |                                                  |
|                          |                                                  |
|``Effects.quad_out``      |                                                  |
+--------------------------+--------------------------------------------------+
|``Effects.sin_in_out``    | acceleration at first then decceleration, from   |
|                          | the softest to the hardest                       |
|``Effects.square_in_out`` |                                                  |
|                          |                                                  |
|``Effects.cubic_in_out``  |                                                  |
|                          |                                                  |
|``Effects.quad_in_out``   |                                                  |
+--------------------------+--------------------------------------------------+
|``Effects.sin_shake``     | go back and forth with decreasing amplitude      |
+--------------------------+--------------------------------------------------+
|``Effects.bounce_in``     | bounce at the start                              |
+--------------------------+--------------------------------------------------+
|``Effects.bounce_out``    | bounce at the end                                |
+--------------------------+--------------------------------------------------+
|``Effects.bounce_in_out`` | bounce at the start and at the end               |
+--------------------------+--------------------------------------------------+

.. Tip:: ``Effects`` being an enumeration, you can use it in a ``for in`` loop, and the effect ``Effects.linear`` can also be accessed by doing ``Effects["linear"]`` or ``Effects[0]`` (They're not in the right order it the table above though).

----------------------
 Custom effects
----------------------

.. _customeffects:

An object that match the next requirements can be used as an effect:

- callable (function, lambda expression, ...)
- takes one parameter, of type ``float``, between 0 (included) and 1 (included)
- returns a ``float``

The parameter is the progression *in time* of the animation (from 0 at the start to 1 at the end).

The returned value is the progression in the animation (0 is the initial state and 1 is the final state). It should begin at 0 and end at 1 (exception: ``Effects.sin_shake`` wich come back 0).
