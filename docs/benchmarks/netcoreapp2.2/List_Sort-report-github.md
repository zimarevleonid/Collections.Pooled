``` ini

BenchmarkDotNet=v0.11.3, OS=Windows 10.0.17763.292 (1809/October2018Update/Redstone5)
Intel Core i7-6700HQ CPU 2.60GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
.NET Core SDK=3.0.100-preview-009812
  [Host] : .NET Core 2.2.1 (CoreCLR 4.6.27207.03, CoreFX 4.6.27207.03), 64bit RyuJIT
  Core   : .NET Core 2.2.1 (CoreCLR 4.6.27207.03, CoreFX 4.6.27207.03), 64bit RyuJIT

Job=Core  Runtime=Core  InvocationCount=1  
UnrollFactor=1  

```
|            Method |      N |       Mean |     Error |    StdDev | Ratio | RatioSD | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|------------------ |------- |-----------:|----------:|----------:|------:|--------:|------------:|------------:|------------:|--------------------:|
|      **ListSort_Int** | **100000** |   **6.582 ms** | **0.1295 ms** | **0.2431 ms** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
|    PooledSort_Int | 100000 |   6.658 ms | 0.1412 ms | 0.2916 ms |  1.02 |    0.06 |           - |           - |           - |                   - |
|   ListSort_String | 100000 | 198.596 ms | 0.8667 ms | 0.7238 ms | 30.55 |    1.17 |           - |           - |           - |                   - |
| PooledSort_String | 100000 | 202.985 ms | 0.4982 ms | 0.4416 ms | 31.20 |    1.15 |           - |           - |           - |                   - |
|                   |        |            |           |           |       |         |             |             |             |                     |
|      **ListSort_Int** | **200000** |  **13.525 ms** | **0.2402 ms** | **0.2006 ms** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
|    PooledSort_Int | 200000 |  13.484 ms | 0.1081 ms | 0.0958 ms |  1.00 |    0.02 |           - |           - |           - |                   - |
|   ListSort_String | 200000 | 426.671 ms | 2.2325 ms | 1.9790 ms | 31.55 |    0.48 |           - |           - |           - |                   - |
| PooledSort_String | 200000 | 412.636 ms | 2.3982 ms | 2.2432 ms | 30.52 |    0.53 |           - |           - |           - |                   - |