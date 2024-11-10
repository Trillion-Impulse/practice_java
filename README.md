# java.lang
***
# 클래스
1. 기본 클래스
    - Object: 모든 Java 클래스의 최상위 부모 클래스입니다.
        - equals(), hashCode(), toString() 등 기본적인 메서드를 제공합니다. 
    - Class: 클래스 메타데이터를 제공하는 클래스입니다.
        - 리플렉션(Reflection)을 사용하여 클래스의 정보나 메서드를 동적으로 조회할 수 있습니다. 
    - String: 문자열을 처리하는 클래스로, 불변(immutable) 객체입니다.
        - 문자열 연결, 비교, 치환 등을 처리하는 메서드를 제공합니다. 
    - StringBuilder: 가변적인 문자열을 처리하는 클래스입니다.
        - 문자열을 변경할 수 있도록 설계되어 성능상 이점이 있습니다. 
    - StringBuffer: StringBuilder와 비슷하지만, 스레드 안전성을 제공합니다.
        - 멀티스레드 환경에서 안전하게 문자열을 변경할 수 있습니다. 
    - Math: 수학적인 함수들을 제공하는 클래스입니다.
        - (예: pow(), sqrt(), abs(), random())
    - System: 시스템 관련 기능을 제공합니다.
        - (예: System.out.println(), System.exit(), currentTimeMillis())
    - Runtime: Java 애플리케이션의 런타임 환경을 관리하는 클래스입니다.
        - 시스템 자원 사용, 가비지 컬렉션 등을 관리합니다. 
    - Thread: 스레드를 생성하고 관리하는 클래스입니다.
        - 멀티스레드 프로그램을 작성할 때 사용됩니다.
3. 멀티스레딩 관련 클래스
    - Thread: 스레드를 생성하고 제어하는 클래스입니다.
        - Thread 객체를 사용하거나 Runnable 인터페이스를 구현하여 멀티스레드를 구현할 수 있습니다. 
    - Runnable: 멀티스레딩을 위한 인터페이스로, 스레드가 실행할 작업을 정의합니다. 
    - ThreadLocal: 스레드마다 독립적인 값을 제공하는 클래스입니다.
        - 주로 스레드 안전성을 제공할 때 사용됩니다. 
    - Thread.State: 스레드의 상태를 나타내는 열거형입니다.
        - 예를 들어 NEW, RUNNABLE, WAITING, TIMED_WAITING, TERMINATED 등이 있습니다.
4. 기타 주요 클래스
    - Process: 외부 프로세스를 실행하고 제어하는 클래스입니다. 
    - ProcessBuilder: 외부 프로세스를 시작하고 관리하는 클래스입니다. 
    - Cloneable: 객체 복제를 지원하는 인터페이스입니다.
        - clone() 메서드를 통해 객체의 복제본을 생성할 수 있습니다. 
    - Comparable: 객체를 비교하는 인터페이스로, 주로 객체 정렬을 위해 사용됩니다. 
    - Enum: 열거형 클래스를 정의하는 기본 클래스입니다.
        - 사용자 정의 열거형을 만들 때 Enum을 상속하여 사용합니다.
5. 기타 유틸리티 클래스
    - Boolean: boolean 기본 타입을 감싸는 클래스입니다.
        - parseBoolean(), toString() 등 메서드를 제공합니다.
    - Character: char 기본 타입을 감싸는 클래스입니다.
        - 문자의 유효성 검사나, 대소문자 변환, 문자 관련 연산을 제공합니다. 
    - Byte: byte 기본 타입을 감싸는 클래스입니다.
        - 바이트 연산을 다루는 다양한 메서드를 제공합니다. 
    - Short: short 기본 타입을 감싸는 클래스입니다. 
    - Integer: int 기본 타입을 감싸는 클래스입니다.
        - parseInt(), toString() 등의 메서드를 제공합니다. 
    - Long: long 기본 타입을 감싸는 클래스입니다. 
    - Float: float 기본 타입을 감싸는 클래스입니다. 
    - Double: double 기본 타입을 감싸는 클래스입니다. 
    - Void: void를 나타내는 클래스입니다.
        - 주로 리플렉션에서 사용됩니다.
6. 기타
    - StringTokenizer: 문자열을 구분자로 나누는 클래스입니다.
        - 특정 구분자를 기준으로 문자열을 분리하는 데 사용됩니다. 
    - Stack: LIFO(Last In, First Out) 구조인 스택을 구현한 클래스입니다. 
    - Character.UnicodeBlock: 유니코드 문자 블록을 나타내는 열거형입니다.
        - 문자 블록을 사용하여 문자를 분류하거나 범위 검사를 할 수 있습니다.

