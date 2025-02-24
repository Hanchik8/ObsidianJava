**Iterator** — это интерфейс, который предоставляет методы для перебора элементов коллекции. 
Основные методы: 
**hasNext():** Возвращает true, если в коллекции есть следующий элемент. 
**next():** Возвращает следующий элемент коллекции. 
**remove():** Удаляет последний возвращенный элемент. дай пример

### Пример 1: Перебор элементов с `Iterator`
![](Pasted%20image%2020250202121557.png)
Вывод:
Apple
Banana
Cherry

### **Пример 2: Удаление элементов во время итерации**

Удалять элементы напрямую в `for-each` нельзя, но `Iterator` позволяет это делать безопасно:
![](Pasted%20image%2020250202121746.png)
**Важно:** Использовать `remove()` можно **только после вызова `next()`**, иначе будет `IllegalStateException`.

---

### **Пример 3: Использование `ListIterator` для изменения элементов**

`ListIterator` (расширение `Iterator`) позволяет изменять элементы списка:
![](Pasted%20image%2020250202122000.png)

---
### **Выводы:**
![](Pasted%20image%2020250202122203.png)

Если **только перебор** — `Iterator`.  
Если **нужна модификация** — `ListIterator`. 

Единственный корректный путь для модификации (удаления элементов) коллекции во время итерации - это использование [Iterator.remove()](http://docs.oracle.com/javase/7/docs/api/java/util/Iterator.html). 
Например:
![](Pasted%20image%2020250204105912.png)