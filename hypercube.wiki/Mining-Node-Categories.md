
![f1]

The miners extensively use pipelining, which is prevalent in CPU architecture. If there's a stream of input data that must be processed through a sequence of steps, and distinct hardware is accountable for each, the tool that will best suit the task is pipeline. An exemplary usage would be doing multiple loads of laundry by washing, drying, and folding everything in a washer and dryer. One machine dries, one machine folds, and another machine washes. To increase productivity, it is important to design a staged pipeline. We'll classify the washer, dryer, and folding procedure as different stages of the folding process. You finish a load of laundry by adding a second load to the washer after it has been put in the dryer. Next, after the second load has finished drying and the first is being folded, the third is being put in the washer. It's possible to do three loads of laundry all at once if one goes about it like this. On a day when the pipeline has to process an unlimited number of loads, the pipeline will finish every load at the speed of the slowest step in the pipeline.

A total of two processes in the miner are pipelined: the TxCreator works in alphanode mode, and the TxSigner works in miner mode. There is no difference in hardware and the equipment which is pipelined for both sets of scenarios: network input, GPU cards, CPU cores, disk writing, and network output. What it does is unlike the competition. The TxCreator's purpose is to produce entries in the ledger, whereas the TxSigner's is to confirm them.

## TxCreator

![f2]

## TxSigner

![f3]


## TxSyncor


![f4]


[f1]: https://i.imgur.com/dmmkEEv.png

[f2]: https://i.imgur.com/GzrWI9z.png

[f3]: https://i.imgur.com/gN9kHJ0.png

[f4 ]: https://i.imgur.com/XpkgEb6.png