***

# 인터페이스
Cloneable - 객체 복제를 가능하게 하는 인터페이스
Comparable<T> - 객체의 자연 순서를 정의하는 인터페이스
Runnable - 멀티스레딩을 위한 인터페이스
Serializable - 객체를 직렬화할 수 있게 하는 인터페이스
CharSequence - 문자열을 나타내는 인터페이스
Appendable - 문자열을 추가할 수 있는 객체를 나타내는 인터페이스
Iterable<T> - 반복 가능한 객체를 나타내는 인터페이스
AutoCloseable - 자원을 자동으로 닫을 수 있게 하는 인터페이스
InvocationHandler: 동적 프록시 객체의 메서드 호출을 처리하는 인터페이스
UncaughtExceptionHandler: 스레드에서 발생한 예외를 처리하는 인터페이스
Observer: 옵저버 패턴을 구현하는 인터페이스
ThreadLocal: 각 스레드마다 독립적인 값을 제공하는 인터페이스

***

# 예외 및 오류 처리 클래스

## Throwable
- 모든 예외 및 오류의 최상위 클래스입니다.
- Throwable은 Exception과 Error의 부모 클래스다.
- Java에서 발생할 수 있는 모든 Exception과 Error 클래스는 이 클래스를 상속한다.
- 예외 객체가 발생한 원인과 상태 정보를 저장하고, 이를 처리할 수 있는 메서드를 제공한다.

### Throwable 클래스의 하위 클래스
- Error
- Exception

### Throwable 클래스의 메서드(Error와 Exception에서 모두 사용)
- String getMessage()
    - 예외의 상세 메시지를 반환합니다.
    - 예외가 생성될 때, 메시지를 전달받을 수 있으며, 예외의 원인이나 문제에 대한 설명을 제공할 수 있습니다.
- String toString()
    - 예외 클래스의 이름과 상세 메시지를 포함한 문자열을 반환합니다.
    - getClass().getName() + ": " + getMessage()를 반환합니다.
- void printStackTrace()
    - 예외의 스택 트레이스를 출력합니다.
    - 예외가 발생한 지점과 호출된 메서드들의 목록을 출력해 디버깅을 용이하게 합니다.
    - printStackTrace()는 예외 객체의 상태를 로그로 남기거나 디버깅할 때 유용합니다.
- StackTraceElement[] getStackTrace()
    - 예외 발생 시의 스택 트레이스를 배열 형태로 반환합니다.
    - 각 StackTraceElement 객체는 예외가 발생한 파일명, 메서드명, 줄 번호 등을 포함합니다.
- Throwable getCause()
    - 예외가 다른 예외를 발생시키는 경우, 발생한 원인 예외를 반환합니다.
    - 원인 예외는 다른 예외를 던졌을 때 initCause(Throwable cause) 메서드를 사용해 설정할 수 있습니다.
- void initCause(Throwable cause)
    - 예외의 원인(cause)을 설정합니다.
    - 예외 체이닝을 할 때 사용됩니다.
- boolean equals(Object obj)
    - Throwable 객체와 다른 객체가 동일한 예외인지를 비교합니다.
- void printStackTrace(PrintStream s)
    - 예외의 스택 트레이스를 PrintStream(예: 파일, 콘솔)으로 출력할 수 있도록 해주는 메서드입니다.
- void printStackTrace(PrintWriter s)
    - 예외의 스택 트레이스를 PrintWriter로 출력할 수 있도록 해주는 메서드입니다.

---

## Error
- 심각한 시스템 수준의 오류를 나타내는 클래스입니다
- 일반적으로 Error는 개발자가 처리할 수 없는 시스템적인 오류를 의미합니다.

### Error 클래스의 하위 클래스
1. OutOfMemoryError
    - JVM이 더 이상 메모리를 할당할 수 없을 때 발생하는 오류입니다.
    - 프로그램이 요구하는 메모리가 시스템에서 제공할 수 있는 메모리 용량을 초과했을 때 발생합니다.
2. StackOverflowError
    - 스택 메모리가 부족할 때 발생하는 오류입니다.
    - 일반적으로 재귀 호출이 끝없이 반복되어 스택 공간을 모두 소모하면 발생합니다.
3. VirtualMachineError
    - JVM 자체의 심각한 오류를 나타내는 클래스입니다.
    - JVM이 더 이상 정상적으로 실행을 유지할 수 없을 때 발생합니다.
4. InternalError
    - JVM 내부에서 발생한 오류를 나타내는 클래스입니다.
    - 주로 JVM의 내부 오류나 시스템 오류로 발생하며, 애플리케이션에서 직접 처리하기보다는 시스템 오류로 취급됩니다.
