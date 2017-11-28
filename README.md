# Build instructions:
Requires:
- Visual Studio 2017 (make sure to install the 'Universal Windows Platform develoment' workload as it has needed libraries. Also install the Windows 10 SDK under the 'Desktop development with C++' workload)
- Boost 1.65.1 (for 64bit I built the libs with 'b2 architecture=x86 address-model=64 variant=release link=static'. I included the libs I compiled under 'nheqminer\3rdparty\libs\boost')

# Run instructions:

*note this version is set to mine at us-east.pool.gold in nheqminer\main.cpp*

If run without parameters, miner will start mining with 75% of available virtual cores on NiceHash. Use parameter -h to learn about available parameters:

        -h              Print this help and quit
        -l [location]   Location (eu, usa, hk, jp)
        -u [username]   Username (bitcoingoldaddress)
        -p [password]   Password (default: x)
        -t [num_thrds]  Number of threads (default: number of sys cores)
        -d [level]      Debug print level (0 = print all, 5 = fatal only, default: 2)
        -b [hashes]     Run in benchmark mode (default: 100 hashes)
        -a [port]       Local API port (default: 0 = do not bind)
        
Example to run benchmark:

        nheqminer_x64_AVX.exe -b
        
Example to run with full logging (including network dump):

        nheqminer_x64_AVX.exe -d 0
        
Example to mine with your own BTG address and worker1 on USA server:

        nheqminer_x64_AVX.exe -l usa -u YOUR_BTG_ADDRESS_HERE.worker1

Example to mine with your own BTG address and worker1 on EU server, using 6 threads:

        nheqminer_x64_AVX.exe -l eu -u YOUR_BTG_ADDRESS_HERE.worker1 -t 6

<i>Note: if you have a 4-core CPU with hyper threading enabled (total 8 threads) it is best to run with only 6 threads (experimental benchmarks shows that best results are achieved with 75% threads utilized)</i>
