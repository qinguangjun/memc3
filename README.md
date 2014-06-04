MemC3
=====

MemC3 is an in-memory key-value cache, derived from Memcached but improved with memory-efficient and concurrent data structures. MemC3 applies multi-reader concurrent cuckoo hashing  as its key-value index and CLOCK-replacement algorithm as cache eviction policy. As a result, MemC3 scales better, runs faster, and uses less memory. For details about the algorithms, performance evaluation and citations, please refer to [our paper in NSDI 2013][1]. For a re-engineered fast, concurrent, stand-alone implementation of concurrent cuckoo hash table, please check our [efficient/libcukoo repository](https://github.com/efficient/libcuckoo).

   [1]: http://www.cs.cmu.edu/~dga/papers/memc3-nsdi2013.pdf "MemC3: Compact and Concurrent Memcache with Dumber Caching and Smarter Hashing"

Authors
======= 

MemC3 is developed by Bin Fan, David G. Andersen, and Michael Kaminsky. You can also email us at [libcuckoo-dev@googlegroups.com](mailto:libcuckoo-dev@googlegroups.com).

Building
==========

    $ autoreconf -fis
    $ ./configure
    $ make

Benchmark
=========

In our [NSDI paper][1], memc3 are benchmared using workloads gerenated by [Yahoo YCSB][2]. Note that, YCSB is designed to benchmark the performance of cloud file systems and it will become the bottleneck if it is used directly to benchmark memc3 or memcached. Therefore, we pre-generate workloads (using script ``bench/ycsb_workloads_gen.sh`` which reads settings in ``bench/ycsb_workloads_settings``).

  [2]: dl.acm.org/citation.cfm?id=1807152 "Benchmarking cloud serving systems with YCSB" 
