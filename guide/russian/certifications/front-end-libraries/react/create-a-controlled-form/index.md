---
title: Create a Controlled Form
localeTitle: Создание управляемой формы
---
## Создание управляемой формы

Создание управляемой формы - это тот же процесс, что и создание управляемого ввода, за исключением необходимости обрабатывать событие отправки.

Во-первых, создайте управляемый вход, который сохраняет свое значение в состоянии, так что есть один источник истины. (Это то, что вы делали в предыдущем вызове.) Создайте элемент ввода, установите его атрибут value в переменную ввода, находящуюся в состоянии. Помните, что состояние доступно через `this.state` . Затем установите атрибут `onChange` элемента ввода, чтобы вызвать функцию 'handleChange'.

### Решение

```react.js
<input value={this.state.input} onChange={this.handleChange}/> 
```

Затем создайте метод handleSubmit для вашего компонента. Во-первых, поскольку ваша форма отправляется, вам придется не обновлять страницу. Во-вторых, вызовите метод `setState()` , передавая в объект разные пары ключ-значение, которые вы хотите изменить. В этом случае вы хотите установить 'submit' в значение переменной 'input' и установить 'input' в пустую строку.

```react.js
handleSubmit(event) { 
  event.preventDefault(); 
  this.setState({ 
    input: '', 
    submit: this.state.input 
  }); 
 } 
```

Теперь, когда ваши данные обрабатываются в состоянии, мы можем использовать эти данные. Создайте элемент `h1` . Внутри вашего элемента `h1` переменную 'submit'. Помните, что «submit» находится в состоянии, поэтому вам нужно использовать `this.state` . Кроме того, для размещения переменной в JSX требуются фигурные скобки `{ }` поскольку это JavaScript.

```jsx
<h1>{this.state.submit}</h1> 

```