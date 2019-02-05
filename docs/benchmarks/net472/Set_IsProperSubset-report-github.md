``` ini

BenchmarkDotNet=v0.11.3, OS=Windows 10.0.17763.292 (1809/October2018Update/Redstone5)
Intel Core i7-6700HQ CPU 2.60GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3324.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3324.0

Job=Clr  Runtime=Clr  

```
|                             Method | InitialSetSize |              Mean |             Error |            StdDev |         Ratio |    RatioSD | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|----------------------------------- |--------------- |------------------:|------------------:|------------------:|--------------:|-----------:|------------:|------------:|------------:|--------------------:|
|     **HashSet_IsProperSubset_Hashset** |         **320000** |          **10.38 ns** |         **0.0459 ns** |         **0.0429 ns** |          **1.00** |       **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledSet_IsProperSubset_PooledSet |         320000 |          11.31 ns |         0.0542 ns |         0.0481 ns |          1.09 |       0.01 |           - |           - |           - |                   - |
|        HashSet_IsProperSubset_Enum |         320000 |  10,786,597.77 ns |   220,655.8775 ns |   316,458.0660 ns |  1,050,933.87 |  39,187.16 |           - |           - |           - |             12168 B |
|      PooledSet_IsProperSubset_Enum |         320000 |  10,620,507.57 ns |    77,790.1580 ns |    68,958.9489 ns |  1,022,493.19 |   8,166.68 |           - |           - |           - |             12168 B |
|       HashSet_IsProperSubset_Array |         320000 |  10,624,768.88 ns |    78,973.9879 ns |    73,872.3173 ns |  1,023,387.89 |   8,467.03 |           - |           - |           - |             12168 B |
|     PooledSet_IsProperSubset_Array |         320000 |   8,982,940.94 ns |    56,663.9585 ns |    53,003.5019 ns |    865,238.20 |   5,270.80 |           - |           - |           - |             12040 B |
|                                    |                |                   |                   |                   |               |            |             |             |             |                     |
|     **HashSet_IsProperSubset_Hashset** |        **8000000** |          **10.52 ns** |         **0.2229 ns** |         **0.2085 ns** |          **1.00** |       **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledSet_IsProperSubset_PooledSet |        8000000 |          10.48 ns |         0.0734 ns |         0.0687 ns |          1.00 |       0.02 |           - |           - |           - |                   - |
|        HashSet_IsProperSubset_Enum |        8000000 | 307,188,933.33 ns | 2,001,655.6070 ns | 1,872,349.8967 ns | 29,217,414.82 | 541,148.33 |           - |           - |           - |             16648 B |
|      PooledSet_IsProperSubset_Enum |        8000000 | 295,444,289.29 ns | 2,481,220.7591 ns | 2,199,537.5747 ns | 28,082,104.58 | 567,525.63 |           - |           - |           - |             16648 B |
|       HashSet_IsProperSubset_Array |        8000000 | 309,653,183.33 ns | 4,627,261.7375 ns | 4,328,343.5002 ns | 29,451,970.96 | 665,777.86 |           - |           - |           - |             16648 B |
|     PooledSet_IsProperSubset_Array |        8000000 | 264,052,443.33 ns | 2,639,703.1810 ns | 2,469,179.9933 ns | 25,113,750.90 | 449,941.42 |           - |           - |           - |             12552 B |