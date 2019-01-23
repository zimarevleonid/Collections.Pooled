``` ini

BenchmarkDotNet=v0.11.3, OS=Windows 10.0.17763.292 (1809/October2018Update/Redstone5)
Intel Core i7-6700HQ CPU 2.60GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
.NET Core SDK=3.0.100-preview-009812
  [Host] : .NET Core 2.2.1 (CoreCLR 4.6.27207.03, CoreFX 4.6.27207.03), 64bit RyuJIT
  Core   : .NET Core 2.2.1 (CoreCLR 4.6.27207.03, CoreFX 4.6.27207.03), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|                       Method |      N |   Type |           Mean |          Error |         StdDev | Ratio | RatioSD | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|----------------------------- |------- |------- |---------------:|---------------:|---------------:|------:|--------:|------------:|------------:|------------:|--------------------:|
|  **StackICollectionConstructor** |   **1000** |    **Int** |       **265.4 us** |      **2.3781 us** |      **2.2245 us** |  **1.00** |    **0.00** |   **1290.0391** |           **-** |           **-** |          **3968.75 KB** |
| PooledICollectionConstructor |   1000 |    Int |       120.8 us |      0.3084 us |      0.2885 us |  0.46 |    0.00 |     12.6953 |           - |           - |            39.06 KB |
|  StackIEnumerableConstructor |   1000 |    Int |     7,066.3 us |     27.4407 us |     25.6681 us | 26.63 |    0.20 |   2687.5000 |           - |           - |          8273.44 KB |
| PooledIEnumerableConstructor |   1000 |    Int |     9,094.7 us |     13.4187 us |     10.4764 us | 34.28 |    0.27 |     15.6250 |           - |           - |            78.13 KB |
|                              |        |        |                |                |                |       |         |             |             |             |                     |
|  **StackICollectionConstructor** |   **1000** | **String** |       **641.5 us** |      **5.4508 us** |      **5.0986 us** |  **1.00** |    **0.00** |   **2556.6406** |           **-** |           **-** |             **7875 KB** |
| PooledICollectionConstructor |   1000 | String |       587.9 us |      2.0677 us |      1.9341 us |  0.92 |    0.01 |     12.6953 |           - |           - |            39.06 KB |
|  StackIEnumerableConstructor |   1000 | String |    11,974.3 us |     51.6540 us |     43.1335 us | 18.68 |    0.12 |   5281.2500 |           - |           - |         16265.63 KB |
| PooledIEnumerableConstructor |   1000 | String |    14,412.5 us |     33.1251 us |     29.3645 us | 22.46 |    0.19 |     15.6250 |           - |           - |            85.94 KB |
|                              |        |        |                |                |                |       |         |             |             |             |                     |
|  **StackICollectionConstructor** |  **10000** |    **Int** |     **2,642.7 us** |      **8.9169 us** |      **8.3408 us** |  **1.00** |    **0.00** |  **12656.2500** |           **-** |           **-** |            **39125 KB** |
| PooledICollectionConstructor |  10000 |    Int |     1,137.2 us |      3.7774 us |      3.5334 us |  0.43 |    0.00 |     11.7188 |           - |           - |            39.06 KB |
|  StackIEnumerableConstructor |  10000 |    Int |    77,945.2 us |    213.6206 us |    199.8209 us | 29.49 |    0.13 |  41571.4286 |           - |           - |        128367.19 KB |
| PooledIEnumerableConstructor |  10000 |    Int |    81,263.1 us |    209.1411 us |    195.6307 us | 30.75 |    0.12 |           - |           - |           - |            78.13 KB |
|                              |        |        |                |                |                |       |         |             |             |             |                     |
|  **StackICollectionConstructor** |  **10000** | **String** |     **6,332.2 us** |     **35.5261 us** |     **33.2311 us** |  **1.00** |    **0.00** |  **24992.1875** |           **-** |           **-** |          **78187.5 KB** |
| PooledICollectionConstructor |  10000 | String |     8,037.4 us |     13.7404 us |     12.1805 us |  1.27 |    0.01 |           - |           - |           - |            39.06 KB |
|  StackIEnumerableConstructor |  10000 | String |   173,661.9 us |    459.1141 us |    383.3811 us | 27.43 |    0.13 |  41333.3333 |  41333.3333 |  41333.3333 |        256359.38 KB |
| PooledIEnumerableConstructor |  10000 | String |   140,039.6 us |    624.0794 us |    583.7643 us | 22.12 |    0.12 |           - |           - |           - |            85.94 KB |
|                              |        |        |                |                |                |       |         |             |             |             |                     |
|  **StackICollectionConstructor** | **100000** |    **Int** |   **162,361.7 us** |  **3,084.3468 us** |  **3,551.9384 us** |  **1.00** |    **0.00** |  **37500.0000** |  **37500.0000** |  **37500.0000** |        **390943.81 KB** |
| PooledICollectionConstructor | 100000 |    Int |    13,804.1 us |     17.0150 us |     15.0834 us |  0.08 |    0.00 |           - |           - |           - |            39.06 KB |
|  StackIEnumerableConstructor | 100000 |    Int | 1,090,771.2 us | 21,692.6208 us | 24,111.2906 us |  6.72 |    0.19 | 222000.0000 | 186000.0000 | 180000.0000 |       1025026.31 KB |
| PooledIEnumerableConstructor | 100000 |    Int |   805,585.6 us |  1,802.7098 us |  1,598.0553 us |  4.94 |    0.10 |           - |           - |           - |            78.13 KB |
|                              |        |        |                |                |                |       |         |             |             |             |                     |
|  **StackICollectionConstructor** | **100000** | **String** |   **371,341.9 us** |  **7,344.5947 us** | **19,730.7768 us** |  **1.00** |    **0.00** |  **14000.0000** |  **14000.0000** |  **14000.0000** |        **781383.41 KB** |
| PooledICollectionConstructor | 100000 | String |    81,122.6 us |    365.6133 us |    341.9949 us |  0.22 |    0.01 |           - |           - |           - |            39.06 KB |
|  StackIEnumerableConstructor | 100000 | String | 1,854,972.8 us |  4,633.3062 us |  4,333.9975 us |  4.95 |    0.29 | 374000.0000 | 333000.0000 | 331000.0000 |       2049661.74 KB |
| PooledIEnumerableConstructor | 100000 | String | 1,372,659.5 us |  3,622.3863 us |  3,388.3823 us |  3.66 |    0.21 |           - |           - |           - |            85.94 KB |