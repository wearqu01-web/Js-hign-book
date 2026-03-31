ЗАДАНИЕ 1
<button onclick="changeSize()">Задать размер</button>

<script>
    function changeSize() {
        document.getElementById('myDiv').classList.add('big-size');
    }
</script>

<style>
    #myDiv.big-size {
        width: 400px !important;
        height: 300px !important;
    }
</style>

ЗАДАНИЕ 2 
<div id="myDiv" style="width: 200px; height: 150px; background: lightblue;">
</div>
<button id="btn">Показать размеры</button>

<script>
  const div = document.getElementById("myDiv");
  const btn = document.getElementById("btn");

  btn.addEventListener("click", () => {
    const width = div.offsetWidth;
    const height = div.offsetHeight;
    alert(`Ширина: ${width}, Высота: ${height}`);
  });
</script>

ЗАДАНИЕ 3
<div id="myDiv" style="font-size: 24px; color: darkblue;">
  Пример текста
</div>
<button id="btn">Показать размер шрифта</button>

<script>
  const div = document.getElementById("myDiv");
  const btn = document.getElementById("btn");

  btn.addEventListener("click", () => {
    const style = window.getComputedStyle(div);
    const fontSize = style.fontSize; // например "24px"
    const numericSize = parseFloat(fontSize); // 24
    alert(`Размер шрифта: ${numericSize}`);
  });
</script>

ЗАДАНИЕ 4 
Объясните, в чем ошибка в следующем коде:
Нужно правильно написать
let elem = document.querySelector('div');
let fontSize = parseFloat(window.getComputedStyle(elem).fontSize); // 16
elem.style.fontSize = (fontSize + 2) + "px"; // 18px

ЗАДАНИЕ 5
Объясните, в чем ошибка в следующем коде:
let elem = document.querySelector('div');
let currentSize = parseInt(window.getComputedStyle(elem).fontSize); // 16
elem.style.fontSize = (currentSize + 2) + 'px'; // 18px

ЗАДАНИЕ 6
Объясните, в чем ошибка в следующем коде:
let elem = document.querySelector('div');
let currentSize = parseFloat(window.getComputedStyle(elem).fontSize); // 40px
// если хотите работать в em, лучше сразу задать в px и потом перевести
elem.style.fontSize = (currentSize + 2) + 'px';

ЗАДАНИЕ 7
ДАН ДИВ:
<div id="elem" style="width: 300px; height: 200px; border: 1px solid red;"> 
  text
</div>
<button id="btn">Увеличить размеры</button>

<script>
  const elem = document.getElementById("elem");
  const btn = document.getElementById("btn");

  btn.addEventListener("click", () => {
    // получаем текущие размеры
    let width = parseInt(window.getComputedStyle(elem).width);
    let height = parseInt(window.getComputedStyle(elem).height);

    // увеличиваем на 50px
    elem.style.width = (width + 50) + "px";
    elem.style.height = (height + 50) + "px";
  });
</script>

ЗАДАНИЕ 8
Дан див:
<div id="elem" style="width: 300px; height: 200px; border: 1px solid red;"> 
  text
</div>
<button id="btn">Увеличить на 10%</button>

<script>
  const elem = document.getElementById("elem");
  const btn = document.getElementById("btn");

  btn.addEventListener("click", () => {
    // получаем текущие размеры
    let width = parseFloat(window.getComputedStyle(elem).width);
    let height = parseFloat(window.getComputedStyle(elem).height);

    // увеличиваем на 10%
    elem.style.width = (width * 1.1) + "px";
    elem.style.height = (height * 1.1) + "px";
  });
</script>

Задание 9
Дан див:

<div id="elem" style="width: 300px; height: 
	200px; border: 1px solid red;"> 
	text
</div>
Дана также кнопка. По клику на кнопку выведите толщину границы, ее тип и цвет.
<div id="elem" style="width: 300px; height: 200px; border: 1px solid red;"> 
  text
</div>

Код:
<button id="btn">Показать границу</button>

<script>
  const elem = document.getElementById("elem");
  const btn = document.getElementById("btn");

  btn.addEventListener("click", () => {
    const style = window.getComputedStyle(elem);

    const borderWidth = style.borderWidth;   // например "1px"
    const borderStyle = style.borderStyle;   // например "solid"
    const borderColor = style.borderColor;   // например "rgb(255, 0, 0)"

    alert(`Толщина: ${borderWidth}, Тип: ${borderStyle}, Цвет: ${borderColor}`);
  });
