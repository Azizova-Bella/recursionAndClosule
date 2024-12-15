# Рекурсия и Замыкания в JavaScript
![Recursion Diagram](https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.linkedin.com%2Fpulse%2Frecursion-explained-understand-you-must-first-ignacio-chitnisky&psig=AOvVaw3v6MOG298zsY7u24etjo7_&ust=1734319830435000&source=images&cd=vfe&opi=89978449&ved=0CBQQjRxqFwoTCICYhYfsqIoDFQAAAAAdAAAAABAE)


## Рекурсия

**Рекурсия** — это процесс, при котором функция вызывает саму себя. Рекурсия полезна для решения задач, которые можно разделить на подзадачи одного типа. Важно, чтобы рекурсивная функция имела условие завершения, иначе это приведет к переполнению стека вызовов.

### Пример: Факториал
```javascript

function sumOfFactorial(num){
    if (num == 0) return 1;
return num * sumOfFactorial(num - 1)

}
console.log(sumOfFactorial(5)); // Результат: 120
```

### Пример: Числа Фибоначчи
```javascript
function fibonacci(n) {
    if (n === 0) {
        return 0;
    } else if (n === 1) {
        return 1;
    } else {
        return fibonacci(n - 1) + fibonacci(n - 2);
    }
}

console.log(fibonacci(6)); // Результат: 8
```

### Полезные советы для использования рекурсии
- Определите базовый случай для завершения рекурсии.
- Убедитесь, что каждый рекурсивный вызов приближает функцию к базовому случаю.
- Если рекурсия слишком глубокая или неэффективная, используйте мемоизацию или итеративные подходы.

## Замыкания

**Замыкание** — это функция, которая запоминает своё лексическое окружение даже после того, как была вызвана за пределами своей области видимости. Замыкания полезны для создания функций с приватными данными и для реализации функционального программирования.

### Пример: Счётчик
```javascript

function createCounter(){
    let cnt = 0;
    return () => {
        return cnt ++
    }
}
 let adder = createCounter ()
 console.log(adder());
 console.log(adder());
 console.log(adder());
 console.log(adder());
 console.log(adder());
 console.log(adder());
 console.log(adder());
 console.log(adder());
 console.log(adder());
 console.log(adder());
 console.log(adder());  // Результат: 10
```

### Пример: Умножение с замыканием
```javascript
function multiplwOfNum (num1){
    let cnt = 0;
     return (num2) =>{
         cnt ++
         return num1 * num2
     }
 }
 let Multiple = multiplwOfNum (5)
 console.log(Multiple(3));   // Результат: 15
```



### Полезные советы для использования замыканий
- Избегайте чрезмерного использования замыканий, чтобы предотвратить утечки памяти.
- Используйте замыкания для инкапсуляции данных и логики.
- Помните, что замыкания могут вести себя неожиданно в циклах. Используйте дополнительные функции для предотвращения ошибок.

## Заключение
Рекурсия и замыкания — это мощные инструменты в программировании на JavaScript. Рекурсия позволяет элегантно решать сложные задачи, а замыкания помогают создавать гибкие и переиспользуемые функции. Дополнительное понимание и практическое использование этих концепций значительно улучшат ваш код и навыки программирования.
