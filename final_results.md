# Performance Testing 

## Results duration=15m

## XGBoost Model

### xgboost-model built on python image (Default)

```shell
~ # vegeta attack -duration=15m -targets=targets.txt -max-workers=1 -rate=0 -max-body=0 -timeout=120s | tee results.bin | vegeta report

Requests      [total, rate, throughput]         360603, 400.67, 400.67
Duration      [total, attack, wait]             15m0s, 15m0s, 2.596ms
Latencies     [min, mean, 50, 90, 95, 99, max]  1.844ms, 2.493ms, 2.472ms, 2.763ms, 2.872ms, 3.171ms, 37.216ms
Bytes In      [total, mean]                     0, 0.00
Bytes Out     [total, mean]                     7212060, 20.00
Success       [ratio]                           100.00%
Status Codes  [code:count]                      200:360603  
Error Set:
```

### xgboost-model built on intel/oneapi image

```shell
~ # vegeta attack -duration=15m -targets=targets.txt -max-workers=1 -rate=0 -max-body=0 -timeout=120s | tee results.bin | vegeta report

Requests      [total, rate, throughput]         181813, 202.01, 202.01
Duration      [total, attack, wait]             15m0s, 15m0s, 4.15ms
Latencies     [min, mean, 50, 90, 95, 99, max]  1.785ms, 4.946ms, 4.032ms, 7.605ms, 9.815ms, 18.494ms, 258.8ms
Bytes In      [total, mean]                     0, 0.00
Bytes Out     [total, mean]                     3636260, 20.00
Success       [ratio]                           100.00%
Status Codes  [code:count]                      200:181813  
Error Set:
```

### xgboost-model built on intel/oneapi-aikit image

```shell
~ # vegeta attack -duration=15m -targets=targets.txt -max-workers=1 -rate=0 -max-body=0 -timeout=120s | tee results.bin | vegeta report

Requests      [total, rate, throughput]         178017, 197.80, 197.80
Duration      [total, attack, wait]             15m0s, 15m0s, 3.956ms
Latencies     [min, mean, 50, 90, 95, 99, max]  2.146ms, 5.05ms, 4.151ms, 7.003ms, 10.253ms, 20.096ms, 326.407ms
Bytes In      [total, mean]                     0, 0.00
Bytes Out     [total, mean]                     3560340, 20.00
Success       [ratio]                           100.00%
Status Codes  [code:count]                      200:178017  
Error Set:
```

### xgboost-model built on intel/intel-optimized-ml:xgboost image

```shell
~ # vegeta attack -duration=15m -targets=targets.txt -max-workers=1 -rate=0 -max-body=0 -timeout=120s | tee results.bin | vegeta report

raise XGBoostError(py_str(_LIB.XGBGetLastError()))
xgboost.core.XGBoostError: No device of requested type available. Please check https://software.intel.com/content/www/us/en/develop/articles/intel-oneapi-dpcpp-system-requirements.html -1 (CL_DEVICE_NOT_FOUND)
```

## XGBoost Model converted to Daal4py

### daal4py-model built on python-image (Default)

```shell
~ # vegeta attack -duration=15m -targets=targets.txt -max-workers=1 -rate=0 -max-body=0 -timeout=120s | tee results.bin | vegeta report

Requests      [total, rate, throughput]         564440, 627.16, 627.15
Duration      [total, attack, wait]             15m0s, 15m0s, 1.48ms
Latencies     [min, mean, 50, 90, 95, 99, max]  1.333ms, 1.592ms, 1.565ms, 1.714ms, 1.792ms, 2.001ms, 64.859ms
Bytes In      [total, mean]                     0, 0.00
Bytes Out     [total, mean]                     11288800, 20.00
Success       [ratio]                           100.00%
Status Codes  [code:count]                      200:564440  
Error Set:
```

### daal4py-model built on intel/oneapi image

```shell
~ # vegeta attack -duration=15m -targets=targets.txt -max-workers=1 -rate=0 -max-body=0 -timeout=120s | tee results.bin | vegeta report

Requests      [total, rate, throughput]         478512, 531.68, 531.68
Duration      [total, attack, wait]             15m0s, 15m0s, 1.476ms
Latencies     [min, mean, 50, 90, 95, 99, max]  1.351ms, 1.877ms, 1.762ms, 2.23ms, 2.451ms, 3.372ms, 4.172s
Bytes In      [total, mean]                     0, 0.00
Bytes Out     [total, mean]                     9570240, 20.00
Success       [ratio]                           100.00%
Status Codes  [code:count]                      200:478512  
Error Set:
```

### daal4py-model built on intel/oneapi-aikit image

```shell
~ # vegeta attack -duration=15m -targets=targets.txt -max-workers=1 -rate=0 -max-body=0 -timeout=120s | tee results.bin | vegeta report

Requests      [total, rate, throughput]         494916, 549.91, 549.90
Duration      [total, attack, wait]             15m0s, 15m0s, 1.92ms
Latencies     [min, mean, 50, 90, 95, 99, max]  1.389ms, 1.815ms, 1.725ms, 2.079ms, 2.258ms, 2.926ms, 4.933s
Bytes In      [total, mean]                     0, 0.00
Bytes Out     [total, mean]                     9898320, 20.00
Success       [ratio]                           100.00%
Status Codes  [code:count]                      200:494916  
Error Set:
```

### daal4py-model built on intel/intel-optimized-ml:xgboost image

```shell
~ # vegeta attack -duration=15m -targets=targets.txt -max-workers=1 -rate=0 -max-body=0 -timeout=120s | tee results.bin | vegeta report

raise XGBoostError(py_str(_LIB.XGBGetLastError()))
xgboost.core.XGBoostError: No device of requested type available. Please check https://software.intel.com/content/www/us/en/develop/articles/intel-oneapi-dpcpp-system-requirements.html -1 (CL_DEVICE_NOT_FOUND)
```
