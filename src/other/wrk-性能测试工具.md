## 性能测试工具使用
1.安装
```
git clone https://github.com/wg/wrk
cd wrk
make # 编译

cp wrk /usr/local/sbin # 二进制文件 放入非管理员目录，可直接运行命令
```

> wrk http://163.com

```
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    32.49ms   56.14ms 230.86ms   84.38%
    Req/Sec   637.05    222.35     1.09k    63.00%
  12710 requests in 10.03s, 6.71MB read
Requests/sec:   1267.57
Transfer/sec:    685.72KB
```