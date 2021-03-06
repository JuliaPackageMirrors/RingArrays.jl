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
| 1   | "constructor ring" | "RingArray{Int, 1}(max_blocks=m_b, block_size=b_s, data_length=d_l)" | 100        | 7.4856e-5 |

| Row | AverageWall | MaxWall  | MinWall | Timestamp             | JuliaHash                                  |
|-----|-------------|----------|---------|-----------------------|--------------------------------------------|
| 1   | 7.4856e-7   | 8.709e-6 | 6.09e-7 | "2016-02-03 12:27:39" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" |

| Row | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|----------|----------|
| 1   | "a999b5934e91d2bd109305e861bc83a2988ab77b" | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category                   | Benchmark         | Iterations | TotalWall | AverageWall | MaxWall | MinWall |
|-----|----------------------------|-------------------|------------|-----------|-------------|---------|---------|
| 1   | "constructor normal array" | "Array{Int, 1}()" | 100        | 2.9612e-5 | 2.9612e-7   | 5.98e-7 | 2.82e-7 |

| Row | Timestamp             | JuliaHash                                  | CodeHash                                   |
|-----|-----------------------|--------------------------------------------|--------------------------------------------|
| 1   | "2016-02-03 12:27:40" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "a999b5934e91d2bd109305e861bc83a2988ab77b" |

| Row | OS       | CPUCores |
|-----|----------|----------|
| 1   | "Darwin" | 4        |

2x4 DataFrames.DataFrame
| Row | Function                         | Average   | Relative | Replications |
|-----|----------------------------------|-----------|----------|--------------|
| 1   | "constructor_ring_bench"         | 8.2094e-7 | 2.48649  | 100          |
| 2   | "constructor_normal_array_bench" | 3.3016e-7 | 1.0      | 100          |


################################################################################
# load_block
################################################################################

1x12 DataFrames.DataFrame
| Row | Category             | Benchmark    | Iterations | TotalWall | AverageWall | MaxWall  | MinWall   |
|-----|----------------------|--------------|------------|-----------|-------------|----------|-----------|
| 1   | "loading with no gc" | "load_block" | 100        | 6.43046   | 0.0643046   | 0.111654 | 0.0509943 |

| Row | Timestamp             | JuliaHash                                  | CodeHash                                   |
|-----|-----------------------|--------------------------------------------|--------------------------------------------|
| 1   | "2016-02-03 12:27:48" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "a999b5934e91d2bd109305e861bc83a2988ab77b" |

| Row | OS       | CPUCores |
|-----|----------|----------|
| 1   | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category          | Benchmark    | Iterations | TotalWall | AverageWall | MaxWall  | MinWall  | Timestamp             |
|-----|-------------------|--------------|------------|-----------|-------------|----------|----------|-----------------------|
| 1   | "loading with gc" | "load_block" | 100        | 11.5925   | 0.115925    | 0.182815 | 0.099769 | "2016-02-03 12:28:00" |

| Row | JuliaHash                                  | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|--------------------------------------------|----------|----------|
| 1   | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "a999b5934e91d2bd109305e861bc83a2988ab77b" | "Darwin" | 4        |

2x4 DataFrames.DataFrame
| Row | Function          | Average   | Relative | Replications |
|-----|-------------------|-----------|----------|--------------|
| 1   | "loading_no_gc"   | 0.0712749 | 1.0      | 100          |
| 2   | "loading_with_gc" | 0.143009  | 2.00644  | 100          |


################################################################################
# size
################################################################################

1x12 DataFrames.DataFrame
| Row | Category          | Benchmark          | Iterations | TotalWall | AverageWall | MaxWall | MinWall |
|-----|-------------------|--------------------|------------|-----------|-------------|---------|---------|
| 1   | "size empty ring" | "size(empty_ring)" | 100        | 2.8728e-5 | 2.8728e-7   | 7.19e-7 | 2.8e-7  |

| Row | Timestamp             | JuliaHash                                  | CodeHash                                   |
|-----|-----------------------|--------------------------------------------|--------------------------------------------|
| 1   | "2016-02-03 12:28:22" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "a999b5934e91d2bd109305e861bc83a2988ab77b" |