</script>

Задание 10
№1

Дан див и две кнопки. По клику на первую кнопку спрячьте див, а по клику на вторую - покажите.

<div id="elem" style="width: 300px; height: 200px; border: 1px solid red;"> 
  text
</div>

<button id="hideBtn">Спрятать</button>
<button id="showBtn">Показать</button>

<script>
  const elem = document.getElementById("elem");
  const hideBtn = document.getElementById("hideBtn");
  const showBtn = document.getElementById("showBtn");

  hideBtn.addEventListener("click", () => {
    elem.style.display = "none";
  });

  showBtn.addEventListener("click", () => {
    elem.style.display = "block";
  });
</script>

Задание 11
№2

Дан див и две кнопки. По клику на первую кнопку покрасьте цвет дива в красный цвет, а по клику на вторую - верните исходный цвет.

<div id="elem" style="width: 300px; height: 200px; border: 1px solid red;"> 
  text
</div>

<button id="redBtn">Покрасить в красный</button>
<button id="resetBtn">Вернуть исходный цвет</button>

<script>
  const elem = document.getElementById("elem");
  const redBtn = document.getElementById("redBtn");
  const resetBtn = document.getElementById("resetBtn");
  const originalColor = window.getComputedStyle(elem).backgroundColor;

  redBtn.addEventListener("click", () => {
    elem.style.backgroundColor = "red";
  });

  resetBtn.addEventListener("click", () => {
    elem.style.backgroundColor = originalColor;
  });
</script>

Задание 12
№1⊗jsSpStyMSS

Перепишите код через изученное свойство:

elem.style.width  = '100px';
elem.style.height = '100px';
elem.style.margin = '10px auto';
elem.style.color  = 'red';

код:
elem.setAttribute("style", "width:100px; height:100px; margin:10px auto; color:red;");

Задание 13
№1
Для элемента заданы следующие стили:

#elem {
	width: 200px;
	height: 200px;
}
По клику на кнопку выведите ширину и высоту элемента.

<div id="elem" style="width: 200px; height: 200px; border: 1px solid red;">
  text
</div>
<button id="btn">Показать размеры</button>

<script>
  const elem = document.getElementById("elem");
  const btn = document.getElementById("btn");

  btn.addEventListener("click", () => {
    const style = window.getComputedStyle(elem);
    const width = style.width;   // например "200px"
    const height = style.height; // например "200px"

    alert(`Ширина: ${width}, Высота: ${height}`);
  });
</script>


Задание 14
№2
Для элемента заданы следующие стили:

#elem {
	width: 200px;
	height: 200px;
}
По клику на кнопку увеличьте ширину и высоту элемента в два раза.
код:
<div id="elem" style="width: 200px; height: 200px; border: 1px solid red;">
  text
</div>
<button id="btn">Увеличить в 2 раза</button>

<script>
  const elem = document.getElementById("elem");
  const btn = document.getElementById("btn");

  btn.addEventListener("click", () => {
    // текущие размеры
    let width = parseFloat(window.getComputedStyle(elem).width);
    let height = parseFloat(window.getComputedStyle(elem).height);

    // увеличиваем в два раза
    elem.style.width = (width * 2) + "px";
    elem.style.height = (height * 2) + "px";
  });
</script>

Задание 15
№1
Для элемента заданы следующие стили:

#elem {
	font-size: 2em;
}
По клику на кнопку выведите размер шрифта элемента.

код:
<div id="elem" style="font-size: 2em; border: 1px solid red;">
  text
</div>
<button id="btn">Показать размер шрифта</button>

<script>
  const elem = document.getElementById("elem");
  const btn = document.getElementById("btn");

  btn.addEventListener("click", () => {
    const style = window.getComputedStyle(elem);
    const fontSize = style.fontSize; // например "32px" в зависимости от базового размера
    alert(`Размер шрифта: ${fontSize}`);
  });
</script>

Задание 16
Даны абзацы с числами.

<p>1</p>
<p>2</p>
<p>3</p>
<p>4</p>

<button id="btn">Покрасить</button>

<script>
  const btn = document.getElementById("btn");
  const paragraphs = document.querySelectorAll("p");

  btn.addEventListener("click", () => {
    paragraphs.forEach(p => {
      const num = parseInt(p.textContent); // получаем число из текста
      if (num % 2 === 0) {
        p.style.color = "red";   // чётные — красные
      } else {
        p.style.color = "green"; // нечётные — зелёные
      }
    });
  });
