# KOI Aleo Miner

## Introduction

ALEO pow miner from KOI Pool, with full GPU support.

## Usage

quick start:

```
$ ./aminer -a [address] 
```

full help:

```
KOI ALEO PoW Miner

Usage: aminer [OPTIONS]

Options:
      --new-address                Generate a new aleo address offline
  -w, --worker-name <WORKER_NAME>  miner worker name, default to local hostname
  -s, --server <SERVER>            server address [default: aleo.koipool.com:3366]
  -a, --address <ADDRESS>          ALEO client address, used for receiving rewards in solo mining; or for settling rewards in pool mining
      --solo                       solo mining mode, receive rewards directly in address, with 3% devfee
  -t, --threads <THREADS>          Number of threads, defaults to number of CPU threads
  -o, --log <LOG>                  Output log to file
      --bench                      run bench against epoch hash
      --bench-epoch <BENCH_EPOCH>  benchmark epoch hash [default: ab134vh2afz9hpkfes2n97al2uakymtczx54eecy8uk7tfas5gp2uyqmj934h]
      --bench-time <BENCH_TIME>    benchmark duration in seconds [default: 15]
      --no-double-buffer           do not use double buffer in GPU to save half of GPU memory, default is false
      --no-device-rng              
      --lower-cpu                  lower cpu usage by using gpu to calculate solution ids
  -h, --help                       Print help
```

## Dependency

* CUDA 12 or above, linux nvidia driver version 525 or above.
* curl: ``` sudo apt-get install curl ```

## Dev Fee

* When mining in solo mode, the miner has a 3% dev fee, which means 3% of the mining rewards will be sent to the developer's address.
* When mining in pool mode, the pool will charge a fee, which is usually 1%, decided by the pool.
* The dev fee is used to support the development of the miner and the maintenance of the pool.
* The dev fee is excluded from the mining power.
* The pool server is used even in solo mode, to provide the epoch hash and submit the mining results.

## GPU Support

### Pascal Architecture

GTX 10 Series

* GTX 1080 Ti
* GTX 1080
* GTX 1070 Ti
* GTX 1070
* GTX 1060 (6GB/3GB)
* GTX 1050 Ti
* GTX 1050

### Turing Architecture

RTX 20 Series

* RTX 2080 Ti
* RTX 2080 Super
* RTX 2080
* RTX 2070 Super
* RTX 2070
* RTX 2060 Super
* RTX 2060
* GTX 16 Series
* GTX 1660 Ti
* GTX 1660 Super
* GTX 1660
* GTX 1650 Super
* GTX 1650
### Ampere Architecture

RTX 30 Series

* RTX 3090 Ti
* RTX 3090
* RTX 3080 Ti
* RTX 3080 (12GB/10GB)
* RTX 3070 Ti
* RTX 3070
* RTX 3060 Ti
* RTX 3060 (12GB)
* RTX 3050

### Ada Lovelace Architecture

RTX 40 Series

* RTX 4090
* RTX 4080 (16GB/12GB)
* RTX 4070 Ti
* RTX 4070
* RTX 4060 Ti
* RTX 4060
* RTX 4050 (Expected)