5. UnknownError
    - 원인을 알 수 없는 오류가 발생했을 때 사용되는 클래스입니다.
    - 이 오류는 JVM이 예상하지 못한 문제로 인해 발생할 때 사용되며, 시스템 상태가 매우 불안정한 경우에 발생할 수 있습니다.
6. OutOfMemoryError
    - 이 오류는 JVM에서 힙 메모리 부족으로 인해 발생합니다.
    - 일반적으로 JVM이 더 이상 객체를 할당할 수 없을 때 발생합니다.

---

## Exception
- 예외 처리의 기본 클래스입니다.
- 주로 프로그램의 정상 흐름을 방해하는 오류를 처리하는 데 사용됩니다.
- 체크 예외(checked exceptions)와 언체크 예외(unchecked exceptions)를 구분하는 중요한 역할을 합니다.

### Exception 클래스의 생성자
- Exception()
    - 기본 생성자로, 예외 메시지 없이 Exception 객체를 생성합니다.
- Exception(String message)
    - 예외 발생 이유를 설명하는 메시지를 전달하여 Exception 객체를 생성합니다.
- Exception(String message, Throwable cause)
    - 예외 메시지와 예외의 원인(cause)을 전달하여 Exception 객체를 생성합니다. 예외 체이닝을 할 수 있는 생성자입니다.
- Exception(Throwable cause)
    - 예외의 원인만을 전달하여 Exception 객체를 생성합니다. Throwable 객체를 원인으로 지정할 수 있습니다.

### Exception 클래스의 하위 클래스
- 체크 예외(checked exceptions)
- 언체크 예외(unchecked exceptions)

### 체크 예외(checked exceptions)
- 컴파일 타임에 반드시 처리해야 하는 예외다.
- 이를 처리하지 않으면 컴파일 오류가 발생한다.
- 이 예외들은 메서드 선언에서 반드시 throws 절로 선언해야 한다.
- 호출하는 측에서 try-catch 또는 throws를 통해 처리해야 합니다.

1. IOException
    - 입출력 관련 예외를 나타냅니다.
    - 파일을 읽거나 쓰는 도중 발생하는 오류나 네트워크 통신 오류 등과 관련이 있습니다.
    - 하위 클래스
        1. FileNotFoundException
            - 파일을 찾을 수 없을 때 발생
        2. EOFException
            - 파일 끝에 도달했을 때 발생
        3. InterruptedIOException
            - 입출력 작업이 인터럽트되었을 때 발생
        4. MalformedURLException
            - URL이 잘못된 형식으로 제공될 때 발생
2. SQLException
    - SQL 관련 예외를 나타냅니다.
    - 예: 데이터베이스에서 쿼리를 실행하거나 데이터베이스 연결에서 오류가 발생했을 때 사용됩니다.
3. ClassNotFoundException
    - 클래스가 로드되지 못했을 때 발생하는 예외입니다.
    - 예: Class.forName() 메서드로 클래스를 찾을 수 없을 때 발생합니다.
4. InterruptedException
    - 스레드가 대기 상태에서 인터럽트될 때 발생하는 예외입니다.
    - 예를 들어, Thread.sleep()이나 Object.wait() 등의 메서드를 호출하는 중에 인터럽트가 발생하면 이 예외가 발생합니다.
5. ParseException
    - 문자열 파싱에서 오류가 발생했을 때 발생하는 예외입니다.
    - 예: 날짜나 숫자 형식이 잘못되었을 때.
6. NoSuchMethodException
    - 요청한 메서드를 찾을 수 없을 때 발생하는 예외입니다.
    - 리플렉션을 사용할 때, 메서드 이름이나 파라미터가 잘못되었을 경우 발생합니다.
7. NoSuchFieldException
    - 요청한 필드를 찾을 수 없을 때 발생하는 예외입니다.
    - 리플렉션을 통해 클래스의 필드를 찾을 때 잘못된 필드명을 제공하면 발생합니다.
8. CloneNotSupportedException
    - Object.clone() 메서드가 호출될 때, 해당 객체가 Cloneable 인터페이스를 구현하지 않으면 발생하는 예외입니다.
9. FileNotFoundException
    - 파일을 찾을 수 없을 때 발생하는 예외입니다.
10. InstantiationException
    - 클래스를 인스턴스화할 수 없을 때 발생하는 예외입니다.
    - 일반적으로 추상 클래스나 인터페이스의 인스턴스를 생성하려고 시도할 때 발생합니다.
    - Class.newInstance() 메서드를 사용하여 클래스를 인스턴스화할 때, 해당 클래스가 인스턴스화할 수 없는 경우 발생합니다.
