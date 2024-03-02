## stdlib待选
> https://github.com/stdlib-js/google-summer-of-code/blob/main/ideas.md


### id2 
> https://github.com/stdlib-js/google-summer-of-code/blob/main/ideas.md#implement-a-broader-range-of-statistical-distributions

这个想法的目标是在stdlib中实现SciPy stats中找到的所有分布。分布支持将包括实现用于计算PDF（概率密度函数）、CDF（累积分布函数）、分位数以及其他分布属性的API。此外，stdlib应支持从任何实现的分布中抽取随机变量的API。

预期成果
stdlib用户将能够构造并计算JavaScript中SciPy所有统计分布的各种属性。

涉及软件
不需要运行时依赖。为了提供参考测试结果，将需要SciPy。

所需前置知识
JavaScript, Node.js。熟悉C/C++/Fortran会有所帮助。

项目难度
中等。对于那些属性和矩有复杂公式的分布，可能会出现困难。开发JavaScript实现可能需要咨询C/C++，可能还有Fortran代码。

项目长度
没有明确说明项目长度，但考虑到项目的复杂性和覆盖的广度，可以预见这将是一个中到长期的项目，需要投入相当的时间和精力来完成。


### id3: 
> https://github.com/stdlib-js/google-summer-of-code/blob/main/ideas.md#provide-apis-for-computing-fast-fourier-transforms

这个想法的目标是提供一套与NumPy中可用的快速傅里叶变换（FFT）接口类似的接口，并且这些接口符合数据APIs数组API规范的文档说明。类似于stdlib的BLAS接口，我们可能希望允许更换FFT后端。

一个可能的参考实现，可以作为这个想法的基础，是NumPy中使用的pocketfft：

https://github.com/mreineck/pocketfft
https://gitlab.mpcdf.mpg.de/mtr/pocketfft
预期成果
stdlib用户将能够在stdlib的ndarrays上执行FFT操作。理想情况下，我们还会提供一套C语言API接口。

涉及软件
将需要参考C/Fortran中的参考实现。

所需前置知识
JavaScript, Node.js, C/C++/Fortran

项目难度
难。这可能是一个直接的移植工作，也可能不是。需要更多的研发工作。

### id5: 
> https://github.com/stdlib-js/google-summer-of-code/blob/main/ideas.md#expand-support-for-additional-pseudorandom-number-generators

这个想法的目标是在stdlib中实现各种伪随机数生成器（PRNGs），用于生成伪随机数。目前，项目默认使用梅森旋转（Mersenne Twister）作为其PRNG；然而，尽管这种PRNG很常见，但由于其相对较大的内部状态，并不是理想选择。如果能够提供一系列的PRNGs，如PCG、Philox、Xorshift等，那将是非常好的。

预期成果
stdlib用户将可以根据自己的个人需要和考虑，从多种PRNGs中选择。当需要复现可能使用非stdlib支持的PRNG的数值模拟结果时，拥有多种PRNGs选择将非常有用。此外，一个理想的结果是，如果我们能用一个新的默认PRNG替换MT19937。

涉及软件
不需要其他软件。基于JS的32位限制，我们可能会有些限制。然而，这并不妨碍我们用C语言实现，以用于生成随机数数组。

所需前置知识
JavaScript, Node.js。熟悉C/C++/Fortran会有所帮助。

项目难度
中等/难。这取决于具体情况。一些PRNGs可能很容易实现。其他的则不那么简单。

项目长度
175/350小时。这个想法可以进行调整。

### id7:
> https://github.com/stdlib-js/google-summer-of-code/blob/main/ideas.md#implement-additional-statistical-tests

这个想法的目标是在stdlib中实现各种目前尚未包括的统计测试，但这些测试在其他环境中已被实现，如R、Python（SciPy, statsmodels）、Julia和MATLAB。

预期成果
stdlib将拥有更广泛的统计测试数组，这些测试可以在ndarrays上操作。

涉及软件
不需要其他软件。然而，我们需要进行需求分析，以确定实现这些测试所需的先决包/功能（例如，BLAS、ndarray切片等）。

所需前置知识
JavaScript, Node.js。熟悉R、Python、C/C++将非常有用，因为需要参考实现。

项目难度
难。这取决于参考实现的要求和算法难度。

项目长度
没有具体提及项目的具体时长，但考虑到实现这些统计测试的复杂性，这将是一个中到长期的项目，需要投入相当的时间和精力来完成。

### id27:
> https://github.com/stdlib-js/google-summer-of-code/blob/main/ideas.md#optimization-algorithms

这个想法的目标是在stdlib中引入优化算法。目前stdlib中还没有优化算法。添加线性规划、凸优化、二次规划和/或非线性优化算法将是一个很好的补充。

预期成果
stdlib将拥有一系列广泛的优化算法，用于解决问题。

涉及软件
不需要其他软件。然而，我们需要进行需求分析，以确定实现这些算法所需的先决包/功能（例如，BLAS）。

所需前置知识
JavaScript, Node.js。熟悉R、Python、C/C++将非常有用，因为需要参考实现。

项目难度
难。这取决于参考实现的要求和算法难度。