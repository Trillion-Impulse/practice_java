# collection framework

***

# what is collection framework
- 데이터를 저장하고 처리하는 데 필요한 다양한 클래스를 제공하는 라이브러리
- List, Set, Queue, Map 인터페이스와 이를 구현한 다양한 클래스들로 구성

---

# 컬렉션 프레임워크의 주요 특징
- 다양한 자료구조 제공
    - 리스트, 세트, 큐, 맵 등 다양한 자료구조를 표준화된 방식으로 제공하여 필요한 자료구조를 쉽게 사용할 수 있다.
- 동적 크기 조정
    - 대부분의 컬렉션 클래스는 크기가 자동으로 조정되어 동적 배열이나 링크드 리스트 기반으로 동작한다.
- 제너릭 지원
    - 컬렉션 클래스는 제너릭을 사용하여 타입 안정성을 보장한다.
    - 예를 들어, List<String>과 같이 특정 타입의 객체만 담을 수 있도록 설정할 수 있다.
- Iterator 패턴
    - 컬렉션은 Iterator를 사용하여 반복적으로 데이터를 처리할 수 있다.
    - 이를 통해 for-each 문법과 같은 간단한 반복문을 사용할 수 있다.
- 병렬 처리
    - 자바 8부터 Stream API를 통해 컬렉션에 대해 병렬 처리 및 다양한 함수형 연산을 할 수 있다.
- 일관성
    - 모든 컬렉션 클래스는 java.util 패키지 내에서 일관된 방식으로 제공
    - import java.util.<인터페이스이름 or 클래스이름>를 통해 라이브러리 호출

***

## List 인터페이스
- 순서가 있는 데이터의 집합
- 중복을 허용한다.

### List의 내부 인터페이스
- ListIterator<E>
    - Iterator와 유사한 ListIterator<E>라는 내부 인터페이스를 제공
    - Iterator<E>의 확장 인터페이스로, 양방향 순회와 수정 기능을 제공

### List의 클래스
1. ArrayList
    - 배열 기반의 동적 리스트
    - 데이터가 많고 빈번한 조회가 필요한 경우에 유용하다.

```
List<String> list = new ArrayList<>();
list.add("Apple");
list.add("Banana");
list.add("Apple");  // 중복 가능

System.out.println(list);  // [Apple, Banana, Apple]
```

2. LinkedList
    - 연결 리스트 구조, 노드를 연결하는 방식
    - 데이터의 삽입 및 삭제가 빈번한 경우에 유리하다.
    - ArrayList와 달리 내부적으로 배열을 사용하지 않는다.
    - 각 요소가 연결 리스트로 연결되어 있어, 리스트 중간에 데이터를 삽입하거나 삭제하는 데 빠르다.

```
List<String> list = new LinkedList<>();
list.add("Apple");
list.add("Banana");
list.add("Orange");

System.out.println(list);  // [Apple, Banana, Orange]

list.remove("Banana");
System.out.println(list);  // [Apple, Orange]
```

3. Vector
    - 동적 배열
    - ArrayList와 비슷하지만 동기화된 메서드를 제공한다.
    - 동기화(synchronization)가 기본적으로 되어 있어, 멀티스레드 환경에서 안전하게 사용할 수 있다.
    - 동기화 때문에 ArrayList보다 성능이 떨어질 수 있다.

```
Vector<String> vector = new Vector<>();
vector.add("Apple");
vector.add("Banana");
vector.add("Orange");

System.out.println("Vector: " + vector);  // [Apple, Banana, Orange]
```

### List의 메서드
- add(E e): 요소를 컬렉션에 추가
- get(int index): 지정된 인덱스에 있는 요소를 반환
- set(int index, E element): 특정 인덱스의 요소 변경
- remove(Object o): 컬렉션에서 특정 요소를 제거
- contains(Object o): 컬렉션에 특정 요소가 포함되어 있는지 확인
- size(): 컬렉션의 크기(요소의 개수)를 반환
- clear(): 컬렉션의 모든 요소를 제거
- isEmpty(): 컬렉션이 비어 있는지 확인
- indexOf(Object o): 특정 요소의 첫 번째 인덱스 찾기
- lastIndexOf(Object o): 특정 요소의 마지막 인덱스 찾기
- subList(int fromIndex, int toIndex): 부분 리스트 반환
- toArray(): 리스트를 배열로 변환

