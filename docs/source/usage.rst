============================
 How to use the package
============================

--------------------------------
 Include th package with pygame
--------------------------------

Import the package
==================

*After* importing ``pygame``, import the package by doing

.. code-block:: python
    
    import pygame_animations

The name is a bit long, so it's better if you import it as :

.. code-block:: python
    
    import pygame_animations as anim


Call ``update_animation``
============================

Then, the only thing needed for the package to work is to call

.. code-block:: python
    
    anim.update_animations()

at each frame. It's better to call it before drawing anything.

----------------------
 Making animations
----------------------

To make an animation, create a ``pygame_animations.Animation`` object and call its ``start()`` method to run it.

Example : move a sprite
===========================

The following code will move ``mysprite`` to x=200 in 2 seconds :

.. code-block:: python
    
    anim.Animation(mysprite, 2, rect__x=200).start()


``mysprite`` is the object to animate. In this example, it's a ``pygame.sprite.Sprite``but you can target any object.


``2`` is the duration of the animation, in seconds. You can also pass a float, and the duration will be rounded to the millisecond.


``rect__x=200`` is the property to animate (here ``mysprite.rect.x``).
Note that the ``__`` replace ``.`` to animate sub-properties, for example ``a.b.c`` becomes ``a__b__c``.
You can animate as many properties as you want. 

-----------------------------
 Complete example : a "Hello World"
-----------------------------

.. code-block:: python
    
    import pygame
    import pygame_animations as anim
    
    pygame.init()
    
    surface = pygame.display.set_mode((640, 480))
    
    font = pygame.font.SysFont('default', 52)
    
    class MySprite (pygame.sprite.Sprite):
        def __init__(self):
            super().__init__()
            self.image = font.render("Hello, World!", 1, (255, 255, 255))
            self.rect = self.image.get_rect()
    label = MySprite()
    group = pygame.sprite.Group(label)
    
    a = anim.Animation(label, 2, anim.Effects.cubic_in_out, rect__x=640-label.rect.w, rect__y=480-label.rect.h)
    
    clock = pygame.time.Clock()
    running = True
    
    while running:
        for ev in pygame.event.get():
            if ev.type == pygame.QUIT:
                running = False
        
        t = pygame.time.get_ticks()
        if t>3000 and a.can_run(): # the animation starts after 3 secs
        a.start()
        
        anim.update_animations()
        
        surface.fill((0, 0, 0))
        group.draw(surface)
        
        pygame.display.flip()
        clock.tick(30)
    
    pygame.quit()
