# 单例模式
## 实现与说明
### java

    public class A {
        private static A a;
        private A() {

        }

        public static A newInstance() {
            if (a != null) {
              return a;
            }
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