### ListIterator<E>의 메서드
- hasNext(): 다음 요소가 있으면 true, 없으면 false 반환
- next(): 현재 요소를 반환하고 커서를 다음 요소로 이동
- hasPrevious(): 이전 요소가 있으면 true, 없으면 false 반환
- previous(): 현재 요소를 반환하고 커서를 이전 요소로 이동
- add(E e): 현재 커서 위치에서 새로운 요소를 추가
- set(E e): 현재 커서 위치의 요소를 주어진 값으로 변경
- remove(): 현재 커서 위치의 요소를 제거

***

## Set 인터페이스
- 순서가 없다.
- 중복을 허용하지 않는다.

### Set의 클래스
1. HashSet
    - 데이터의 순서를 보장하지 않는다.
    - 빠른 검색을 제공

```
Set<String> set = new HashSet<>();
set.add("Apple");
set.add("Banana");
set.add("Apple");  // 중복 값은 저장되지 않음

System.out.println(set);  // [Apple, Banana]
```

2. LinkedHashSet
    - 삽입 순서를 유지하는 Set
    - 요소가 삽입된 순서대로 반환된다.

```
Set<String> set = new LinkedHashSet<>();
set.add("Apple");
set.add("Banana");
set.add("Apple");  // 중복을 허용하지 않음

System.out.println(set);  // [Apple, Banana] 순서대로 출력
```

3. TreeSet
    - 내부적으로 트리 구조를 사용
    - 데이터가 자동으로 정렬됨
    - 기본적으로 오름차순으로 정렬

```
Set<String> set = new TreeSet<>();
set.add("Apple");
set.add("Banana");
set.add("Orange");

System.out.println(set);  // [Apple, Banana, Orange] 자동 정렬됨
```

### Set의 메서드
- add(E e): 요소를 컬렉션에 추가
- remove(Object o): 컬렉션에서 특정 요소를 제거
- contains(Object o): 컬렉션에 특정 요소가 포함되어 있는지 확인
- size(): 컬렉션의 크기(요소의 개수)를 반환
- clear(): 컬렉션의 모든 요소를 제거
- isEmpty(): 컬렉션이 비어 있는지 확인
- iterator(): 반복자 반환
- addAll(Collection<? extends E> c): 다른 컬렉션의 모든 요소 추가
- removeAll(Collection<?> c): 지정된 컬렉션에 포함된 모든 요소 제거
- retainAll(Collection<?> c): 지정된 컬렉션과 공통된 요소만 남기기
- toArray(): Set을 배열로 변환

***

## Map 인터페이스
- 키(key)와 값(value)의 쌍으로 이루어진 데이터 구조
- 키는 중복되지 않으며, 각 키에 대응하는 값이 하나씩 존재

### Map의 내부 인터페이스
- Map.Entry<K, V>
    - 주로 Map의 entrySet() 메서드를 사용하여 Map.Entry 객체들을 반환
    - Map의 각 키-값 쌍을 나타낸다.
    - Map.Entry는 Map의 항목을 표현하는 객체
    - Map.Entry는 Map에서 키와 값을 동시에 접근할 수 있는 방법을 제공


### Map의 클래스
1. HashMap
    - 키와 값의 쌍을 저장하는 해시 기반 맵
    - 순서는 보장되지 않지만, 빠른 조회 성능을 제공

```
Map<String, Integer> map = new HashMap<>();
map.put("Apple", 3);
map.put("Banana", 2);
System.out.println(map);  // {Apple=3, Banana=2}
System.out.println("Apple count: " + map.get("Apple"));  // 3
```

