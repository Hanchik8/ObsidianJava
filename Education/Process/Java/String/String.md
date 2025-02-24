## Класс String

**String** – это базовый класс для работы с текстовыми данными в Java. Его ключевые особенности:

- **Неизменяемость (immutable):** После создания объект класса String нельзя изменить. Любая операция, которая кажется изменяющей строку (например, конкатенация, замена символов, извлечение подстроки), создаёт новый объект. Это позволяет:
    
    - Кэшировать вычисленный хэш-код (важно при использовании строк в качестве ключей в коллекциях, таких как `HashMap`);
    - Гарантировать потокобезопасность при одновременном использовании в разных потоках;
    - Использовать строковый пул (string pool), где литералы хранятся для экономии памяти. При использовании строковых литералов компилятор помещает их в пул, поэтому одинаковые литералы используют один и тот же объект.
- **Конкатенация:** Оператор «+» перегружен для строк, и даже при использовании его компилятор под капотом преобразует выражения в использование класса StringBuilder (или StringBuffer) для построения итоговой строки.
    

> Пример:
> 
> `String s = "Hello, " + "world!";`
> 
> Здесь компилятор преобразует операцию конкатенации в вызов методов append() у StringBuilder, а затем преобразует результат в строку.  
> 
> [javarush.com](https://javarush.com/en/groups/posts/en.2351.introduction-to-string-stringbuffer-and-stringbuilder-in-java)


## Методы в String

В классе `**String**` существует масса полезных методов, которые можно применять к строкам (перед именем метода будем указывать тип того значения, которое он возвращает):

1. `int length()` — возвращает длину строки (количество символов в ней);
2. `boolean isEmpty()` — проверяет, пустая ли строка;
3. `String replace(a, b)` — возвращает строку, где символ a (литерал или переменная типа char) заменён на символ b;
4. `String toLowerCase()` — возвращает строку, где все символы исходной строки преобразованы к строчным;
5. `String toUpperCase()` — возвращает строку, где все символы исходной строки преобразованы к прописным;
6. `boolean equals(s)` — возвращает истину, если строка к которой применён метод, совпадает со строкой s указанной в аргументе метода (с помощью оператора `==` строки сравнивать нельзя, как и любые другие объекты);
7. `int indexOf(ch)` — возвращает индекс символа ch в строке (индекс это порядковый номер символа, но нумероваться символы начинают с нуля). Если символ совсем не будет найден, то возвратит -1. Если символ встречается в строке несколько раз, то возвратит индекс его первого вхождения.
8. `int lastIndexOf(ch)` — аналогичен предыдущему методу, но возвращает индекс последнего вхождения, если символ встретился в строке несколько раз.
9. `int indexOf(ch,n)` — возвращает индекс символа ch в строке, но начинает проверку с индекса n (индекс это порядковый номер символа, но нумероваться символы начинают с нуля).
10. `char charAt(n)` — возвращает код символа, находящегося в строке под индексом n (индекс это порядковый номер символа, но нумероваться символы начинают с нуля).

Конкатенация — склеивание строк