| Row | OS       | CPUCores |
|-----|----------|----------|
| 1   | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category         | Benchmark         | Iterations | TotalWall | AverageWall | MaxWall | MinWall | Timestamp             |
|-----|------------------|-------------------|------------|-----------|-------------|---------|---------|-----------------------|
| 1   | "size full ring" | "size(full_ring)" | 100        | 2.775e-5  | 2.775e-7    | 4.37e-7 | 2.66e-7 | "2016-02-03 12:28:22" |

| Row | JuliaHash                                  | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|--------------------------------------------|----------|----------|
| 1   | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "a999b5934e91d2bd109305e861bc83a2988ab77b" | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category        | Benchmark        | Iterations | TotalWall | AverageWall | MaxWall | MinWall | Timestamp             |
|-----|-----------------|------------------|------------|-----------|-------------|---------|---------|-----------------------|
| 1   | "size end ring" | "size(end_ring)" | 100        | 4.5278e-5 | 4.5278e-7   | 2.4e-6  | 3.25e-7 | "2016-02-03 12:28:22" |

| Row | JuliaHash                                  | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|--------------------------------------------|----------|----------|
| 1   | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "a999b5934e91d2bd109305e861bc83a2988ab77b" | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category            | Benchmark        | Iterations | TotalWall | AverageWall | MaxWall | MinWall |
|-----|---------------------|------------------|------------|-----------|-------------|---------|---------|
| 1   | "size normal array" | "size(big_data)" | 100        | 2.9685e-5 | 2.9685e-7   | 2.8e-6  | 2.59e-7 |

| Row | Timestamp             | JuliaHash                                  | CodeHash                                   |
|-----|-----------------------|--------------------------------------------|--------------------------------------------|
| 1   | "2016-02-03 12:28:22" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "a999b5934e91d2bd109305e861bc83a2988ab77b" |

| Row | OS       | CPUCores |
|-----|----------|----------|
| 1   | "Darwin" | 4        |

4x4 DataFrames.DataFrame
| Row | Function                  | Average   | Relative | Replications |
|-----|---------------------------|-----------|----------|--------------|
| 1   | "size_empty_bench"        | 3.7623e-7 | 1.31558  | 100          |
| 2   | "size_full_bench"         | 2.9719e-7 | 1.0392   | 100          |
| 3   | "size_end_bench"          | 2.8598e-7 | 1.0      | 100          |
| 4   | "size_normal_array_bench" | 2.9155e-7 | 1.01948  | 100          |


################################################################################
# checkbounds
################################################################################

1x12 DataFrames.DataFrame
| Row | Category                | Benchmark                                      | Iterations | TotalWall   | AverageWall |
|-----|-------------------------|------------------------------------------------|------------|-------------|-------------|
| 1   | "checkbounds full ring" | "checkbounds(full_ring, full_ring.range.stop)" | 100        | 0.000109511 | 1.09511e-6  |

| Row | MaxWall  | MinWall | Timestamp             | JuliaHash                                  |
|-----|----------|---------|-----------------------|--------------------------------------------|
| 1   | 9.773e-6 | 6.85e-7 | "2016-02-03 12:28:22" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" |

| Row | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|----------|----------|
| 1   | "a999b5934e91d2bd109305e861bc83a2988ab77b" | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category               | Benchmark                                    | Iterations | TotalWall | AverageWall | MaxWall  |
|-----|------------------------|----------------------------------------------|------------|-----------|-------------|----------|
| 1   | "checkbounds end ring" | "checkbounds(end_ring, end_ring.range.stop)" | 100        | 6.1161e-5 | 6.1161e-7   | 4.537e-6 |

| Row | MinWall | Timestamp             | JuliaHash                                  |
|-----|---------|-----------------------|--------------------------------------------|
| 1   | 5.26e-7 | "2016-02-03 12:28:22" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" |

| Row | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|----------|----------|
| 1   | "a999b5934e91d2bd109305e861bc83a2988ab77b" | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category                   | Benchmark                                    | Iterations | TotalWall | AverageWall |
|-----|----------------------------|----------------------------------------------|------------|-----------|-------------|
| 1   | "checkbounds normal array" | "checkbounds(big_data, end_ring.range.stop)" | 100        | 6.4972e-5 | 6.4972e-7   |

