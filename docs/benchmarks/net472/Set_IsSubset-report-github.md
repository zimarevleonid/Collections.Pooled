``` ini

BenchmarkDotNet=v0.11.3, OS=Windows 10.0.17763.292 (1809/October2018Update/Redstone5)
Intel Core i7-6700HQ CPU 2.60GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3324.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3324.0

Job=Clr  Runtime=Clr  

```
|                       Method | InitialSetSize |               Mean |             Error |            StdDev |        Ratio |   RatioSD | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|----------------------------- |--------------- |-------------------:|------------------:|------------------:|-------------:|----------:|------------:|------------:|------------:|--------------------:|
|     **HashSet_IsSubset_Hashset** |         **320000** |           **6.857 ns** |         **0.0887 ns** |         **0.0786 ns** |         **1.00** |      **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledSet_IsSubset_PooledSet |         320000 |           6.423 ns |         0.0709 ns |         0.0663 ns |         0.94 |      0.02 |           - |           - |           - |                   - |
|        HashSet_IsSubset_Enum |         320000 |  10,134,495.565 ns |    90,882.4048 ns |    85,011.4578 ns | 1,477,324.82 | 23,357.10 |           - |           - |           - |             12168 B |
|      PooledSet_IsSubset_Enum |         320000 |  10,113,710.833 ns |   140,442.1510 ns |   131,369.6751 ns | 1,476,743.54 | 25,911.29 |           - |           - |           - |             12168 B |
|       HashSet_IsSubset_Array |         320000 |  10,103,826.120 ns |   105,353.8312 ns |    98,548.0391 ns | 1,472,148.53 | 16,953.41 |           - |           - |           - |             12168 B |
|     PooledSet_IsSubset_Array |         320000 |   8,717,739.364 ns |   128,157.7549 ns |   113,608.5116 ns | 1,271,423.38 | 13,160.11 |           - |           - |           - |             12040 B |
|                              |                |                    |                   |                   |              |           |             |             |             |                     |
|     **HashSet_IsSubset_Hashset** |        **8000000** |   **3,026,993.971 ns** |    **35,905.6831 ns** |    **33,586.1983 ns** |         **1.00** |      **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledSet_IsSubset_PooledSet |        8000000 |   3,002,706.250 ns |    23,830.4551 ns |    22,291.0225 ns |         0.99 |      0.01 |           - |           - |           - |                   - |
|        HashSet_IsSubset_Enum |        8000000 | 292,870,575.000 ns | 3,005,366.8220 ns | 2,664,179.4071 ns |        96.81 |      1.13 |           - |           - |           - |             16648 B |
|      PooledSet_IsSubset_Enum |        8000000 | 283,567,628.571 ns | 4,336,028.4101 ns | 3,843,776.2452 ns |        93.74 |      2.06 |           - |           - |           - |             16648 B |
|       HashSet_IsSubset_Array |        8000000 | 292,557,803.333 ns | 2,829,893.5708 ns | 2,647,084.2019 ns |        96.66 |      1.42 |           - |           - |           - |             16648 B |
|     PooledSet_IsSubset_Array |        8000000 | 249,816,683.333 ns | 1,792,930.2072 ns | 1,589,385.9283 ns |        82.58 |      1.23 |           - |           - |           - |             12552 B |
