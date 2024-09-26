# Các loại Design Patterns
 Các Design Patterns được chia làm ba nhóm chính: **Creational (Tạo kiểu)**, **Structural (Cấu trúc)**, và **Behavioral (Hành vi)**.

## Creational
### 1.**Singleton Patterns**
Đảm bảo rằng 1 class chỉ có duy nhất 1 instance và có thể truy cập ở mọi nơi.
#### 
```
public class Log{
    private static Log instance;
    private Log(){

    }
    public static Log getInstance(){
        if(instance == null){
            instance = new Log();
        }
        return instance;
    }

    public void write(String msg){
        System.out.println("Log: " + msg);
    }
}
```
-----
```
import java.lang.annotation.ElementType;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.annotation.Target;

@Target(ElementType.TYPE)  
@Retention(RetentionPolicy.RUNTIME)
public @interface Singleton {
}
```

```
import java.util.HashMap;
import java.util.Map;

public class SingletonManager {
    private static Map<Class<?>, Object> instances = new HashMap<>();

    public static <T> T getInstance(Class<T> clazz) {
        if (instances.containsKey(clazz)) {
            return clazz.cast(instances.get(clazz));
        }

        if (clazz.isAnnotationPresent(Singleton.class)) {
            try {
                T instance = clazz.getDeclaredConstructor().newInstance();
                instances.put(clazz, instance);
                return instance;
            } catch (Exception e) {
                throw new RuntimeException("Create instance failed, class: " + clazz.getName(), e);
            }
        }

        throw new RuntimeException("Class " + clazz.getName() + " can not mark annotation @Singleton");
    }
}
```
```
@Singleton 
public class Log {

    private Log() {
    
    }

    public void writeLog(String message) {
        System.out.println("Log: " + message);
    }
}

```

### 2. **Factory Pattern**
Tạo object mà không để lộ logic khởi tạo
```
public enum VehicleType {
    CAR, MOTORCYCLE, TRUCK
}
```

```
public class Vehicle {
    public void run() {
        System.out.println("-----------");
    }
}
```

```
public class Car extends Vehicle {
    @Override
    public void run() {
        System.out.println("++++++++++.");
    }
}
```

```
public class Truck extends Vehicle {
    @Override
    public void run() {
        System.out.println("__________");
    }
}
```