| Row | MaxWall  | MinWall | Timestamp             | JuliaHash                                  |
|-----|----------|---------|-----------------------|--------------------------------------------|
| 1   | 7.355e-6 | 3.69e-7 | "2016-02-03 12:28:22" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" |

| Row | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|----------|----------|
| 1   | "a999b5934e91d2bd109305e861bc83a2988ab77b" | "Darwin" | 4        |

3x4 DataFrames.DataFrame
| Row | Function                         | Average    | Relative | Replications |
|-----|----------------------------------|------------|----------|--------------|
| 1   | "checkbounds_full_bench"         | 1.87499e-6 | 3.45149  | 100          |
| 2   | "checkbounds_end_bench"          | 1.11096e-6 | 2.04506  | 100          |
| 3   | "checkbounds_normal_array_bench" | 5.4324e-7  | 1.0      | 100          |


################################################################################
# getindex
################################################################################

1x12 DataFrames.DataFrame
| Row | Category                   | Benchmark                          | Iterations | TotalWall   | AverageWall | MaxWall   |
|-----|----------------------------|------------------------------------|------------|-------------|-------------|-----------|
| 1   | "getindex full start ring" | "full_ring[full_ring.range.start]" | 100        | 0.000443641 | 4.43641e-6  | 4.1668e-5 |

| Row | MinWall  | Timestamp             | JuliaHash                                  |
|-----|----------|-----------------------|--------------------------------------------|
| 1   | 3.288e-6 | "2016-02-03 12:28:23" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" |

| Row | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|----------|----------|
| 1   | "a999b5934e91d2bd109305e861bc83a2988ab77b" | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category                  | Benchmark                         | Iterations | TotalWall   | AverageWall | MaxWall  |
|-----|---------------------------|-----------------------------------|------------|-------------|-------------|----------|
| 1   | "getindex full stop ring" | "full_ring[full_ring.range.stop]" | 100        | 0.000262353 | 2.62353e-6  | 7.416e-6 |

| Row | MinWall  | Timestamp             | JuliaHash                                  |
|-----|----------|-----------------------|--------------------------------------------|
| 1   | 1.968e-6 | "2016-02-03 12:28:23" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" |

| Row | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|----------|----------|
| 1   | "a999b5934e91d2bd109305e861bc83a2988ab77b" | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category                  | Benchmark                        | Iterations | TotalWall   | AverageWall | MaxWall  |
|-----|---------------------------|----------------------------------|------------|-------------|-------------|----------|
| 1   | "getindex end start ring" | "end_ring[end_ring.range.start]" | 100        | 0.000278001 | 2.78001e-6  | 7.193e-6 |

| Row | MinWall  | Timestamp             | JuliaHash                                  |
|-----|----------|-----------------------|--------------------------------------------|
| 1   | 2.072e-6 | "2016-02-03 12:28:23" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" |

| Row | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|----------|----------|
| 1   | "a999b5934e91d2bd109305e861bc83a2988ab77b" | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category                 | Benchmark                       | Iterations | TotalWall  | AverageWall | MaxWall     |
|-----|--------------------------|---------------------------------|------------|------------|-------------|-------------|
| 1   | "getindex end stop ring" | "end_ring[end_ring.range.stop]" | 100        | 0.00143267 | 1.43267e-5  | 0.000252716 |

| Row | MinWall  | Timestamp             | JuliaHash                                  |
|-----|----------|-----------------------|--------------------------------------------|
| 1   | 2.111e-6 | "2016-02-03 12:28:23" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" |

| Row | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|----------|----------|
| 1   | "a999b5934e91d2bd109305e861bc83a2988ab77b" | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category                | Benchmark                       | Iterations | TotalWall | AverageWall | MaxWall  | MinWall |
|-----|-------------------------|---------------------------------|------------|-----------|-------------|----------|---------|
| 1   | "getindex normal array" | "big_data[end_ring.range.stop]" | 100        | 4.4248e-5 | 4.4248e-7   | 5.234e-6 | 3.46e-7 |

| Row | Timestamp             | JuliaHash                                  | CodeHash                                   |
|-----|-----------------------|--------------------------------------------|--------------------------------------------|
| 1   | "2016-02-03 12:28:23" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" | "a999b5934e91d2bd109305e861bc83a2988ab77b" |

| Row | OS       | CPUCores |
|-----|----------|----------|
| 1   | "Darwin" | 4        |