2. LinkedHashMap
    - HashMap의 특성을 가지면서도, 삽입 순서를 유지
    - 키-값 쌍을 삽입한 순서대로 반환

```
Map<String, Integer> map = new LinkedHashMap<>();
map.put("Apple", 3);
map.put("Banana", 2);
map.put("Orange", 5);

System.out.println(map);  // {Apple=3, Banana=2, Orange=5} 삽입 순서 유지
```

3. TreeMap
    - 내부적으로 이진 탐색 트리를 사용
    - 키가 자동으로 정렬됨
    - 기본적으로 키가 오름차순으로 정렬

```
Map<String, Integer> map = new TreeMap<>();
map.put("Apple", 3);
map.put("Banana", 2);
map.put("Orange", 5);

System.out.println(map);  // {Apple=3, Banana=2, Orange=5} 키 기준으로 자동 정렬됨
```

### Map의 메서드
- put(K key, V value): 키와 값을 매핑하여 맵에 추가
- get(Object key): 지정된 키에 해당하는 값을 반환
- remove(Object key): 지정된 키에 해당하는 키-값 쌍을 맵에서 제거
- containsKey(Object key): 지정된 키가 맵에 있는지 확인
- containsValue(Object value): 값 존재 여부 확인
- size(): 컬렉션의 크기(요소의 개수)를 반환
- clear(): 컬렉션의 모든 요소를 제거
- isEmpty(): 컬렉션이 비어 있는지 확인
- keySet(): 맵의 모든 키 반환
- values(): 맵의 모든 값 반환
- entrySet(): 맵의 모든 키-값 쌍을 Set<Map.Entry<K, V>>로 반환
- putIfAbsent(K key, V value): 맵에 해당키가 없을 경우 값 추가

### Map.Entry<K, V>의 메서드
- 주로 Map의 entrySet() 메서드와 함께 사용
- getKey(): Map.Entry 객체에서 키를 반환
    - 반환 타입은 K이며, Map에서 정의한 키의 타입에 따라 달라짐
- getValue(): Map.Entry 객체에서 값을 반환
    - 반환 타입은 V이며, Map에서 정의한 값의 타입에 따라 달라짐
- setValue(V value): Map.Entry 객체에서 값을 변경
    - Map을 직접 수정하는 것이 아니라, Map.Entry 객체에서 값을 변경하는 것
    - 기존의 값이 새로운 값으로 대체

***

## Queue 인터페이스
- FIFO(First In First Out) 방식으로 동작하는 자료구조인 큐를 다루기 위한 메서드를 제공
- 한쪽 끝에서 데이터를 삽입하고, 다른 쪽 끝에서 데이터를 제거하는 방식으로 동작

### Queue의 클래스
1. LinkedList
    - 큐를 구현한 클래스
    - 양쪽 끝에서의 삽입과 삭제가 빠르다.

```
Queue<String> queue = new LinkedList<>();
queue.offer("Apple");
queue.offer("Banana");

System.out.println(queue.poll());  // Apple (가장 먼저 들어온 값이 나옴)
System.out.println(queue);  // [Banana]
```

2. PriorityQueue
    - 우선순위과 있는 큐
    - 우선순위가 높은 요소가 먼저 나온다.
    - 기본적으로 Comparable을 구현한 객체에 대해 우선순위가 자동으로 적용

```
Queue<Integer> queue = new PriorityQueue<>();
queue.offer(5);
queue.offer(1);
queue.offer(3);

System.out.println(queue);  // [1, 3, 5] 자동으로 우선순위 정렬됨
System.out.println(queue.poll());  // 1 (우선순위가 가장 낮은 값이 먼저 나옴)
```

### Queue의 메서드
- offer(E e): 큐의 끝에 요소를 추가
    - 큐가 가득 차면 예외를 발생시키지 않고 false를 반환
- add(E e): 큐의 끝에 요소를 추가
    - 큐가 가득 차면 예외(IllegalStateException)를 발생
