guava jar包结构：
    android
    guava
        web使用的guava功能
    guava-gwt
    test
    util
    
    
guava模块：
    common
        annotations
        base
            使用和避免null
                Optional类：有子类Present和Absent，这是google对null值的处理，避免代码中出现null值
                      在出现null的时候方法立马变中断了，不再往下进行。
                      快速失败操作拒绝null值，当存在null值的时候，可以想到用guava的此类工具
            前置条件
                Preconditions类方法，验证失败均会抛出异常
                    checkArgument(boolean)
                    checkNotNull(T)
                    checkState(boolean)
                    checkElementIndex(int index, int size):index>=0 && index<size 
                    checkPositionIndex(int index, int size):index>=0 && index<=size
                    checkPositionIndexed(int start, int end, int end) 
            常见Object方法
                重新写了hashCode和equals方法，equals避免了null的情况
            排序
                Ordering类，实现了Comparator接口
                实现了多种排序器，排序器可以链式叠加（注意reverse的用法），也可以使用自定义的排序器
                可以通过排序器来获取结果
                排序在内部还是调用了Collections.sort(Iterator, Comparator)方法
            Throwables
                Throwables类：
                对异常对象的再次抛出，有这种业务逻辑的时候可以考虑
                也有输出异常信息签名的方法
        cache
        collect
            对JDK的拓展
            不可变集合
            新集合类型
            集合工具类
            拓展工具类
        escape  
        eventbus
        gragh
        hash
            散列
        html
        io
            io流和文件的操作
        math
            数学运算
        net
        primitives
            原生类型的操作
            提供了更多对基本数据类型的封装，比如加入了无符号整数的实现
        reflect
            反射机制工具类
        util.concurrent
        xml
    thirdparty
    