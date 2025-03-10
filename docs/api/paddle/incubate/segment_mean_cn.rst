.. _cn_api_incubate_segment_mean:

segment_mean
-------------------------------

.. py:function:: paddle.incubate.segment_mean((data, segment_ids, name=None)


分段求均值函数。

此运算符，将 ``segment_ids`` 中相同索引对应的 ``data`` 的元素，进行求均值操作。其中 ``segment_ids`` 是一个单调非减序列。
具体而言，该算子计算一个 Tensor ``out``，使得

.. math::

    out_i = \mathop{mean}_{j \in \{segment\_ids_j == i \} } data_{j}

其中求均值的索引 ``j``，是符合 ``segment_ids[j] == i`` 的所有 ``j`` 。


参数
:::::::::
    - **data** (Tensor) - 张量，数据类型为 float32、float64。
    - **segment_ids** (Tensor) - 一维张量，与输入数据`data`的第一维大小相同，表示`data`分段位置，单调非减。合法的数据类型为 int32、int64。
    - **name** (str，可选) - 具体用法请参见 :ref:`api_guide_Name`，一般无需设置，默认值为 None。

返回
:::::::::
    Tensor，分段求均值的结果。空的 segment_id 对应的默认值为 0。

代码示例
:::::::::

COPY-FROM: paddle.incubate.segment_mean