- poll(): 큐에서 첫 번째 요소를 제거하고 반환
    - 큐가 비어 있으면 null을 반환합니다.
- remove(): 큐의 첫 번째 요소를 제거하고 반환
    - 큐가 비어 있으면 예외(NoSuchElementException)를 발생
- peek(): 큐에서 첫 번째 요소를 반환 (제거하지 않음)
    - 큐가 비어 있으면 null을 반환
- element(): 큐의 첫 번째 요소를 반환합니다 (제거하지 않음)
    - 큐가 비어 있으면 예외(NoSuchElementException)를 발생

***

## Deque 인터페이스
- Double Ended Queue
- 양쪽 끝에서 요소를 추가하고 제거할 수 있는 큐
- 큐(FIFO, 선입선출)와 스택(LIFO, 후입선출) 양쪽의 특성을 모두 가질 수 있다.

### Deque의 클래스
1. ArrayDeque
    - 양쪽 끝에서 데이터를 추가하고 제거할 수 있는 덱(Deque)
    - 큐와 스택을 모두 구현할 수 있는 자료구조
    - Queue처럼 큐 연산을 하거나 Stack처럼 후입선출(LIFO) 연산을 할 수 있다.

```
Deque<String> deque = new ArrayDeque<>();
deque.addFirst("Apple");
deque.addLast("Banana");

System.out.println(deque);  // [Apple, Banana]

System.out.println(deque.removeFirst());  // Apple
System.out.println(deque.removeLast());   // Banana
```

### Deque의 메서드
- addFirst(E e): 큐의 앞부분에 요소를 추가
- offerFirst(E e): 큐의 앞부분에 요소를 추가
    - 큐가 가득 차면 false를 반환
- addLast(E e): 큐의 뒷부분에 요소를 추가
- offerLast(E e): 큐의 뒷부분에 요소를 추가
    - 큐가 가득 차면 false를 반환
- pollFirst(): 큐의 앞부분에 있는 요소를 제거하고 반환
    - 큐가 비어 있으면 null을 반환
- removeFirst(): 큐의 앞부분에 있는 요소를 제거하고 반환
    - 큐가 비어 있으면 예외(NoSuchElementException)가 발생
- getFirst(): 큐의 앞부분에 있는 요소를 확인합니다(제거하지 않음)
    - 큐가 비어 있으면 예외(NoSuchElementException)가 발생
- pollLast(): 큐의 뒷부분에 있는 요소를 제거하고 반환
    - 큐가 비어 있으면 null을 반환
- removeLast(): 큐의 뒷부분에 있는 요소를 제거하고 반환
    - 큐가 비어 있으면 예외(NoSuchElementException)가 발생
- getLast(): 큐의 뒷부분에 있는 요소를 확인합니다(제거하지 않음)
    - 큐가 비어 있으면 예외(NoSuchElementException)가 발생
- peekFirst(): 큐의 앞부분에 있는 요소를 반환 (제거하지 않음)
    - 큐가 비어 있으면 null을 반환
- peekLast(): 큐의 뒷부분에 있는 요소를 반환 (제거하지 않음)
    - 큐가 비어 있으면 null을 반환

***

## Iterator 인터페이스
- 컬렉션의 요소를 순차적으로 접근하고, 요소를 제거하는 기능을 제공하는 인터페이스

```
List<String> list = new ArrayList<>();
list.add("Apple");
list.add("Banana");
list.add("Orange");

// Iterator를 사용하여 리스트 순회
Iterator<String> iterator = list.iterator();
        
while (iterator.hasNext()) {
    String element = iterator.next();
    System.out.println("Element: " + element);
            
    // "Banana" 요소를 제거
    if (element.equals("Banana")) {
        iterator.remove();
    }
}
        
System.out.println("List after removal: " + list);  // [Apple, Orange]
```