11. UnsupportedEncodingException
    - 지원되지 않는 문자 인코딩을 사용하려고 할 때 발생하는 예외입니다.
    - 문자열을 바이트 배열로 변환하거나, 바이트 배열을 문자열로 변환할 때, 지정된 문자 인코딩이 지원되지 않는 경우에 발생합니다.
    - String.getBytes(String charsetName) 메서드나
        new String(byte[] bytes, String charsetName) 생성자를 사용할 때 잘못된 문자 인코딩을 지정하면 이 예외가 발생합니다.

### 언체크 예외(unchecked exceptions)
- 런타임 예외이다.
- 일반적으로 프로그래밍 실수로 발생하는 예외이다.
- 컴파일 타임에 예외 처리를 강제하지 않는 예외이다.
- 이 예외들은 RuntimeException을 상속한다.

1. RuntimeException
    - 언체크 예외의 최상위 클래스입니다.
    - 프로그래밍 실수로 발생하는 예외들을 나타냅니다.
2. NullPointerException
    - null 객체를 참조하려 할 때 발생하는 예외이다.
3. ArrayIndexOutOfBoundsException
    - 배열의 잘못된 인덱스를 참조할 때 발생하는 예외입니다.
4. ArithmeticException
    - 수학적 연산에서 잘못된 연산이 수행될 때 발생하는 예외입니다. 예: 0으로 나누기.
5. IllegalArgumentException
    - 잘못된 인자를 메서드에 전달할 때 발생하는 예외입니다.
6. IllegalStateException
    - 객체의 상태가 메서드 호출에 적합하지 않을 때 발생합니다.
7. IndexOutOfBoundsException
    - 리스트나 배열 등에서 잘못된 인덱스를 참조할 때 발생합니다.
8. ClassCastException
    - 객체 타입 변환이 잘못되었을 때 발생합니다.
9. NegativeArraySizeException
    - 배열의 크기가 음수일 때 발생합니다.

---

## e
- e는 예외 객체를 나타내는 변수 이름입니다.
- 예외 처리 구문인 try-catch 문에서 catch 블록에서 예외 객체를 참조할 때 일반적으로 e라는 이름을 많이 사용합니다.
- 이 이름은 개발자들 간의 약속으로, 코드의 가독성을 높이고 일관성을 유지하는 데 도움을 줍니다.
- catch 블록에서 예외가 발생했을 때 그 예외의 상세 정보를 담고 있습니다.
- 예외 객체에는 예외 메시지, 스택 트레이스 정보, 원인 예외(cause) 등 다양한 정보가 포함되어 있다.

### e의 타입
- catch 블록에서 예외 객체 e는 항상 catch에서 지정한 예외 타입의 인스턴스입니다.
- 예를 들어, catch (ArithmeticException e)에서 e는 ArithmeticException 클래스의 객체입니다.
- Java는 예외 계층 구조를 사용하기 때문에, e는 그 예외 타입의 부모 클래스 타입의 객체일 수 있습니다.

### e 대신 다른 변수명 사용
- e는 예외 객체를 나타내는 변수로 자주 사용되지만, 반드시 e라는 이름을 사용해야 하는 것은 아닙니다.
- e는 일반적으로 사용되는 변수명일 뿐이며, 원하는 다른 이름을 사용할 수도 있습니다.
```
try {
throw new Exception("예외 발생");
} catch (Exception ex) {  // "e" 대신 "ex"를 사용
System.out.println("예외 메시지: " + ex.getMessage());
}
```

***

# Enum
- Java 열거형(enum) 클래스의 상위 클래스이다.
- Java에서 열거형(enumeration)을 정의할 때 사용되는 기본 클래스이다.
- 열거형은 고정된 상수 집합을 표현하는 데 사용되며, enum은 이 상수들을 객체로 다룰 수 있게 합니다.

## Enum 클래스의 메서드
- Enum 클래스는 열거형 상수에 대한 고급 기능을 제공하는 여러 메서드를 포함하고 있습니다.
- Enum 클래스는 모든 열거형이 공통적으로 상속받는 메서드를 제공합니다.

1. name()
    - 열거형 상수의 이름을 문자열로 반환합니다.
    - name() 메서드는 enum 상수의 이름을 대소문자 그대로 반환합니다.
2. ordinal()
    - 열거형 상수의 순서(인덱스)를 반환합니다. ordinal() 메서드는 열거형 상수가 정의된 순서를 0부터 시작하는 정수로 반환합니다.
