# Hardware Specification

## Generic Requirement

- CPU 
    - 8 core or more
    - 2.0 GHZ or faster

    To mine, you'll need a high-end CPU, at least 8 cores. We would really encourage a model that supports Intel SHA Extensions: Zen for AMD, or Ice Lake for Intel. A substantial slowdown is caused by the lack of SHA Extensions.

***

- RAM
    - 128 GB or more

    At the absolute minimum, you will need 128 GB of RAM. On an extremely fast NVMe SSD storage medium, you should also have 256 GiB of swap for extra space.

***

- Disk
    - 1TB or More

    Miner activities can be hindered by slower drives, which can result in their performance issues. In one instance, a 32GiB drive was increased to about 480GiB. The HyperCube network's 100 GiB of settings must be read and confirmed in order to activate the Miner. Above, you'll remember we discussed how RAM issues have to be handled by way of an exceptional swap disk or an efficient file system.

    We advise that, to avoid storing frequently accessed content in cache more than necessary, at least 1TiB of NVMe cache space should be allotted. HyperCube parameters and other general data should be stored on this disk, as it's needed for caching data during the sealing process.

***

- GPU
    - 1660s with 6GB  Memory or Better

***
    A powerful GPU is recommended as it can significantly speed up SNARK computations.  


## Whitelabel Machine

We have provided a list of throughly tested rig spec which will highly increase the output of miner machine. Usually miner rigs in the white list are usually much superior in terms of output.


## Cloud Mining

It is feasibile to run a HyperCube miner on the cloud, although it is much cost-efficient ot run a bare metal.