### Iterator의 메서드
- hasNext(): 더 이상 탐색할 요소가 있는지 확인
- next(): 다음 요소 반환
- remove(): 마지막으로 반환된 요소를 컬렉션에서 제거

***

## Spliterator 인터페이스
- 자바 8에서 추가된 순차적 또는 병렬 스트림 처리를 지원하는 인터페이스
- 컬렉션을 병렬로 처리할 수 있도록 돕기 위해 설계
- 기존의 Iterator와 비슷한 기능을 제공하면서도, 병렬 처리와 분할 작업을 보다 효율적으로 처리
- 컬렉션을 분할하고, 여러 스레드를 사용하여 병렬로 처리할 수 있는 방법을 제공

### Spliterator의 메서드
- tryAdvance(Consumer<? super T> action)
    - 순차적으로 컬렉션의 각 요소에 대해 지정된 Consumer 액션을 적용
    - 한 번에 하나의 요소를 처리
    - 요소가 있으면 true를 반환하고, 없으면 false를 반환
- forEachRemaining(Consumer<? super T> action)
    - 남은 모든 요소에 대해 지정된 Consumer 액션을 적용
    - tryAdvance()와는 달리, 남은 모든 요소에 대해 일괄적으로 처리
- trySplit()
    - 현재 Spliterator를 나누어, 두 개의 Spliterator로 분할할 수 있으면 하나를 반환

```
List<String> list = Arrays.asList("Apple", "Banana", "Grape", "Orange", "Peach");

// Spliterator 생성
Spliterator<String> spliterator = list.spliterator();

// 순차적으로 각 요소를 처리 (tryAdvance 사용)
System.out.println("순차적 처리 (tryAdvance):");
while (spliterator.tryAdvance(System.out::println)) {
// 요소가 있을 때마다 출력
}

// 새로 Spliterator를 생성하여, forEachRemaining 사용
spliterator = list.spliterator();  // 새로 생성
System.out.println("\n남은 모든 요소 처리 (forEachRemaining):");
spliterator.forEachRemaining(System.out::println);

// 병렬 처리 예시
// parallelStream()을 사용하여 병렬 처리
System.out.println("\n병렬 처리:");
list.parallelStream().forEach(System.out::println);

// Spliterator의 trySplit() 예시: 컬렉션을 반으로 나눔
spliterator = list.spliterator();
Spliterator<String> split = spliterator.trySplit();  // 반으로 나눔

// 첫 번째 Spliterator의 요소 처리
System.out.println("\n첫 번째 Spliterator 처리:");
split.forEachRemaining(System.out::println);

// 두 번째 Spliterator의 요소 처리
System.out.println("\n두 번째 Spliterator 처리:");
spliterator.forEachRemaining(System.out::println);
```

- estimateSize()
    - 남아 있는 요소의 대략적인 개수를 반환

```
long size = spliterator.estimateSize();
```

- characteristics()
    - Spliterator의 특성을 반환하는 비트 플래그를 반환
    - 예를 들어 ORDERED, SIZED, DISTINCT 등의 특성을 나타낼 수 있다.

```
int characteristics = spliterator.characteristics();
```

- getComparator()
    - Spliterator가 정렬 가능한 경우, 그 정렬 기준을 나타내는 Comparator를 반환

```
Comparator<? super T> comparator = spliterator.getComparator();
```

***

## Collections 클래스
- 컬렉션을 다루는 다양한 유틸리티 메서드를 제공
- 예를 들어, 컬렉션의 정렬, 검색, 동기화, 최소값/최대값 구하기 등의 작업을 할 수 있다.

```
import java.util.*;

List<Integer> list = new ArrayList<>();
list.add(3);
list.add(1);
list.add(2);

// 리스트 정렬
Collections.sort(list);
System.out.println("Sorted List: " + list);  // [1, 2, 3]
```

