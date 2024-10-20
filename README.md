# [pprof](https://github.com/google/pprof)

pprof is a tool for visualization and analysis of profiling data.

pprof reads a collection of profiling samples and generates reports to visualize and help analyze the data. It can generate both text and graphical reports (through the use of the dot visualization package).

![main-pprof](output/main-pprof.png)

# [gprof](https://sourceware.org/binutils/docs/gprof/index.html)

gprof is the GNU profiler and you can use it to determine which parts of a program are taking most of the execution time.

❌ No support for muti-threaded applications.

```
             Call graph (explanation follows)


granularity: each sample hit covers 2 byte(s) for 0.27% of 3.64 seconds

index % time    self  children    called     name
                0.00    0.64       1/4           void std::__invoke_impl<void, void (*)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const*, std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>, std::reference_wrapper<std::vector<double, std::allocator<double> > const> >(std::__invoke_other, void (*&&)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const*&&, std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>&&, std::reference_wrapper<std::vector<double, std::allocator<double> > const>&&) [10]
                0.00    1.92       3/4           main [2]
[1]     70.5    0.00    2.57       4         bench(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&) [1]
                0.00    1.14       2/2           sum2(std::vector<double, std::allocator<double> > const&) [3]
                0.00    1.07       2/2           sum1(std::vector<double, std::allocator<double> > const&) [4]
                0.00    0.36       1/1           sum3(std::vector<double, std::allocator<double> > const&) [14]
                0.00    0.00       5/5           std::common_type<std::chrono::duration<long, std::ratio<1l, 1000000000l> >, std::chrono::duration<long, std::ratio<1l, 1000000000l> > >::type std::chrono::operator-<std::chrono::_V2::system_clock, std::chrono::duration<long, std::ratio<1l, 1000000000l> >, std::chrono::duration<long, std::ratio<1l, 1000000000l> > >(std::chrono::time_point<std::chrono::_V2::system_clock, std::chrono::duration<long, std::ratio<1l, 1000000000l> > > const&, std::chrono::time_point<std::chrono::_V2::system_clock, std::chrono::duration<long, std::ratio<1l, 1000000000l> > > const&) [62]
                0.00    0.00       5/5           std::chrono::duration<double, std::ratio<1l, 1000l> >::duration<long, std::ratio<1l, 1000000000l>, void>(std::chrono::duration<long, std::ratio<1l, 1000000000l> > const&) [61]
                0.00    0.00       5/11          std::chrono::duration<double, std::ratio<1l, 1000l> >::count() const [45]
-----------------------------------------------
                                                 <spontaneous>
[2]     58.3    0.00    2.12                 main [2]
                0.00    1.92       3/4           bench(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&) [1]
                0.00    0.20       1/1           std::vector<double, std::allocator<double> >::vector(unsigned long, double const&, std::allocator<double> const&) [23]
                0.00    0.00       3/3           std::reference_wrapper<std::vector<double, std::allocator<double> > const> std::ref<std::vector<double, std::allocator<double> > const>(std::vector<double, std::allocator<double> > const&) [104]
                0.00    0.00       3/3           std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)> std::ref<double (std::vector<double, std::allocator<double> > const&)>(double (&)(std::vector<double, std::allocator<double> > const&)) [103]
                0.00    0.00       3/3           std::jthread::jthread<void (&)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const (&) [5], std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>, std::reference_wrapper<std::vector<double, std::allocator<double> > const>, void>(void (&)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const (&) [5], std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>&&, std::reference_wrapper<std::vector<double, std::allocator<double> > const>&&) [100]
                0.00    0.00       2/2           std::jthread::~jthread() [131]
                0.00    0.00       1/1           std::vector<double, std::allocator<double> >::~vector() [156]
-----------------------------------------------
                0.00    1.14       2/2           bench(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&) [1]
[3]     31.2    0.00    1.14       2         sum2(std::vector<double, std::allocator<double> > const&) [3]
                0.28    0.79       2/2           double std::accumulate<__gnu_cxx::__normal_iterator<double const*, std::vector<double, std::allocator<double> > >, double, double (*)(double, double)>(__gnu_cxx::__normal_iterator<double const*, std::vector<double, std::allocator<double> > >, __gnu_cxx::__normal_iterator<double const*, std::vector<double, std::allocator<double> > >, double, double (*)(double, double)) [5]
                0.02    0.03       2/5           std::vector<double, std::allocator<double> >::end() const [31]
                0.00    0.03       2/5           std::vector<double, std::allocator<double> >::begin() const [34]
-----------------------------------------------
                0.00    1.07       2/2           bench(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&) [1]
[4]     29.5    0.00    1.07       2         sum1(std::vector<double, std::allocator<double> > const&) [4]
                0.38    0.62       2/2           double std::accumulate<__gnu_cxx::__normal_iterator<double const*, std::vector<double, std::allocator<double> > >, double>(__gnu_cxx::__normal_iterator<double const*, std::vector<double, std::allocator<double> > >, __gnu_cxx::__normal_iterator<double const*, std::vector<double, std::allocator<double> > >, double) [6]
                0.02    0.03       2/5           std::vector<double, std::allocator<double> >::end() const [31]
                0.00    0.03       2/5           std::vector<double, std::allocator<double> >::begin() const [34]
-----------------------------------------------
                0.28    0.79       2/2           sum2(std::vector<double, std::allocator<double> > const&) [3]
[5]     29.3    0.28    0.79       2         double std::accumulate<__gnu_cxx::__normal_iterator<double const*, std::vector<double, std::allocator<double> > >, double, double (*)(double, double)>(__gnu_cxx::__normal_iterator<double const*, std::vector<double, std::allocator<double> > >, __gnu_cxx::__normal_iterator<double const*, std::vector<double, std::allocator<double> > >, double, double (*)(double, double)) [5]
                0.17    0.15 135829439/263561189     _ZN9__gnu_cxxeqIPKdSt6vectorIdSaIdEEEEbRKNS_17__normal_iteratorIT_T0_EESB_QrqXeqcldtfL0p_4baseEcldtfL0p0_4baseERSt14convertible_toIbEE [13]
                0.12    0.00 137318222/264787326     __gnu_cxx::__normal_iterator<double const*, std::vector<double, std::allocator<double> > >::operator++() [18]
                0.12    0.00 136889883/264960449     std::remove_reference<double&>::type&& std::move<double&>(double&) [17]
                0.12    0.00 137352337/260815399     add_doubles(double, double) [19]
                0.10    0.00 138877857/266581286     __gnu_cxx::__normal_iterator<double const*, std::vector<double, std::allocator<double> > >::operator*() const [20]
-----------------------------------------------
                0.38    0.62       2/2           sum1(std::vector<double, std::allocator<double> > const&) [4]
[6]     27.6    0.38    0.62       2         double std::accumulate<__gnu_cxx::__normal_iterator<double const*, std::vector<double, std::allocator<double> > >, double>(__gnu_cxx::__normal_iterator<double const*, std::vector<double, std::allocator<double> > >, __gnu_cxx::__normal_iterator<double const*, std::vector<double, std::allocator<double> > >, double) [6]
                0.16    0.14 127731744/263561189     _ZN9__gnu_cxxeqIPKdSt6vectorIdSaIdEEEEbRKNS_17__normal_iteratorIT_T0_EESB_QrqXeqcldtfL0p_4baseEcldtfL0p0_4baseERSt14convertible_toIbEE [13]
                0.12    0.00 128070566/264960449     std::remove_reference<double&>::type&& std::move<double&>(double&) [17]
                0.12    0.00 127469099/264787326     __gnu_cxx::__normal_iterator<double const*, std::vector<double, std::allocator<double> > >::operator++() [18]
                0.10    0.00 127703424/266581286     __gnu_cxx::__normal_iterator<double const*, std::vector<double, std::allocator<double> > >::operator*() const [20]
-----------------------------------------------
                                                 <spontaneous>
[7]     22.5    0.82    0.00                 _init [7]
-----------------------------------------------
                0.00    0.64       1/1           std::thread::_Invoker<std::tuple<void (*)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const*, std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>, std::reference_wrapper<std::vector<double, std::allocator<double> > const> > >::operator()() [9]
[8]     17.6    0.00    0.64       1         void std::thread::_Invoker<std::tuple<void (*)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const*, std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>, std::reference_wrapper<std::vector<double, std::allocator<double> > const> > >::_M_invoke<0ul, 1ul, 2ul, 3ul>(std::_Index_tuple<0ul, 1ul, 2ul, 3ul>) [8]
                0.00    0.64       1/1           std::__invoke_result<void (*)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const*, std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>, std::reference_wrapper<std::vector<double, std::allocator<double> > const> >::type std::__invoke<void (*)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const*, std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>, std::reference_wrapper<std::vector<double, std::allocator<double> > const> >(void (*&&)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const*&&, std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>&&, std::reference_wrapper<std::vector<double, std::allocator<double> > const>&&) [11]
                0.00    0.00       7/7           std::remove_reference<std::tuple<void (*)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const*, std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>, std::reference_wrapper<std::vector<double, std::allocator<double> > const> >&>::type&& std::move<std::tuple<void (*)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const*, std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>, std::reference_wrapper<std::vector<double, std::allocator<double> > const> >&>(std::tuple<void (*)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const*, std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>, std::reference_wrapper<std::vector<double, std::allocator<double> > const> >&) [48]
                0.00    0.00       2/2           std::tuple_element<2ul, std::tuple<void (*)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const*, std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>, std::reference_wrapper<std::vector<double, std::allocator<double> > const> > >::type&& std::get<2ul, void (*)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const*, std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>, std::reference_wrapper<std::vector<double, std::allocator<double> > const> >(std::tuple<void (*)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const*, std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>, std::reference_wrapper<std::vector<double, std::allocator<double> > const> >&&) [136]
                0.00    0.00       2/2           std::tuple_element<1ul, std::tuple<void (*)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const*, std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>, std::reference_wrapper<std::vector<double, std::allocator<double> > const> > >::type&& std::get<1ul, void (*)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const*, std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>, std::reference_wrapper<std::vector<double, std::allocator<double> > const> >(std::tuple<void (*)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const*, std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>, std::reference_wrapper<std::vector<double, std::allocator<double> > const> >&&) [135]
                0.00    0.00       2/2           std::tuple_element<0ul, std::tuple<void (*)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const*, std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>, std::reference_wrapper<std::vector<double, std::allocator<double> > const> > >::type&& std::get<0ul, void (*)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const*, std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>, std::reference_wrapper<std::vector<double, std::allocator<double> > const> >(std::tuple<void (*)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const*, std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>, std::reference_wrapper<std::vector<double, std::allocator<double> > const> >&&) [134]
                0.00    0.00       1/1           std::tuple_element<3ul, std::tuple<void (*)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const*, std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>, std::reference_wrapper<std::vector<double, std::allocator<double> > const> > >::type&& std::get<3ul, void (*)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const*, std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>, std::reference_wrapper<std::vector<double, std::allocator<double> > const> >(std::tuple<void (*)(char const*, double (*)(std::vector<double, std::allocator<double> > const&), std::vector<double, std::allocator<double> > const&), char const*, std::reference_wrapper<double (std::vector<double, std::allocator<double> > const&)>, std::reference_wrapper<std::vector<double, std::allocator<double> > const> >&&) [161]
...
```

# [perf](https://perfwiki.github.io/main)

Linux profiling with performance counters

`perf` can instrument CPU performance counters, tracepoints, kprobes, and uprobes (dynamic tracing). It is capable of lightweight profiling.

![main-perf](output/main-perf.png)
