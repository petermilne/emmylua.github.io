Remote Debug 远程调试
========================================

.. hint::
    说明：远程调试通信基于socket，内核基于mobdebug.lua ，依赖于luasocket模块，所以被调试的程序需要支持luasocket
    
    远程调试要先启动，再启动目标程序

1. 执行步骤
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* 配置Remote调试设置，点击右上角 ``Edit Configurations``

.. image:: /images/debug/remote/debug-config.png

* 点击 ``+`` 选择并创建 ``Lua Remote(Mobdebug)`` 配置

.. image:: /images/debug/remote/debug-config2.png

* 设置好相关参数后点击OK

.. image:: /images/debug/remote/debug-config3.png

* 点击右上角debug按钮

.. image:: /images/debug/remote/debug-config4.png

* 注意IDEA控制台LOG输出，如下图所示表示启动

.. image:: /images/debug/remote/debug-config5.png

* 下载 ``mobdebug.lua`` 并在目标程序的lua代码入口处添加代码

.. code-block:: lua
    :linenos:

    require("mobdebug").start()

或者

.. code-block:: lua
    :linenos:
    
    require("mobdebug").start("host-ip", port) --默认值为 "localhost", 8172
    
* 最后启动目标程序，并注意IDEA控制台窗口，出现下图所示`Connected`则表示调试器连接成功并可以添加断点并调试了

.. image:: /images/debug/remote/debug-config6.png

2. 失败相关问题排查
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* 运行目标程序后控制台并没有出现`Connected`日志

    * 确认目标程序包含luasocket模块
    * 确认调试端口一致（默认是8172端口）

* ``Connected`` 日志有，但断点无效

    * 检查 ``Sources`` 目录设置正确
    * 检查目标程序在运行时提供的文件名与源码文件的文件名一致（致少除了后缀名的前面的部分一致）
    
        此项检查快捷方式是在 ``mobdebug.lua`` 的

        .. code-block:: lua
            :linenos:

            local function has_breakpoint(file, line)

        函数中打印输出 ``file``