### Collections의 메서드
- sort(List<T> list): 리스트를 오름차순으로 정렬
- reverse(List<?> list): 리스트를 역순으로 변경
- copy(List<? super T> dest, List<? extends T> src): 리스트 복사
    - src 리스트의 요소를 dest 리스트에 복사
    - dest 리스트는 src 리스트와 크기가 같거나 더 커야 한다.
    - 만약 dest 리스트가 더 작으면 IndexOutOfBoundsException이 발생
- fill(List<? super T> list, T obj): 리스트의 모든 요소를 지정된 값으로 채우기
- swap(List<?> list, int i, int j): 리스트의 지정된 두 인덱스의 요소를 교환
- shuffle(List<?> list): 리스트의 요소를 무작위로 섞기
- binarySearch(List<? extends Comparable<? super T>> list, T key)
    - 이진 검색을 사용하여 정렬된 리스트에서 특정 요소의 인덱스를 찾기
- synchronizedList(List<T> list): 주어진 리스트를 동기화된 리스트로 변환
- unmodifiableList(List<? extends T> list): 주어진 리스트를 읽기 전용 리스트로 변환
- emptyList(): 빈 리스트 반환, 수정 불가, 읽기 전용
- max(Collection<? extends T> coll): 최대값 반환
- min(Collection<? extends T> coll): 최소값 반환
    - 최소값을 찾기 위해 요소는 Comparable을 구현해야 한다.
- frequency(Collection<?> c, Object o): 특정 요소의 빈도 수 찾기
    - 컬렉션에 o가 없다면 0을 반환
- singletonList(T o): 단일 요소를 포함하는 리스트 반환, 수정 불가, 읽기 전용

```
// 1. List 생성
List<String> list = new ArrayList<>(Arrays.asList("Banana", "Apple", "Grape", "Orange", "Peach"));
List<String> copyList = new ArrayList<>(Arrays.asList("Empty", "Empty", "Empty", "Empty", "Empty"));

// 2. Collections.sort() - 리스트 정렬
Collections.sort(list);
System.out.println("정렬된 리스트: " + list);  // [Apple, Banana, Grape, Orange, Peach]

// 3. Collections.reverse() - 리스트 순서 반대로 뒤집기
Collections.reverse(list);
System.out.println("반대로 뒤집은 리스트: " + list);  // [Peach, Orange, Grape, Banana, Apple]

// 4. Collections.copy() - 리스트 복사
Collections.copy(copyList, list);  // list의 요소를 copyList로 복사
System.out.println("복사된 리스트: " + copyList);  // [Apple, Banana, Grape, Orange, Peach]

// 5. Collections.fill() - 리스트 모든 요소 채우기
Collections.fill(list, "Mango");
System.out.println("Mango로 채운 리스트: " + list);  // [Mango, Mango, Mango, Mango, Mango]

// 6. Collections.swap() - 리스트 요소 교환
Collections.swap(list, 0, 4);  // 첫 번째와 마지막 요소를 교환
System.out.println("요소 교환 후 리스트: " + list);  // [Peach, Banana, Grape, Orange, Apple]

// 7. Collections.shuffle() - 리스트 섞기
Collections.shuffle(list);
System.out.println("섞은 리스트: " + list);  // 예시 출력: [Apple, Grape, Peach, Banana, Orange]

// 8. Collections.binarySearch() - 이진 검색
List<Integer> numberList = Arrays.asList(1, 3, 5, 7, 9);
int index = Collections.binarySearch(numberList, 5);
System.out.println("이진 검색 결과 (값 5의 인덱스): " + index);  // 2

// 9. Collections.synchronizedList() - 동기화된 리스트
List<String> syncList = Collections.synchronizedList(new ArrayList<>(list));
System.out.println("동기화된 리스트: " + syncList);

// 10. Collections.unmodifiableList() - 읽기 전용 리스트
List<String> unmodifiableList = Collections.unmodifiableList(new ArrayList<>(list));
System.out.println("읽기 전용 리스트: " + unmodifiableList);

// 11. Collections.emptyList() - 빈 리스트
List<String> emptyList = Collections.emptyList();
System.out.println("빈 리스트: " + emptyList);  // []

// 12. Collections.max() - 최대값 찾기
System.out.println("리스트에서 최대값: " + Collections.max(list));  // Peach

// 13. Collections.min() - 최소값 찾기
System.out.println("리스트에서 최소값: " + Collections.min(list));  // Apple (기본적으로 문자열의 사전식 비교)

// 14. Collections.frequency() - 요소의 빈도수 구하기
int frequency = Collections.frequency(list, "Apple");
System.out.println("'Apple'의 빈도수: " + frequency);  // 1

// 15. Collections.singletonList() - 하나의 요소를 가진 리스트 생성
List<String> singletonList = Collections.singletonList("OnlyOne");
System.out.println("하나의 요소를 가진 리스트: " + singletonList);  // [OnlyOne]
```

