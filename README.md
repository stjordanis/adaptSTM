# adaptSTM

Transactional memory (TM) is an attractive platform for parallel programs,  and
several software transactional memory (STM) designs have been presented. Here
we explore several optimization opportunities to adapt to the running program
and to adapt parameters that are optimized for the average case. Depending on
the program the transactional load can vary per thread (e.g., client/server
threads), or the program uses multiple phases of computation with different
transactional loads. Therefore it is important that the STM adapts to the
current situation, and that the adaptation process is short, efficient, and
thread-local.
 
We present adaptSTM, a competitive, word-based STM library that is based on a
global clock and an array of combined global versions (timestamps) and locks.
To keep track of transactional data adaptSTM implements a multi-level buffer
and uses read-set extension to achieve competitive performance. 
 
The fine-grained adaptation system measures important runtime parameters like
read- and write-locations, commit-, and abort-rate, and is able to adapt
important parameters like write-set hash-size, hash function, and write
strategy based on runtime statistics on a per-thread basis. Using the STAMP
benchmarks, adaptSTM can be compared against other STM libraries.


# References

* [adaptSTM tech. report'10](http://nebelwelt.net/publications/files/10TRadaptstm.pdf) with implementation
  details and comparison to other STM libraries.
* [ISPASS'11 paper](http://nebelwelt.net/publications/files/11ISPASS.pdf) with a focus on performance evaluation.
* [ISPASS'11 presentation](http://nebelwelt.net/publications/files/11ISPASS-presentation.pdf) for a quick
  overview.


# Contact

If you have questions, problems, or bug reports please forward them to
Mathias Payer <mathias.payer@nebelwelt.net>


# Installation

1. download and untar the current version of adaptSTM into a directory
2. open the Makefile and select different optimizations
   * maybe fine-tune the optimizations in adaptstm.h
3. Run make
4. Use lib/libadaptstm.a in your projects by including
   include/adaptstm-external.h
5. Have fun

