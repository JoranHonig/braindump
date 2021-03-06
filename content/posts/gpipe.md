+++
title = "Gpipe"
author = ["Jethro Kuan"]
lastmod = 2020-05-31T20:19:57+08:00
draft = false
+++

Gpipe is a scalable pipeline parallelism library published by Google
Brain, which allows for efficient training of large, memory-consuming
models <a id="f5a07e10ad91af167044009928ccf64f" href="#huang18_gpipe">(Huang et al., 2018)</a>. Pipeline parallelism allows for
[Fast Neural Network Training]({{< relref "fast_nn_training" >}}).

In Gpipe, neural networks with sequential layers are partitioned
across accelerators. The pipeline parallelism divides each input
mini-batch into smaller micro-batches, enabling different accelerators
to work on different micro-batches simultaneously. This is especially
useful in [Large Batch Training]({{< relref "large_batch_training" >}}).

{{< figure src="/ox-hugo/screenshot2020-02-05_23-05-00_.png" >}}

# Bibliography

<a id="huang18_gpipe" target="_blank">Huang, Y., Cheng, Y., Bapna, A., Firat, O., Chen, M. X., Chen, D., Lee, H., …, _Gpipe: Efficient training of giant neural networks using pipeline parallelism_, CoRR, _()_, (2018). </a> [↩](#f5a07e10ad91af167044009928ccf64f)