</script>

Задание 17 
Даны абзацы.
<style>
  p.active {
    color: red;
  }
  p {
    color: black;
    cursor: pointer;
  }
</style>

<p>Абзац 1</p>
<p>Абзац 2</p>
<p>Абзац 3</p>

<script>
  const paragraphs = document.querySelectorAll("p");

  paragraphs.forEach(p => {
    p.addEventListener("click", () => {
      p.classList.toggle("active");
    });
  });
</script>

Задание 18
Дан инпут. По потери фокуса проверьте, что в него введено не более 9-ти символов. Если это так, покрасьте границу инпута в зеленый цвет, а если не так - в красный.

<input id="myInput" type="text" placeholder="Введите текст">

<script>
  const input = document.getElementById("myInput");

  input.addEventListener("blur", () => {
    if (input.value.length <= 9) {
      input.style.borderColor = "green"; // не более 9 символов
    } else {
      input.style.borderColor = "red";   // больше 9 символов
    }
  });
</script>

Задание 19
Дан инпут. По потери фокуса проверьте введенное в него число. Если это число до десяти, то покрасьте инпут в зеленый цвет, если от десяти до двадцати - в желтый, а если более двадцати - в красный.

<input id="myInput" type="number" placeholder="Введите число">

<script>
  const input = document.getElementById("myInput");

  input.addEventListener("blur", () => {
    const value = parseFloat(input.value);

    if (value < 10) {
      input.style.borderColor = "green";   // до 10
    } else if (value >= 10 && value <= 20) {
      input.style.borderColor = "yellow";  // от 10 до 20
    } else if (value > 20) {
      input.style.borderColor = "red";     // более 20
    } else {
      input.style.borderColor = "";        // если не число, сбросим стиль
    }
  });
</script>

Задание 20
Сделайте себе аналогичный тестовый элемент. Проверяйте на нем свойства, которые будут изучаться в следующих уроках.

<div id="elem">
  some long text some long text some long text some long text some long text
  some long text some long text some long text some long text some long text
</div>

<style>
  #elem {
    width: 300px;
    height: 150px;
    margin: 50px auto;
    padding: 25px;
    background: #CFF5BF;
    border: 25px solid #F0D7A1;
    overflow: auto;
    text-align: justify;
  }
</style>

<script>
  const elem = document.querySelector('#elem');

  // Пример проверки разных метрик:
  console.log("offsetWidth:", elem.offsetWidth);       // ширина с padding + border
  console.log("offsetHeight:", elem.offsetHeight);     // высота с padding + border
  console.log("clientWidth:", elem.clientWidth);       // ширина с padding, но без border и полосы прокрутки
  console.log("clientHeight:", elem.clientHeight);     // высота с padding, но без border и полосы прокрутки
  console.log("scrollWidth:", elem.scrollWidth);       // полная ширина содержимого
  console.log("scrollHeight:", elem.scrollHeight);     // полная высота содержимого
  console.log("getBoundingClientRect:", elem.getBoundingClientRect()); // объект с координатами и размерами
</script>

Задание 21
Дан элемент и кнопка. По нажатию на кнопку выведите в консоль клиентскую ширину и высоту элемента.

<div id="elem" style="width: 300px; height: 150px; padding: 25px; border: 10px solid red; overflow: auto;">
  some long text some long text some long text some long text some long text
</div>

<button id="btn">Показать размеры</button>

<script>
  const elem = document.getElementById("elem");
  const btn = document.getElementById("btn");

  btn.addEventListener("click", () => {
    console.log("clientWidth:", elem.clientWidth);
    console.log("clientHeight:", elem.clientHeight);
  });
</script>

Задание 22 
Дан элемент и кнопка. По нажатию на кнопку выведите в консоль полную ширину и высоту элемента.

<div id="elem" style="width: 300px; height: 150px; padding: 25px; border: 10px solid red; overflow: auto;">
  some long text some long text some long text some long text some long text
</div>

<button id="btn">Показать полные размеры</button>

<script>
  const elem = document.getElementById("elem");
  const btn = document.getElementById("btn");

  btn.addEventListener("click", () => {
    console.log("offsetWidth:", elem.offsetWidth);
    console.log("offsetHeight:", elem.offsetHeight);
  });
</script>

Задание 23ьдбжощ
Если отнять от полной ширины клиентскую ширину, то получится некоторое число. Какие размеры оно содержит в себе?

