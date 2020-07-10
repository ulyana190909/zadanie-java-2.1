# Отчёт о тестировании приложения "Мобильный банк, раздел "пополнение счета""

Дата провередения тестирования: 10.07.2020.

На тестирование был потрачен 1 час.

### Проведено санитарное тестирование функции "пополнение счета" в приложении "Мобильный банк". Результат тестирования должен был показать насколько корректно отражается остаток счета, после его пополнения. 
### Результат тестирования показал, что расчет остатка денежных средств после перевода выполнен некорректно. 

**В процессе тестирования использовались данные одного из счетов VIP-клиента банка:** 
* счет с остатком на счету 2 000 000 000 
* данные о пополнении счета на 500 000 000
```
public class Main {
    public static void main(String[] args) {
        int balance = 2_000_000_000;
        int moneytransfer = 500_000_000;
        int total = balance + moneytransfer;
        System.out.println(total);
    }
}
```

**Результат тестирования кода:**
```
"C:\Program Files\Java\jdk-11.0.7\bin\java.exe" -javaagent:C:\Users\79269\AppData\Local\JetBrains\Toolbox\apps\IDEA-C\ch-0\201.7846.76\lib\idea_rt.jar=53086:C:\Users\79269\AppData\Local\JetBrains\Toolbox\apps\IDEA-C\ch-0\201.7846.76\bin -Dfile.encoding=UTF-8 -classpath C:\Users\79269\IdeaProjects\untitled\out\production\untitled Main
-1794967296

Process finished with exit code 0
``` 

### По результату заведен BAG Report -  https://github.com/ulyana190909/zadanie-java-2.1/issues/1
### Рекомендация для программистов: иcпользовать тип данных - long

**Тестирование производилось в следующем окружении:**
* HP Pavilion Gaming, Windows 10
* Java - openjdk version "11.0.7" 2020-04-14
* javac 11.0.7
* IntelliJ IDEA