3. valueOf(String name)
    - 이름에 해당하는 열거형 상수를 반환합니다.
    - 주어진 문자열과 일치하는 열거형 상수를 반환하며, 존재하지 않는 이름을 전달하면 IllegalArgumentException이 발생합니다.
4. getDeclaringClass()
    - 열거형 클래스 자체를 반환합니다. 즉, 열거형 상수가 속한 클래스 객체를 반환합니다.
5. compareTo(E o)
    - 열거형 상수의 순서를 비교하는 메서드입니다.
    - 이 메서드는 상수의 정의 순서에 따라 두 상수를 비교합니다.
    - ordinal()을 사용하여 순서를 비교하는 것과 동일합니다.
6. toString()
    - 열거형 상수의 문자열 표현을 반환합니다.
    - 기본적으로 name() 메서드와 동일하지만, 열거형 클래스에서 toString()을 오버라이드하여 다르게 구현할 수도 있습니다.

## enum 클래스 정의 방법
- Java에서 열거형은 enum 키워드를 사용하여 정의합니다.
- enum은 클래스와 비슷하지만, 상수 집합을 정의하는 데 특화된 클래스입니다.

1. 기본적인 enum 정의
    ```
    enum Day {
    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY
    }
    ```
   
2. enum에 필드, 생성자, 메서드 추가

    - enum 클래스는 각 상수에 여러 값을 추가할 수 있습니다.
    - 값을 추가하려면 필드, 생성자, 그리고 getter 메서드를 사용하여 값을 저장하고 조회할 수 있습니다.
    - 여러 값은 다양한 타입을 사용할 수 있으며, 복잡한 값이 필요하면 객체를 사용하여 enum 상수에 다양한 정보를 저장할 수 있습니다.

    ```
    public enum Day {
        MONDAY(1, new WorkHours(9, 17)),
        TUESDAY(2, new WorkHours(9, 17)),
        WEDNESDAY(3, new WorkHours(9, 17)),
        THURSDAY(4, new WorkHours(9, 17)),
        FRIDAY(5, new WorkHours(9, 16)),
        SATURDAY(6, new WorkHours(0, 0)),
        SUNDAY(7, new WorkHours(0, 0));
    
        private final int dayNumber;      // 요일 번호
        private final WorkHours workHours; // 근무 시간
    
        // 생성자
        Day(int dayNumber, WorkHours workHours) {
            this.dayNumber = dayNumber;
            this.workHours = workHours;
        }
    
        public int getDayNumber() {
            return dayNumber;
        }
    
        public WorkHours getWorkHours() {
            return workHours;
        }
    
        // WorkHours 클래스 (근무 시간 정보)
        static class WorkHours {
            private final int startHour;
            private final int endHour;
    
            public WorkHours(int startHour, int endHour) {
                this.startHour = startHour;
                this.endHour = endHour;
            }
    
            public int getStartHour() {
                return startHour;
            }
    
            public int getEndHour() {
                return endHour;
            }
    
            @Override
            public String toString() {
                return startHour + " to " + endHour;
            }
        }
    }
    
    public class EnumExample {
        public static void main(String[] args) {
            // 각 요일의 번호와 근무 시간 출력
            for (Day day : Day.values()) {
            System.out.println(day + " : " + day.getDayNumber() + ", Work Hours: " + day.getWorkHours());
            }
        }
    }
    ```
    - 이 예제에서는 각 요일에 대한 설명을 추가했습니다.
    - 각 열거형 상수는 description을 갖고 있으며, getDescription() 메서드를 통해 설명을 반환할 수 있습니다.

## enum의 활용
1. 상수 관리
    - enum을 사용하면 고정된 값들을 그룹화하여 관리할 수 있습니다. 예를 들어, 요일, 색상, 상태 등을 enum으로 정의하면 코드가 깔끔하고 직관적으로 작성됩니다.
2. 타입 안전성
    - enum은 타입 안전성을 제공합니다. 즉, 잘못된 값을 사용하려고 하면 컴파일러가 오류를 발생시켜 잘못된 사용을 방지합니다.
3. Switch 문과의 결합
    - enum은 switch문과 잘 결합됩니다. enum 상수들은 switch에서 비교할 수 있는 안전하고 명확한 값이 됩니다.
    ```
    public class EnumExample {
        enum Day { MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY }
    
        public static void main(String[] args) {
            Day day = Day.WEDNESDAY;
            switch (day) {
                case MONDAY:
                    System.out.println("Start of the week");
                    break;
                case WEDNESDAY:
                    System.out.println("Midweek");
                    break;
                case FRIDAY:
                    System.out.println("End of the work week");
                    break;
                default:
                    System.out.println("Weekend or other day");
            }
        }
    }
    ```