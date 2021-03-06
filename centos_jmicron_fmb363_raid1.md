[基于JMicron JMB363在CentOS上架设 RAID 的问题](http://zengrong.net/post/2009.htm)

## 配置

主板： [MSI EFINITY][1]
CPU： Intel Core2
内存： 金士顿DDR2 800 2Gx2
硬盘：希捷 500Gx1 做主盘安装操作系统。500G硬盘分成3个区，50G挂载 /， 4G挂载为交换分区， 剩余400G挂载为 /home。
操作系统：CentOS 6.1

## 需求

购买了2块希捷4T做RAID1，当作数据盘。

系统已经运行2年，我不希望重装操作系统，RAID1的磁盘仅做数据盘使用，分成1个4TB分区。

## 已经完成的步骤

主板上自带 JMicron JMB363 芯片，支持RAID0/1/JBOD。JMB363提供的2个SATA2口连接2块4T硬盘。

我已经使用主板BIOS中自带的JMicro工具将2块4T硬盘组成了一个 RAID Disk Drive。见下图：

![][/wp-content/uploads/2013/12/jmicron.jpg]

根据 jimicron 提供的 [FAQ][3]，Linux内核已经自带了JMB363的驱动。

而要让CentOS支持RAID硬盘，需要使用 [dmraid][2] 工具。[这篇文章][4] 详细介绍了该工具的用法。

## 问题

使用 jmiron 虚拟出来的RAID设备，使用 parted 只能认到1.8T，即使是使用 GPT 分区表也是如此。

最终我放弃了使用硬RAID，而改为使用软RAID。见 [4TB HDD + RAID1 on CentOS 6.1][6] 。

## 参考

* [How to Create Partition on Linux for >2TB Size using Parted GPT][5]
* [dmraid的介绍][4]

[1]: http://cn.msi.com/product/mb/EFINITY.html
[2]: http://people.redhat.com/~heinzm/sw/dmraid/
[3]: http://www.jmicron.com/Support_FAQ.html
[4]: http://book.51cto.com/art/200902/110753.htm
[5]: http://www.thegeekstuff.com/2012/08/2tb-gtp-parted/
[6]: http://zengrong.net/post/2014.htm