***

## Arrays 클래스
- 배열을 다루는 유틸리티 클래스
- 배열을 리스트로 변환하거나 배열을 정렬, 검색, 복사, 비교 등의 작업을 할 수 있다.
- 모든 메서드는 정적 메서드로 제공

### Arrays의 메서드
- sort(T[] a): 배열을 오름차순으로 정렬
- sort(T[] a, Comparator<? super T> c): 배열을 주어진 Comparator를 기준으로 정렬
- binarySearch(T[] a, T key): 정렬된 배열에서 이진 검색을 사용해 key의 인덱스를 찾는다.
- copyOf(T[] original, int newLength): 배열을 지정된 길이로 복사
    - 길이가 더 길면 나머지는 기본값으로 채워짐
- copyOfRange(T[] original, int from, int to): 배열의 특정 범위만 복사
- equals(Object[] a, Object[] a2): 두 배열이 동일한지 비교
- fill(T[] a, T val): 배열의 모든 요소를 주어진 값으로 채움
- toString(T[] a): 배열을 문자열로 변환
- asList(T... a): 배열을 List로 변환

```
// 1. 배열 생성
int[] arr = {5, 2, 8, 1, 3};

// 2. Arrays.sort() - 배열 정렬
Arrays.sort(arr);  // 오름차순 정렬
System.out.println("정렬된 배열: " + Arrays.toString(arr));  // [1, 2, 3, 5, 8]

// 3. Arrays.binarySearch() - 이진 탐색
int index = Arrays.binarySearch(arr, 5);  // 값 5의 위치 찾기
System.out.println("5의 위치: " + index);  // 3 (배열이 정렬되어 있어야 함)

// 4. Arrays.copyOf() - 배열 복사
int[] copiedArr = Arrays.copyOf(arr, 7);  // 크기를 7로 지정해서 복사
System.out.println("복사된 배열: " + Arrays.toString(copiedArr));  // [1, 2, 3, 5, 8, 0, 0]

// 5. Arrays.copyOfRange() - 배열 일부 복사
int[] rangeArr = Arrays.copyOfRange(arr, 1, 4);  // 인덱스 1부터 3까지 복사
System.out.println("부분 복사된 배열: " + Arrays.toString(rangeArr));  // [2, 3, 5]

// 6. Arrays.equals() - 배열 비교
int[] arr2 = {1, 2, 3, 5, 8};
System.out.println("배열이 같은가? " + Arrays.equals(arr, arr2));  // true

// 7. Arrays.fill() - 배열 채우기
Arrays.fill(arr, 0);  // 배열을 모두 0으로 채움
System.out.println("배열을 0으로 채운 후: " + Arrays.toString(arr));  // [0, 0, 0, 0, 0]

// 8. Arrays.toString() - 배열을 문자열로 출력
System.out.println("배열 출력: " + Arrays.toString(arr2));  // [1, 2, 3, 5, 8]

// 9. Arrays.asList() - 배열을 List로 변환
List<Integer> list = Arrays.asList(1, 2, 3, 5, 8);
System.out.println("배열을 List로 변환: " + list);  // [1, 2, 3, 5, 8]
```

***
