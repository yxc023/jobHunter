# 单例模式
## 实现与说明
### java
#### 实现例子

    public class A {
        private static A a;
        private A() {

        }

        public static A newInstance() {
            if (a != null) {
              return a;
            }
            // 创建时代码做同步处理
            synchronized(A.class) {
                if (a != null) {
                    return a;
                }
                a = new A();
                // ... other init operation
                return a;
            }
        }
    }

#### 用例
1. Calendar类
