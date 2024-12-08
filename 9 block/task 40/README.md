# Практика #1
## Что произойдет при выполнении данного кода? Поясните.

```
public class App {
  final static int START_COUNTER;
  static {
    START_COUNTER = Integer.parseInt("Y-");
  }
  public static void main(String[] args) {
    System.out.println("Hello");
  }
}
```

При выполнении данного кода возникнет ошибка во время инициализации класса. final static int START_COUNTER; — переменная START_COUNTER объявлена как final, поэтому она должна быть инициализирована один раз.
Статический блок пытается присвоить переменной START_COUNTER значение, полученное при парсинге строки "Y-" в целое число, что вызывает исключение NumberFormatException.
Исключение происходит во время статической инициализации, еще до выполнения метода main. Это исключение не будет обработано, так как оно произошло при инициализации самого класса, и программа завершится аварийно.