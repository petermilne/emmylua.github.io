.. _ann_class:

@class class declaration
------------------------

.. note::
    EmmyLua利用 ``@class`` 注解来模拟面向对象中的类，可以继承，可以定义字段/属性

    .. image:: /images/annotation/class1.png

* Usage:

::

--@class MY_TYPE[:PARENT_TYPE] [@comment]

* Targets：

    + local variables
    + global variables

* Example:

    .. code-block:: lua
        :linenos:
        :emphasize-lines: 1

        ---@class Car : Transport @Declare class Car, inherited from Transport
        local cls = class()

        function cls:test()
        end

* Example spec：

    Declare ``cls`` as new class ``Car``, so we can use annotation ``@type`` to mark variable's type, used to improve code completions and other features

.. seealso::
    :ref:`ann_type`