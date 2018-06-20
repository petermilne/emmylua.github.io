.. _ann_dict:

Dictionary type
-------------------

.. note::
    Use ``table<KEY_TYPE, VALUE_TYPE>`` to mark variables as dictionary (similar to Dictionary<K,V> in C# or Map<K,V> in Java)

* Usage:

::

---@type table<KEY_TYPE, VALUE_TYPE>

* Example:

    .. code-block:: lua
        :linenos:
        :emphasize-lines: 1

        ---@type table<string, Car>
        local dict = {}

        local car = dict['key']
        -- car. [Completion shows here]

        for key, car in pairs(dict) do
            -- car. [Completion shows here]
        end

.. seealso::
    :ref:`ann_type`