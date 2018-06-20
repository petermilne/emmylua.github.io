.. _ann_fun:

Function type
-------------------

.. note::
    可以利用 ``fun(param:MY_TYPE):RETURN_TYPE`` 的方式来标注一个数据类型为函数

* Usage:

::

---@type fun(param:MY_TYPE):RETURN_TYPE

* Example:

    .. code-block:: lua
        :linenos:
        :emphasize-lines: 1, 7

        ---@type fun(key:string):Car
        local carCreatorFn1

        local car = carCreatorFn1('key')
        -- car. [Completion shows here]

        ---@type fun():Car[]
        local carCreatorFn2

        for i, car in ipairs(carCreatorFn2()) do
            -- car. [Completion shows here]
        end

.. seealso::
    :ref:`ann_type`