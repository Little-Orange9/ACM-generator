## rand_real

1. `double rand_real()`

   返回一个浮点数类型为`double`，范围为 $[0,1)$ 。

2. `double rand_real(T n)`

   传入一个类型为`T`的参数 $n$ ，`T`需要为可以转换成浮点型的类型。

   返回一个浮点数类型为`double`，范围为 $[0,n)$ 。

3. `double rand_real(T from,T to)`

   传入两个类型为`T`的参数 $from, to$ ，`T`需要为可以转换成浮点型的类型。

   返回一个浮点数类型为`double`，范围为 $[from, to)$ 。

4. `double rand_real(T from,U to)`

   传入两个类型分别为`T,U`的参数 $from, to$ ，`T,U`均需要为可以转换成浮点型的类型。

   返回一个浮点数类型为`double`，范围为 $[from, to)$ 。

5. `double rand_real(const char* format,...)`

   传入一个类似`printf`中的格式控制字符串。

   返回一个浮点数类型为`double`，范围为格式控制字符串所描述。

   格式控制字符串中应该包含一个左括号'['或'('，一个右括号']'或')'表示开闭区间，以及一个逗号分隔左右端点。

   其中左右端点的值可以包含`e`或者`E`作为科学计数法。

   例子：

   ```cpp
   rand_real("[%lf, 3.14e-2]",0.00125);
   rand_real("(%.5lf, 10)",0.12);
   ```
   
   返回浮点数的精度由左右端点精度最大的值决定，默认为 $0.1(10^{-1})$ 。
   
   精度决定了输出时最高可以支持的精度，注意精度不应该超过`double`所允许的限制 $-1$ (即大约 $10^{-14}$ )。
   
   比如对于：`rand_real("[0.001, 0.001]")` ，如果输出的小数位数大于 $3$ 位，那么得到的值就会超出限制。
   
   另外需要注意的是，输出的位数不应该小于最小的精度，这样会因为四舍五入造成值超出限制。

[示例代码](../../../examples/rand_real.cpp)

[返回目录](../../home.md)