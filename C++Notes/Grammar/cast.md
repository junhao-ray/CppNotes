# force type convertion

   1. static_cast
   2. interpret_cast
   3. const_cast
   4. dynamic_cast

为了区分出类型转换的严重程度

+ static_cast 用来比较自然的低风险的转换，比如int和float和char之间的转换，而不能在不同类型的指针间转换，int与指针间的转换，不同类型的引用间的转换
  
+ reinterpret_cast 不同类型的指针，引用，以及指针和容纳得下指针的整数类型间的转换，执行逐个bit的拷贝

+ 
