DAG checksums
=============

This repository contains checksums for DAG files for:

Algorithm	Epochs		Last epoch ends on coin
---------	---------	--------------------------
Ethash		  0 - 479	2022-03-24 ETH
ETChash		190 - 439	2027-02-25 ETC
Ubqhash		 22 -  99	2038-02-15 UBQ

DAG growth forecasts from minerstat.com/dag-size-calculator, obtained
2021-07-10. Note that these forecasts are extremely noisy and can jump
by weeks if not months.


File format
-----------

Each checksum file consists of one checksum of 8 bytes for each "chunk"
of the DAG. The checksum of a chunk is the first 8 bytes of the SHA3-256
hash of the chunk. Each chunk is 2^20 bytes, except for the last chunk
in the DAG, which will be shorter.

I.e., the first checksum is for DAG lines 0 to 8191, the second checksum
for DAG lines 8192 to 16383, and so on.

There is a separate checksum file for every DAG. Ethash and ETChash DAGs
differ in size and content.


Purpose
-------

DAG checksums are used by Linzhi Phoenix miners to rapidly verify the
consistency of DAGs. The checksum files are placed in the directory csum/
of the uSD card.
