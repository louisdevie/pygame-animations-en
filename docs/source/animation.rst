===================
 Animation Classes
===================

---------------------
 The Animation class
---------------------

.. class:: pygame_animations.Animation(target, duration[, effect] [, flag=None], **attrs)

    An animation.
    
    :Parameters:
        - **target** *(object)*: the object to animate.
        - **duration** *(int, float)*: duration of the animation, in seconds.
        - **effect** *(callable)*: effect applied to the animation. It can be a :ref:`native effect <nativeeffects>` or a :ref:`custom one <customeffects>`.
        - **flag** : used to track the animation. Anything can be used, and a same flag can be used on different animations.
        - **attrs** : properties to animate. To select a sub-property ``a.b.c``, use ``a__b__c``
    
    .. attribute:: target
        
        (Read-only) The object targeted by the animation.
    
    .. attribute:: duration
        
        (Read-only) Duration of the animation, converted and rounded to millisecondes.
    
    .. function:: start()
        
        Starts the animation. It can only be called once.
        
        :Parameters: None
        
        :Returns: ``None``

    .. _stopmethod:

    .. function:: stop([noerror=False])

        Stop the animation and leave the animated object as it is. Once stopped, it cannot be resumed.
        
        :Parameters:
            - **noerror** *(bool)*: when the method is called on an animation that is not running, ignore if set to ``True`` or raise a ``RuntimeError`` if set to ``False``.
        
        :Returns: ``None``

    .. _cancelmethod:

    .. function:: cancel([noerror=False])

        Same as :ref:`stop() <stopmethod>`, but put the animated object back in it's initial state.

        :Parameters:
            - **noerror** *(bool)*: see :ref:`stop() <stopmethod>`
        
        :Returns: ``None``

    .. _fastforwardmethod:

    .. function:: fastforward([noerror=False])

        Same as :ref:`stop() <stopmethod>`, but put the animated object directly in it's final state.

        :Parameters:
            - **noerror** *(bool)*: see :ref:`stop() <stopmethod>`
        
        :Returns: ``None``
        
    .. function:: is_running()

        Returns ``True`` if the animation is running.
        
        :Parameters: Aucuns
        
        :Returns: ``bool``
        
    .. function:: can_run()

        Returns ``True`` if the animation hasn't been started yet.
        
        :Parameters: Aucuns
        
        :Returns: ``bool``


-----------------------------
 The AnimationSequence class
-----------------------------

.. class:: pygame_animations.AnimationSequence(a, b, [*others] [, flag=None])
    
    Inherits from ``pygame_animations.Animation``

    Multiple animations run one after another.
    A sequence can be created by adding animations together : ``anim1 + anim2 + anim3`` gives ``AnimationSequence(anim1, anim2, anim3)``
    
    :Parameters:
        - **a**, **b** and **others** *(Animation)*: animations of the sequence
        - **flag** : used to track the animation. Anything can be used, and a same flag can be used on different animations.
    
    .. attribute:: animations
        
        (Read-only) The animations of the sequence.
    
    .. attribute:: duration
        
        (Read-only) The duration of the sequence, equal to the sum of all the animations.
    
    .. function:: start()
        
        Starts the animation. It can only be called once.
        
        :Parameters: None
        
        :Returns: ``None``

    .. _stopsequence:

    .. function:: stop([noerror=False])

        Stops the sequence and call :ref:`stop() <stopmethod>` on all the animations.
        
        :Parameters:
            - **noerror** *(bool)*: when the method is called on an animation that is not running, ignore if set to ``True`` or raise a ``RuntimeError`` if set to ``False``.
        
        :Returns: ``None``

    .. _cancelsequence:

    .. function:: cancel([noerror=False])

        Same as :ref:`stop() <stopsequence>`, but call :ref:`cancel() <cancelmethod>` on all the animations.

        :Parameters:
            - **noerror** *(bool)*: see :ref:`stop() <stopsequence>`
        
        :Returns: ``None``

    .. _fastforwardsequence:

    .. function:: fastforward([noerror=False])

        Same as :ref:`stop() <stopsequence>`, but call :ref:`fastforward() <fastforwardmethod>` on all the animations.

        :Parameters:
            - **noerror** *(bool)*: see :ref:`stop() <stopsequence>`
        
        :Returns: ``None``
        
    .. function:: is_running()

        Returns ``True`` if the animation is running.
        
        :Parameters: None
        
        :Returns: ``bool``
        
    .. function:: can_run()

        Returns ``True`` if the animation hasn't been started yet.
        
        :Parameters: None
        
        :Renvoie: ``bool``


-----------------------
 Classe AnimationGroup
-----------------------

.. class:: pygame_animations.AnimationGroup(a, b, [*others] [, flag=None])
    
    Inherits from ``pygame_animations.Animation``

    Multiple animations run together.
    A group can be created by using the ``&`` operator between animations : ``anim1 & anim2 & anim3`` gives ``AnimationGroup(anim1, anim2, anim3)``
    
    :Parameters:
        - **a**, **b** and **others** *(Animation)*: the animations of the group
        - **flag** : used to track the animation. Anything can be used, and a same flag can be used on different animations.
    
    .. attribute:: animations
        
        (Read-only) The animations of the group.
    
    .. attribute:: duration
        
        (Read-only) The duration of the group, equal to the longest duration of the animations.
    
    .. function:: start()
        
        Starts the animation. It can only be called once.
        
        :Parameters: None
        
        :Returns: ``None``

    .. _stopgroup:

    .. function:: stop([noerror=False])

        Stops the group and call :ref:`stop() <stopmethod>` on all the animations.
        
        :Parameters:
            - **noerror** *(bool)*: when the method is called on an animation that is not running, ignore if set to ``True`` or raise a ``RuntimeError`` if set to ``False``.
        
        :Returns: ``None``

    .. _cancelgroup:

    .. function:: cancel([noerror=False])

        Same as :ref:`stop() <stopgroup>`, but call :ref:`cancel() <cancelmethod>` on all the animations.

        :Parameters:
            - **noerror** *(bool)*: see :ref:`stop() <stopgroup>`
        
        :Returns: ``None``

    .. _fastforwardgroup:

    .. function:: fastforward([noerror=False])

        Same as :ref:`stop() <stopgroup>`, but call :ref:`fastforward() <fastforwardmethod>` on all the animations.

        :Parameters:
            - **noerror** *(bool)*: see :ref:`stop() <stopgroup>`
        
        :Returns: ``None``
        
    .. function:: is_running()

        Returns ``True`` if the animation is running.
        
        :Parameters: None
        
        :Returns: ``bool``
        
    .. function:: can_run()

        Returns ``True`` if the animation hasn't been started yet.
        
        :Parameters: None
        
        :Returns: ``bool``