5x4 DataFrames.DataFrame
| Row | Function                      | Average    | Relative | Replications |
|-----|-------------------------------|------------|----------|--------------|
| 1   | "getindex_full_start_bench"   | 2.6531e-6  | 6.11215  | 100          |
| 2   | "getindex_full_stop_bench"    | 2.43545e-6 | 5.61073  | 100          |
| 3   | "getindex_end_start_bench"    | 2.48899e-6 | 5.73408  | 100          |
| 4   | "getindex_end_stop_bench"     | 2.46069e-6 | 5.66888  | 100          |
| 5   | "getindex_normal_array_bench" | 4.3407e-7  | 1.0      | 100          |


################################################################################
# getindex range
################################################################################

1x12 DataFrames.DataFrame
| Row | Category                       | Benchmark                    | Iterations | TotalWall   | AverageWall | MaxWall   |
|-----|--------------------------------|------------------------------|------------|-------------|-------------|-----------|
| 1   | "getindex range full all ring" | "full_ring[full_ring.range]" | 100        | 0.000524739 | 5.24739e-6  | 1.9024e-5 |

| Row | MinWall  | Timestamp             | JuliaHash                                  |
|-----|----------|-----------------------|--------------------------------------------|
| 1   | 4.655e-6 | "2016-02-03 12:28:23" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" |

| Row | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|----------|----------|
| 1   | "a999b5934e91d2bd109305e861bc83a2988ab77b" | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category                         | Benchmark                                              | Iterations | TotalWall   |
|-----|----------------------------------|--------------------------------------------------------|------------|-------------|
| 1   | "getindex range full small ring" | "full_ring[full_ring.range.stop:full_ring.range.stop]" | 100        | 0.000511507 |

| Row | AverageWall | MaxWall   | MinWall  | Timestamp             | JuliaHash                                  |
|-----|-------------|-----------|----------|-----------------------|--------------------------------------------|
| 1   | 5.11507e-6  | 1.5452e-5 | 4.373e-6 | "2016-02-03 12:28:23" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" |

| Row | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|----------|----------|
| 1   | "a999b5934e91d2bd109305e861bc83a2988ab77b" | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category                      | Benchmark                  | Iterations | TotalWall   | AverageWall | MaxWall   |
|-----|-------------------------------|----------------------------|------------|-------------|-------------|-----------|
| 1   | "getindex range end all ring" | "end_ring[end_ring.range]" | 100        | 0.000896581 | 8.96581e-6  | 1.6856e-5 |

| Row | MinWall  | Timestamp             | JuliaHash                                  |
|-----|----------|-----------------------|--------------------------------------------|
| 1   | 7.371e-6 | "2016-02-03 12:28:23" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" |

| Row | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|----------|----------|
| 1   | "a999b5934e91d2bd109305e861bc83a2988ab77b" | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category                        | Benchmark                                      | Iterations | TotalWall   |
|-----|---------------------------------|------------------------------------------------|------------|-------------|
| 1   | "getindex range end small ring" | "end_ring[end_ring.range:end_ring.range.stop]" | 100        | 0.000486123 |

| Row | AverageWall | MaxWall  | MinWall  | Timestamp             | JuliaHash                                  |
|-----|-------------|----------|----------|-----------------------|--------------------------------------------|
| 1   | 4.86123e-6  | 8.215e-6 | 4.361e-6 | "2016-02-03 12:28:23" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" |

| Row | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|----------|----------|
| 1   | "a999b5934e91d2bd109305e861bc83a2988ab77b" | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category                          | Benchmark                  | Iterations | TotalWall | AverageWall | MaxWall  |
|-----|-----------------------------------|----------------------------|------------|-----------|-------------|----------|
| 1   | "getindex range normal all array" | "big_data[end_ring.range]" | 100        | 8.4432e-5 | 8.4432e-7   | 4.997e-6 |

| Row | MinWall | Timestamp             | JuliaHash                                  |
|-----|---------|-----------------------|--------------------------------------------|
| 1   | 4.41e-7 | "2016-02-03 12:28:23" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" |

| Row | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|----------|----------|
| 1   | "a999b5934e91d2bd109305e861bc83a2988ab77b" | "Darwin" | 4        |

