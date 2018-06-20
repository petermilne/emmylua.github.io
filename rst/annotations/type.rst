.. _ann_type:

@type type annotation
---------------------

.. note::

    Use annotation ``@type`` to mark variable's type, used to improve code completions and other features

    .. image:: /images/annotation/type1.gif

* Usage:

::

  ---@type MY_TYPE[|OTHER_TYPE] [@comment]


* Targets:

    + local variables

    .. code-block:: lua
        :linenos:
        :emphasize-lines: 1, 4

        ---@type Car @mark local variable's type
        local car1 = {}

        ---@type Car|Ship @交通工具，车或者船。因lua脚本的灵活性，一个变量可能对应多个类型，
        ---用|符号列出可能的类型
        local transport = {}

    + global variables

    .. code-block:: lua
        :linenos:
        :emphasize-lines: 1
        
        ---@type Car @mark global variable's type
        global_car = {}

    + propertys

    .. code-block:: lua
        :linenos:
        :emphasize-lines: 2

        local obj = {}
        ---@type Car @mark property's type
        obj.car = getCar()

.. seealso::
    :ref:`ann_class`