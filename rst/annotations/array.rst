.. _ann_array:

Array type
-------------------

.. note::
    可以利用 ``MY_TYPE[]`` 的方式来标注一个数据类型为数组

* Usage：

::

---@type MY_TYPE[] [@comment]

* Example:

    .. code-block:: lua
        :linenos:
        :emphasize-lines: 1

        ---@type Car[]
        local list = {}

        local car = list[1]
        -- car. [Completion shows here]

        for i, car in ipairs(list) do
            -- car. [Completion shows here]
        end

.. seealso::
    :ref:`ann_type`