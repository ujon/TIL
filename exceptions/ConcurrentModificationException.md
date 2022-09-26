# ConcurrentModificationException

## java.util.ConcurrentModificationException

> lang: JAVA

### cause

주로 Collection을 loop하면서 삭제할 때 실시간으로 index가 변하면서 발생

```java
import java.util.ArrayList;
import java.util.List;

List<int> list = new ArrayList<int>();

list.add(1);
list.add(2);
list.add(3);

for(Integer i : list){
	list.remove(i);
}
```

### solution

`remove()`대신 `removeIf()`를 사용해 어떤 요소를 삭제할 것인지 정의하여 해결 가능

```java
List<Integer> list = new ArrayList<>();

list.add(1);
list.add(2);
list.add(3);

// remove if item is 1 or 3
list.removeIf(x -> x == 1 || x == 3);
```
