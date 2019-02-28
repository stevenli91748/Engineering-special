# 目录
* [Docker概述](#Docker概述)

# 内容
## Docker概述

当我们使用了微服务架构后，我们将一个原本完整的系统，按照业务逻辑拆分成一个个可独立运行的子系统。为了降低系统间的耦合度，我们希望这些子系统能够运行在
独立的环境中，这些环境之间能够相互隔离。

在Docker出现之前，若使用虚拟机来实现运行环境的相互隔离的话成本较高，虚拟机会消耗较多的计算机硬件/软件资源。Docker不仅能够实现运行环境的隔离，而且能
极大程度的节约计算机资源，它成为一种轻量级的“虚拟机”。