============
 Events
============

Pygame events are posted whenever an animation starts or end.

This package adds then two event types:

.. attribute:: pygame_animations.ANIMATIONSTARTED
    
    Posted when an animation starts.

    :Event attributes:
        - **animation** : the animation that have been started.
        - **flag** : the ``flag`` of the animation.

.. attribute:: pygame_animations.ANIMATIONENDED
    
    Posted when an animation ends.

    :Event attributes:
        - **animation** : the animation that ended.
        - **flag** : the ``flag`` of the animation.
