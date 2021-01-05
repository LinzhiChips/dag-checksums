DAG checksums
=============

This repository contains checksums for DAG files for Ethash epochs 0
to 439, and ETChash epochs 190 to 439.


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
