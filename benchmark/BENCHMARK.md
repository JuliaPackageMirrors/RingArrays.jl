## Benchmarking VirtualArray

Checking the performance of VirtualArray

### To run these BenchMarks

You need `Benchmark.jl`, which you can get [here](https://github.com/johnmyleswhite/Benchmark.jl).

In the `RingArray` directory, run `julia benchmark/benchmark.jl`. 

The results of that tests are stored in [benchmark_result](benchmark_result).

### Test Ran

The code I used to benchmark can be found [here](benchmark.jl).

### Results

The results of the test are [here](benchmark_result) and below.

```
################################################################################
# constructor
################################################################################

1x12 DataFrames.DataFrame
| Row | Category           | Benchmark                                                            | Iterations | TotalWall |
|-----|--------------------|----------------------------------------------------------------------|------------|-----------|
| 1   | "constructor ring" | "RingArray{Int, 1}(max_blocks=m_b, block_size=b_s, data_length=d_l)" | 100        | 6.739e-5  |

| Row | AverageWall | MaxWall  | MinWall | Timestamp             | JuliaHash                                  |
|-----|-------------|----------|---------|-----------------------|--------------------------------------------|
| 1   | 6.739e-7    | 5.854e-6 | 5.96e-7 | "2016-02-01 15:39:15" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" |

| Row | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|----------|----------|
| 1   | "60fea3cacff026099d6e3a949b34972997a51db1" | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category                   | Benchmark         | Iterations | TotalWall | AverageWall | MaxWall | MinWall |
|-----|----------------------------|-------------------|------------|-----------|-------------|---------|---------|
| 1   | "constructor normal array" | "Array{Int, 1}()" | 100        | 2.9314e-5 | 2.9314e-7   | 6.01e-7 | 2.8e-7  |

| Row | Timestamp             | JuliaHash                                  | CodeHash                                   | OS       |
|-----|-----------------------|--------------------------------------------|--------------------------------------------|----------|
| 1   | "2016-02-01 15:39:16" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "60fea3cacff026099d6e3a949b34972997a51db1" | "Darwin" |

| Row | CPUCores |
|-----|----------|
| 1   | 4        |

2x4 DataFrames.DataFrame
| Row | Function                         | Average   | Relative | Replications |
|-----|----------------------------------|-----------|----------|--------------|
| 1   | "constructor_ring_bench"         | 8.8343e-7 | 2.4773   | 100          |
| 2   | "constructor_normal_array_bench" | 3.5661e-7 | 1.0      | 100          |


################################################################################
# load_block
################################################################################

1x12 DataFrames.DataFrame
| Row | Category             | Benchmark    | Iterations | TotalWall | AverageWall | MaxWall   | MinWall   | Timestamp             |
|-----|----------------------|--------------|------------|-----------|-------------|-----------|-----------|-----------------------|
| 1   | "loading with no gc" | "load_block" | 100        | 6.31391   | 0.0631391   | 0.0750923 | 0.0519753 | "2016-02-01 15:39:24" |

| Row | JuliaHash                                  | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|--------------------------------------------|----------|----------|
| 1   | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "60fea3cacff026099d6e3a949b34972997a51db1" | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category          | Benchmark    | Iterations | TotalWall | AverageWall | MaxWall  | MinWall  | Timestamp             |
|-----|-------------------|--------------|------------|-----------|-------------|----------|----------|-----------------------|
| 1   | "loading with gc" | "load_block" | 100        | 10.6234   | 0.106234    | 0.118542 | 0.100199 | "2016-02-01 15:39:35" |

| Row | JuliaHash                                  | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|--------------------------------------------|----------|----------|
| 1   | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "60fea3cacff026099d6e3a949b34972997a51db1" | "Darwin" | 4        |

2x4 DataFrames.DataFrame
| Row | Function          | Average   | Relative | Replications |
|-----|-------------------|-----------|----------|--------------|
| 1   | "loading_no_gc"   | 0.0634124 | 1.0      | 100          |
| 2   | "loading_with_gc" | 0.105073  | 1.65697  | 100          |


################################################################################
# size
################################################################################

1x12 DataFrames.DataFrame
| Row | Category          | Benchmark          | Iterations | TotalWall | AverageWall | MaxWall  | MinWall | Timestamp             |
|-----|-------------------|--------------------|------------|-----------|-------------|----------|---------|-----------------------|
| 1   | "size empty ring" | "size(empty_ring)" | 100        | 2.7445e-5 | 2.7445e-7   | 1.658e-6 | 2.55e-7 | "2016-02-01 15:39:52" |

| Row | JuliaHash                                  | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|--------------------------------------------|----------|----------|
| 1   | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "60fea3cacff026099d6e3a949b34972997a51db1" | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category         | Benchmark         | Iterations | TotalWall | AverageWall | MaxWall | MinWall | Timestamp             |
|-----|------------------|-------------------|------------|-----------|-------------|---------|---------|-----------------------|
| 1   | "size full ring" | "size(full_ring)" | 100        | 2.6337e-5 | 2.6337e-7   | 6.23e-7 | 2.53e-7 | "2016-02-01 15:39:52" |

| Row | JuliaHash                                  | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|--------------------------------------------|----------|----------|
| 1   | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "60fea3cacff026099d6e3a949b34972997a51db1" | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category        | Benchmark        | Iterations | TotalWall | AverageWall | MaxWall  | MinWall | Timestamp             |
|-----|-----------------|------------------|------------|-----------|-------------|----------|---------|-----------------------|
| 1   | "size end ring" | "size(end_ring)" | 100        | 2.9268e-5 | 2.9268e-7   | 1.568e-6 | 2.72e-7 | "2016-02-01 15:39:52" |

| Row | JuliaHash                                  | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|--------------------------------------------|----------|----------|
| 1   | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "60fea3cacff026099d6e3a949b34972997a51db1" | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category            | Benchmark        | Iterations | TotalWall | AverageWall | MaxWall  | MinWall | Timestamp             |
|-----|---------------------|------------------|------------|-----------|-------------|----------|---------|-----------------------|
| 1   | "size normal array" | "size(big_data)" | 100        | 2.7017e-5 | 2.7017e-7   | 1.912e-6 | 2.49e-7 | "2016-02-01 15:39:52" |

| Row | JuliaHash                                  | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|--------------------------------------------|----------|----------|
| 1   | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "60fea3cacff026099d6e3a949b34972997a51db1" | "Darwin" | 4        |

4x4 DataFrames.DataFrame
| Row | Function                  | Average   | Relative | Replications |
|-----|---------------------------|-----------|----------|--------------|
| 1   | "size_empty_bench"        | 3.5993e-7 | 1.16925  | 100          |
| 2   | "size_full_bench"         | 3.5374e-7 | 1.14914  | 100          |
| 3   | "size_end_bench"          | 3.0783e-7 | 1.0      | 100          |
| 4   | "size_normal_array_bench" | 5.9785e-7 | 1.94214  | 100          |


################################################################################
# checkbounds
################################################################################

1x12 DataFrames.DataFrame
| Row | Category                | Benchmark                                      | Iterations | TotalWall | AverageWall | MaxWall  |
|-----|-------------------------|------------------------------------------------|------------|-----------|-------------|----------|
| 1   | "checkbounds full ring" | "checkbounds(full_ring, full_ring.range.stop)" | 100        | 6.3068e-5 | 6.3068e-7   | 4.141e-6 |

| Row | MinWall | Timestamp             | JuliaHash                                  | CodeHash                                   |
|-----|---------|-----------------------|--------------------------------------------|--------------------------------------------|
| 1   | 5.3e-7  | "2016-02-01 15:39:52" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "60fea3cacff026099d6e3a949b34972997a51db1" |

| Row | OS       | CPUCores |
|-----|----------|----------|
| 1   | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category               | Benchmark                                    | Iterations | TotalWall | AverageWall | MaxWall |
|-----|------------------------|----------------------------------------------|------------|-----------|-------------|---------|
| 1   | "checkbounds end ring" | "checkbounds(end_ring, end_ring.range.stop)" | 100        | 6.1961e-5 | 6.1961e-7   | 2.3e-6  |

| Row | MinWall | Timestamp             | JuliaHash                                  | CodeHash                                   |
|-----|---------|-----------------------|--------------------------------------------|--------------------------------------------|
| 1   | 5.36e-7 | "2016-02-01 15:39:52" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "60fea3cacff026099d6e3a949b34972997a51db1" |

| Row | OS       | CPUCores |
|-----|----------|----------|
| 1   | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category                   | Benchmark                                    | Iterations | TotalWall | AverageWall | MaxWall  |
|-----|----------------------------|----------------------------------------------|------------|-----------|-------------|----------|
| 1   | "checkbounds normal array" | "checkbounds(big_data, end_ring.range.stop)" | 100        | 3.6041e-5 | 3.6041e-7   | 3.954e-6 |

| Row | MinWall | Timestamp             | JuliaHash                                  | CodeHash                                   |
|-----|---------|-----------------------|--------------------------------------------|--------------------------------------------|
| 1   | 3.0e-7  | "2016-02-01 15:39:53" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "60fea3cacff026099d6e3a949b34972997a51db1" |

| Row | OS       | CPUCores |
|-----|----------|----------|
| 1   | "Darwin" | 4        |

3x4 DataFrames.DataFrame
| Row | Function                         | Average   | Relative | Replications |
|-----|----------------------------------|-----------|----------|--------------|
| 1   | "checkbounds_full_bench"         | 6.5309e-7 | 1.81646  | 100          |
| 2   | "checkbounds_end_bench"          | 6.5453e-7 | 1.82047  | 100          |
| 3   | "checkbounds_normal_array_bench" | 3.5954e-7 | 1.0      | 100          |


################################################################################
# getindex
################################################################################

1x12 DataFrames.DataFrame
| Row | Category                   | Benchmark                          | Iterations | TotalWall   | AverageWall | MaxWall   |
|-----|----------------------------|------------------------------------|------------|-------------|-------------|-----------|
| 1   | "getindex full start ring" | "full_ring[full_ring.range.start]" | 100        | 0.000248219 | 2.48219e-6  | 2.7017e-5 |

| Row | MinWall  | Timestamp             | JuliaHash                                  | CodeHash                                   |
|-----|----------|-----------------------|--------------------------------------------|--------------------------------------------|
| 1   | 1.911e-6 | "2016-02-01 15:39:53" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "60fea3cacff026099d6e3a949b34972997a51db1" |

| Row | OS       | CPUCores |
|-----|----------|----------|
| 1   | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category                  | Benchmark                         | Iterations | TotalWall   | AverageWall | MaxWall  |
|-----|---------------------------|-----------------------------------|------------|-------------|-------------|----------|
| 1   | "getindex full stop ring" | "full_ring[full_ring.range.stop]" | 100        | 0.000232114 | 2.32114e-6  | 5.724e-6 |

| Row | MinWall  | Timestamp             | JuliaHash                                  | CodeHash                                   |
|-----|----------|-----------------------|--------------------------------------------|--------------------------------------------|
| 1   | 1.918e-6 | "2016-02-01 15:39:53" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "60fea3cacff026099d6e3a949b34972997a51db1" |

| Row | OS       | CPUCores |
|-----|----------|----------|
| 1   | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category                  | Benchmark                        | Iterations | TotalWall   | AverageWall | MaxWall  | MinWall  |
|-----|---------------------------|----------------------------------|------------|-------------|-------------|----------|----------|
| 1   | "getindex end start ring" | "end_ring[end_ring.range.start]" | 100        | 0.000242783 | 2.42783e-6  | 5.204e-6 | 2.118e-6 |

| Row | Timestamp             | JuliaHash                                  | CodeHash                                   | OS       |
|-----|-----------------------|--------------------------------------------|--------------------------------------------|----------|
| 1   | "2016-02-01 15:39:53" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "60fea3cacff026099d6e3a949b34972997a51db1" | "Darwin" |

| Row | CPUCores |
|-----|----------|
| 1   | 4        |

1x12 DataFrames.DataFrame
| Row | Category                 | Benchmark                       | Iterations | TotalWall   | AverageWall | MaxWall  | MinWall  |
|-----|--------------------------|---------------------------------|------------|-------------|-------------|----------|----------|
| 1   | "getindex end stop ring" | "end_ring[end_ring.range.stop]" | 100        | 0.000308082 | 3.08082e-6  | 3.343e-5 | 2.052e-6 |

| Row | Timestamp             | JuliaHash                                  | CodeHash                                   | OS       |
|-----|-----------------------|--------------------------------------------|--------------------------------------------|----------|
| 1   | "2016-02-01 15:39:53" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "60fea3cacff026099d6e3a949b34972997a51db1" | "Darwin" |

| Row | CPUCores |
|-----|----------|
| 1   | 4        |

1x12 DataFrames.DataFrame
| Row | Category                | Benchmark                       | Iterations | TotalWall | AverageWall | MaxWall   | MinWall |
|-----|-------------------------|---------------------------------|------------|-----------|-------------|-----------|---------|
| 1   | "getindex normal array" | "big_data[end_ring.range.stop]" | 100        | 5.6965e-5 | 5.6965e-7   | 1.3357e-5 | 3.3e-7  |

| Row | Timestamp             | JuliaHash                                  | CodeHash                                   | OS       |
|-----|-----------------------|--------------------------------------------|--------------------------------------------|----------|
| 1   | "2016-02-01 15:39:53" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "60fea3cacff026099d6e3a949b34972997a51db1" | "Darwin" |

| Row | CPUCores |
|-----|----------|
| 1   | 4        |

5x4 DataFrames.DataFrame
| Row | Function                      | Average    | Relative | Replications |
|-----|-------------------------------|------------|----------|--------------|
| 1   | "getindex_full_start_bench"   | 2.62605e-6 | 6.36881  | 100          |
| 2   | "getindex_full_stop_bench"    | 2.49052e-6 | 6.04011  | 100          |
| 3   | "getindex_end_start_bench"    | 2.60837e-6 | 6.32593  | 100          |
| 4   | "getindex_end_stop_bench"     | 2.43511e-6 | 5.90573  | 100          |
| 5   | "getindex_normal_array_bench" | 4.1233e-7  | 1.0      | 100          |


################################################################################
# getindex range
################################################################################

1x12 DataFrames.DataFrame
| Row | Category                       | Benchmark                    | Iterations | TotalWall | AverageWall | MaxWall     |
|-----|--------------------------------|------------------------------|------------|-----------|-------------|-------------|
| 1   | "getindex range full all ring" | "full_ring[full_ring.range]" | 100        | 0.0263691 | 0.000263691 | 0.000632656 |

| Row | MinWall     | Timestamp             | JuliaHash                                  |
|-----|-------------|-----------------------|--------------------------------------------|
| 1   | 0.000243216 | "2016-02-01 15:39:53" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" |

| Row | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|----------|----------|
| 1   | "60fea3cacff026099d6e3a949b34972997a51db1" | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category                         | Benchmark                                              | Iterations | TotalWall  |
|-----|----------------------------------|--------------------------------------------------------|------------|------------|
| 1   | "getindex range full small ring" | "full_ring[full_ring.range.stop:full_ring.range.stop]" | 100        | 0.00100395 |

| Row | AverageWall | MaxWall  | MinWall | Timestamp             | JuliaHash                                  |
|-----|-------------|----------|---------|-----------------------|--------------------------------------------|
| 1   | 1.00395e-5  | 3.771e-5 | 7.73e-6 | "2016-02-01 15:39:53" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" |

| Row | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|----------|----------|
| 1   | "60fea3cacff026099d6e3a949b34972997a51db1" | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category                      | Benchmark                  | Iterations | TotalWall | AverageWall | MaxWall   | MinWall     |
|-----|-------------------------------|----------------------------|------------|-----------|-------------|-----------|-------------|
| 1   | "getindex range end all ring" | "end_ring[end_ring.range]" | 100        | 0.034646  | 0.00034646  | 0.0101054 | 0.000229837 |

| Row | Timestamp             | JuliaHash                                  | CodeHash                                   | OS       |
|-----|-----------------------|--------------------------------------------|--------------------------------------------|----------|
| 1   | "2016-02-01 15:39:53" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "60fea3cacff026099d6e3a949b34972997a51db1" | "Darwin" |

| Row | CPUCores |
|-----|----------|
| 1   | 4        |

1x12 DataFrames.DataFrame
| Row | Category                        | Benchmark                                      | Iterations | TotalWall   | AverageWall |
|-----|---------------------------------|------------------------------------------------|------------|-------------|-------------|
| 1   | "getindex range end small ring" | "end_ring[end_ring.range:end_ring.range.stop]" | 100        | 0.000924926 | 9.24926e-6  |

| Row | MaxWall   | MinWall  | Timestamp             | JuliaHash                                  |
|-----|-----------|----------|-----------------------|--------------------------------------------|
| 1   | 2.7488e-5 | 7.599e-6 | "2016-02-01 15:39:53" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" |

| Row | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|----------|----------|
| 1   | "60fea3cacff026099d6e3a949b34972997a51db1" | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category                          | Benchmark                  | Iterations | TotalWall | AverageWall | MaxWall  | MinWall |
|-----|-----------------------------------|----------------------------|------------|-----------|-------------|----------|---------|
| 1   | "getindex range normal all array" | "big_data[end_ring.range]" | 100        | 8.1916e-5 | 8.1916e-7   | 5.428e-6 | 3.88e-7 |

| Row | Timestamp             | JuliaHash                                  | CodeHash                                   | OS       |
|-----|-----------------------|--------------------------------------------|--------------------------------------------|----------|
| 1   | "2016-02-01 15:39:53" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "60fea3cacff026099d6e3a949b34972997a51db1" | "Darwin" |

| Row | CPUCores |
|-----|----------|
| 1   | 4        |

1x12 DataFrames.DataFrame
| Row | Category                            | Benchmark                                           | Iterations | TotalWall |
|-----|-------------------------------------|-----------------------------------------------------|------------|-----------|
| 1   | "getindex range normal small array" | "big_data[end_ring.range.stop:end_ring.range.stop]" | 100        | 6.4938e-5 |

| Row | AverageWall | MaxWall  | MinWall | Timestamp             | JuliaHash                                  |
|-----|-------------|----------|---------|-----------------------|--------------------------------------------|
| 1   | 6.4938e-7   | 4.421e-6 | 4.64e-7 | "2016-02-01 15:39:53" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" |

| Row | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|----------|----------|
| 1   | "60fea3cacff026099d6e3a949b34972997a51db1" | "Darwin" | 4        |

6x4 DataFrames.DataFrame
| Row | Function                                  | Average     | Relative | Replications |
|-----|-------------------------------------------|-------------|----------|--------------|
| 1   | "getindex_range_full_all_bench"           | 0.000254553 | 417.198  | 100          |
| 2   | "getindex_range_full_small_bench"         | 1.00452e-5  | 16.4635  | 100          |
| 3   | "getindex_range_end_all_bench"            | 0.000256508 | 420.402  | 100          |
| 4   | "getindex_range_end_small_bench"          | 8.89573e-6  | 14.5796  | 100          |
| 5   | "getindex_range_normal_array_all_bench"   | 7.064e-7    | 1.15775  | 100          |
| 6   | "getindex_range_normal_array_small_bench" | 6.1015e-7   | 1.0      | 100          |


################################################################################
# overall
################################################################################

23x4 DataFrames.DataFrame
| Row | Function                                  | Average     | Relative  | Replications |
|-----|-------------------------------------------|-------------|-----------|--------------|
| 1   | "standard"                                | 2.3227e-7   | 1.0       | 100          |
| 2   | "constructor_ring_bench"                  | 7.6431e-7   | 3.29061   | 100          |
| 3   | "constructor_normal_array_bench"          | 3.231e-7    | 1.39105   | 100          |
| 4   | "loading_no_gc"                           | 0.0635755   | 2.73714e5 | 100          |
| 5   | "loading_with_gc"                         | 0.109325    | 4.70681e5 | 100          |
| 6   | "size_empty_bench"                        | 2.7776e-7   | 1.19585   | 100          |
| 7   | "size_full_bench"                         | 2.7767e-7   | 1.19546   | 100          |
| 8   | "size_end_bench"                          | 2.8701e-7   | 1.23567   | 100          |
| 9   | "size_normal_array_bench"                 | 2.7742e-7   | 1.19439   | 100          |
| 10  | "checkbounds_full_bench"                  | 6.3422e-7   | 2.73053   | 100          |
| 11  | "checkbounds_end_bench"                   | 6.2747e-7   | 2.70147   | 100          |
| 12  | "checkbounds_normal_array_bench"          | 3.3633e-7   | 1.44801   | 100          |
| 13  | "getindex_full_start_bench"               | 2.29885e-6  | 9.89732   | 100          |
| 14  | "getindex_full_stop_bench"                | 2.27216e-6  | 9.78241   | 100          |
| 15  | "getindex_end_start_bench"                | 2.26271e-6  | 9.74172   | 100          |
| 16  | "getindex_end_stop_bench"                 | 2.25996e-6  | 9.72988   | 100          |
| 17  | "getindex_normal_array_bench"             | 3.5993e-7   | 1.54962   | 100          |
| 18  | "getindex_range_full_all_bench"           | 0.000251682 | 1083.58   | 100          |
| 19  | "getindex_range_full_small_bench"         | 7.91018e-6  | 34.056    | 100          |
| 20  | "getindex_range_end_all_bench"            | 0.000357484 | 1539.09   | 100          |
| 21  | "getindex_range_end_small_bench"          | 8.62408e-6  | 37.1295   | 100          |
| 22  | "getindex_range_normal_array_all_bench"   | 5.6131e-7   | 2.41663   | 100          |
| 23  | "getindex_range_normal_array_small_bench" | 5.4229e-7   | 2.33474   | 100          |
```