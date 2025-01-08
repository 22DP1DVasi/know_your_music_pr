<template>

<div class="recommendations">
        <p>Last recommendations:</p>
    </div>

    <div class="flex-container">
        <div class="column">
            <img src="../../img/linkinpark.jpg" alt="Linkin Park" width="200" height="200">
            <h1>Linkin Park</h1>
            <p>One of the biggest rock and metal bands in the world.</p>
            <button class="button">Listen</button>
        </div>

        <div class="column">
            <img src="../../img/celldweller.jpg" alt="Celldweller" width="200" height="200">
            <h1>Celldweller</h1>
            <p>Main electro-industrial-rock musician of 2000s.</p>
            <button class="button">Listen</button>
        </div>

        <div class="column">
            <img src="../../img/tallah.jpeg" alt="Tallah" width="200" height="200">
            <h1>Tallah</h1>
            <p>Representative of modern nu-metal.</p>
            <button class="button">Listen</button>
        </div>
    </div>

    <div class="flex-container">
        <div class="column">
            <img src="../../img/linkinpark.jpg" alt="Linkin Park" width="200" height="200">
            <h1>Linkin Park</h1>
            <p>One of the biggest rock and metal bands in the world.</p>
            <button class="button">Listen</button>
        </div>

        <div class="column">
            <img src="../../img/celldweller.jpg" alt="Celldweller" width="200" height="200">
            <h1>Celldweller</h1>
            <p>Main electro-industrial-rock musician of 2000s.</p>
            <button class="button">Listen</button>
        </div>

        <div class="column">
            <img src="../../img/tallah.jpeg" alt="Tallah" width="200" height="200">
            <h1>Tallah</h1>
            <p>Representative of modern nu-metal.</p>
            <button class="button">Listen</button>
        </div>
    </div>

</template>

<style scoped>

.flex-container {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: stretch;
  padding: 0 4px;
  flex-wrap: wrap;
  column-gap: 10px;
  align-items: stretch;
}

.column {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  margin: 20px auto;
  flex: 1 1 25%;
  max-width: 500px;
  padding: 0 4px;
  gap: 20px;
  border: 5px solid #007c9ced;
  padding-top: 5px;
  align-items: center;
  min-height: 300px;
}

.column img {
  margin-top: 8px;
  vertical-align: middle;
  margin: auto;
}

.column > h1 {
  display: -webkit-box;
  -webkit-box-orient: vertical; 
  -webkit-line-clamp: 2;
  overflow: hidden;
  text-align: center;
  justify-content: center;
  font-size: clamp(30px, 4vw, 45px);
  line-height: 1.2em;
  margin-bottom: 7px;
}

.column > p {
  height: 4.5em;  /* three rows for text */
  overflow: hidden;
  display: -webkit-box; /* using older browser WebKit versions  */
  -webkit-line-clamp: 3; /* Limit text to three lines */
  -webkit-box-orient: vertical;   /* Set vertical orientation */
  font-size: clamp(23px, 2vw, 27px); /* Responsive text size */
  text-align: center;
  justify-content: center;
  margin-bottom: auto;
}

.button {
  width: 150px;
  height: 30px;
  background-color: #52ffffed;
  color: black;
  border: 2px solid #2b6fec;
  margin-top: auto; /* places the button down */
  margin-bottom: 20px; /* adds bottom margin */
  font-size: 20px;
}

.button:hover {
  box-shadow: 6px 6px 6px rgba(0, 0, 0, 0.6);
  animation: hoverUp 0.5s forwards; /*hoverUp - keyframes animation*/
}

.column:hover{
  box-shadow: 6px 6px 6px rgba(0, 0, 0, 0.6);
  animation: hoverUp 0.5s forwards;
}

.recommendations {
  padding-top: 2%;
  padding-left: 1.5%;
  font-size: 190%;
  margin-left: 2%;
  margin-bottom: 1%;
}

@keyframes hoverUp {
  0% {transform: translateY(0) translateX(0) ;}   /*animation starts*/
  100% {transform: translateY(-10px) translateX(-1px) scale(1.02);} /*animation ends*/
}

/* Responsive layout - makes a two column-layout instead of four columns */
@media (max-width: 800px) {
.column {
  flex: 1 1 calc(50% - 5px);
  max-width: 100%;
}
.flex-container{
  flex: 1 1 calc(50% - 5px);
  max-width: 100%;
}

.column > h1 {
  font-size: 50px;
  font-size: 5vw;
}
}

/* Responsive layout - makes the two columns stack on top of each other instead of next to each other */
@media (max-width: 600px) {
.column {
  flex: 1 1 calc(100% - 5px);
  max-width: 100%;
}
.flex-container{
  flex: 1 1 calc(100% - 5px);
  max-width: 100%;
}

.column > h1 {
  font-size: 50px;
  font-size: 5vw;
}

.footer ul {
  flex-direction: column; /* Перестройка в колонку на маленьких экранах */
  align-items: center; /* Центрирует элементы списка */
}

.footer ul li {
  margin: 5px 0; /* Уменьшаем отступы для компактности */
}
}

</style>