1x12 DataFrames.DataFrame
| Row | Category                            | Benchmark                                           | Iterations | TotalWall |
|-----|-------------------------------------|-----------------------------------------------------|------------|-----------|
| 1   | "getindex range normal small array" | "big_data[end_ring.range.stop:end_ring.range.stop]" | 100        | 9.2575e-5 |

| Row | AverageWall | MaxWall | MinWall | Timestamp             | JuliaHash                                  |
|-----|-------------|---------|---------|-----------------------|--------------------------------------------|
| 1   | 9.2575e-7   | 3.3e-6  | 6.9e-7  | "2016-02-03 12:28:23" | "1f7c72e0e44f18b4d463e15fdbf68bbeee54dba0" |

| Row | CodeHash                                   | OS       | CPUCores |
|-----|--------------------------------------------|----------|----------|
| 1   | "a999b5934e91d2bd109305e861bc83a2988ab77b" | "Darwin" | 4        |

6x4 DataFrames.DataFrame
| Row | Function                                  | Average    | Relative | Replications |
|-----|-------------------------------------------|------------|----------|--------------|
| 1   | "getindex_range_full_all_bench"           | 4.82043e-6 | 6.64355  | 100          |
| 2   | "getindex_range_full_small_bench"         | 4.75896e-6 | 6.55884  | 100          |
| 3   | "getindex_range_end_all_bench"            | 4.80968e-6 | 6.62874  | 100          |
| 4   | "getindex_range_end_small_bench"          | 5.84046e-6 | 8.04937  | 100          |
| 5   | "getindex_range_normal_array_all_bench"   | 8.2338e-7  | 1.13479  | 100          |
| 6   | "getindex_range_normal_array_small_bench" | 7.2558e-7  | 1.0      | 100          |


################################################################################
# overall
################################################################################

23x4 DataFrames.DataFrame
| Row | Function                                  | Average    | Relative  | Replications |
|-----|-------------------------------------------|------------|-----------|--------------|
| 1   | "standard"                                | 2.5922e-7  | 1.0       | 100          |
| 2   | "constructor_ring_bench"                  | 8.1372e-7  | 3.13911   | 100          |
| 3   | "constructor_normal_array_bench"          | 3.3477e-7  | 1.29145   | 100          |
| 4   | "loading_no_gc"                           | 0.101272   | 3.9068e5  | 100          |
| 5   | "loading_with_gc"                         | 0.140049   | 5.40272e5 | 100          |
| 6   | "size_empty_bench"                        | 3.0952e-7  | 1.19404   | 100          |
| 7   | "size_full_bench"                         | 3.04e-7    | 1.17275   | 100          |
| 8   | "size_end_bench"                          | 3.0613e-7  | 1.18097   | 100          |
| 9   | "size_normal_array_bench"                 | 3.0155e-7  | 1.1633    | 100          |
| 10  | "checkbounds_full_bench"                  | 6.9483e-7  | 2.68046   | 100          |
| 11  | "checkbounds_end_bench"                   | 6.7685e-7  | 2.6111    | 100          |
| 12  | "checkbounds_normal_array_bench"          | 3.6729e-7  | 1.4169    | 100          |
| 13  | "getindex_full_start_bench"               | 2.52886e-6 | 9.75565   | 100          |
| 14  | "getindex_full_stop_bench"                | 2.50308e-6 | 9.6562    | 100          |
| 15  | "getindex_end_start_bench"                | 2.52776e-6 | 9.75141   | 100          |
| 16  | "getindex_end_stop_bench"                 | 2.70452e-6 | 10.4333   | 100          |
| 17  | "getindex_normal_array_bench"             | 4.0088e-7  | 1.54649   | 100          |
| 18  | "getindex_range_full_all_bench"           | 4.92355e-6 | 18.9937   | 100          |
| 19  | "getindex_range_full_small_bench"         | 4.91731e-6 | 18.9696   | 100          |
| 20  | "getindex_range_end_all_bench"            | 8.99897e-6 | 34.7156   | 100          |
| 21  | "getindex_range_end_small_bench"          | 8.81902e-6 | 34.0214   | 100          |
| 22  | "getindex_range_normal_array_all_bench"   | 8.7117e-7  | 3.36074   | 100          |
| 23  | "getindex_range_normal_array_small_bench" | 5.7033e-7  | 2.20018   | 100          |
```