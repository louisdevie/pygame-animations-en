===========
 Functions
===========

.. function:: pygame_animations.update_animations()
    
    Update all running animations. It needs to be called before drawing each frame.
    
    :Parameters: None
    
    :Returns: ``None``

.. function:: pygame_animations.stop_all([flags=None])
    
    Stop all the running animations. See :ref:`Animation.stop <stopmethod>` for more informations.
    
    If ``flags`` is given, stop only the animations that matches these flags. See :ref:`Animation.match <matchmethod>` for more informations.
    
    :Parameters:
        - **flags** *(str)*: See :ref:`Animation.match <matchmethod>`.
    
    :Returns: ``None``

.. function:: pygame_animations.cancel_all([flags=None])
    
    Cancel all the running animations. See :ref:`Animation.cancel <cancelmethod>` for more informations.
    
    If ``flags`` is given, stop only the animations that matches these flags. See :ref:`Animation.match <matchmethod>` for more informations.
    
    :Parameters:
        - **flags** *(str)*: See :ref:`Animation.match <matchmethod>`.
    
    :Returns: ``None``

.. function:: pygame_animations.fastforward_all([flags=None])
    
    Finish all the running animations. See :ref:`Animation.fastforward <fastforwardmethod>` for more informations.
    
    If ``flags`` is given, stop only the animations that matches these flags. See :ref:`Animation.match <matchmethod>` for more informations.
    
    :Parameters:
        - **flags** *(str)*: See :ref:`Animation.match <matchmethod>`.
    
    :Returns: ``None``