Если отнять от полной ширины (offsetWidth) клиентскую ширину (clientWidth), то получится значение, которое включает в себя:

толщину левой границы (border-left)

толщину правой границы (border-right)

ширину вертикальной полосы прокрутки, если она присутствует

То есть разница показывает, сколько места занимают рамки и возможная полоса прокрутки, так как clientWidth учитывает только содержимое и внутренние отступы (padding), но не включает границы и скроллбар.

Задание 24
Дан элемент и кнопка. По нажатию на кнопку выведите в консоль ширину и высоту элемента с прокруткой.

<div id="elem" style="width: 300px; height: 150px; padding: 25px; border: 10px solid red; overflow: auto;">
  some long text some long text some long text some long text some long text
  some long text some long text some long text some long text some long text
</div>

<button id="btn">Показать размеры с прокруткой</button>

<script>
  const elem = document.getElementById("elem");
  const btn = document.getElementById("btn");

  btn.addEventListener("click", () => {
    console.log("scrollWidth:", elem.scrollWidth);
    console.log("scrollHeight:", elem.scrollHeight);
  });
</script>

Задание 25
Если отнять от высоты с прокруткой полную высоту, то получится некоторое число. Какие размеры оно содержит в себе?

Если отнять от высоты с прокруткой (scrollHeight) полную высоту (offsetHeight), то разница будет содержать:

высоту скрытой части содержимого, которая выходит за пределы видимой области и доступна только через прокрутку;

толщину горизонтальных границ (border-top и border-bottom), так как offsetHeight включает границы, а scrollHeight — нет.

Задание 26
Дан элемент и кнопка. По нажатию на кнопку узнайте на сколько прокручен элемент по вертикали.

<div id="elem" style="width: 300px; height: 150px; padding: 25px; border: 10px solid red; overflow: auto;">
  some long text some long text some long text some long text some long text
  some long text some long text some long text some long text some long text
  some long text some long text some long text some long text some long text
</div>

<button id="btn">Узнать прокрутку</button>

<script>
  const elem = document.getElementById("elem");
  const btn = document.getElementById("btn");

  btn.addEventListener("click", () => {
    console.log("scrollTop:", elem.scrollTop);
  });
</script>

Задание 27
Дан элемент и кнопка. По нажатию на кнопку проверьте, прокручен ли элемент по вертикали.

<div id="elem" style="width: 300px; height: 150px; padding: 25px; border: 10px solid red; overflow: auto;">
  some long text some long text some long text some long text some long text
  some long text some long text some long text some long text some long text
  some long text some long text some long text some long text some long text
</div>

<button id="btn">Проверить прокрутку</button>

<script>
  const elem = document.getElementById("elem");
  const btn = document.getElementById("btn");

  btn.addEventListener("click", () => {
    if (elem.scrollTop > 0) {
      console.log("Элемент прокручен по вертикали");
    } else {
      console
      
 Задание 28
   Прокрутите элемент до конца. Нажмите на кнопку, чтобы вывелась величина полной прокрутки.
      <div id="elem" style="width: 300px; height: 150px; padding: 25px; border: 10px solid red; overflow: auto;">
  some long text some long text some long text some long text some long text
  some long text some long text some long text some long text some long text
  some long text some long text some long text some long text some long text
</div>

<button id="btn">Показать полную прокрутку</button>

<script>
  const elem = document.getElementById("elem");
  const btn = document.getElementById("btn");

  btn.addEventListener("click", () => {
    // величина полной прокрутки
    const fullScroll = elem.scrollHeight - elem.clientHeight;
    console.log("Полная прокрутка:", fullScroll);
  });
</script>

Задание 29
Получите scrollHeight элемента и отнимите от него величину полной прокрутки (из предыдущей задачи). Какое значение получится? Какие размеры оно содержит в себе?

scrollHeight это вся высота содержимого.
scrollHeight (scrollHeight - clientHeight) = clientHeight.

То есть если отнять полную прокрутку от scrollHeight, получится клиентская высота элемента. Она включает в себя содержимое + padding, но не учитывает границы и полосы прокрутки.

Задание 30 
Сложите offsetHeight и величину полной прокрутки. Отнимите эту сумму от значения scrollHeight. Какое число получится?

offsetHeight  полная прокрутка  scrollHeight = clientHeight  offsetHeight.
А это значит, что получится отрицательное число, равное толщине границ и полосы прокрутки ведь offsetHeight учитывает их, а clientHeight нет.
