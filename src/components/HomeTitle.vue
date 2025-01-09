<template>
    <div class="greeting">
      <p>Improve your music experience.</p>
      <p>Make new discoveries, learn the background of your favorite music and share your tastes.</p>
    </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@800&display=swap');

.greeting {
  position: relative;
  align-items: stretch;
  margin: auto;
  font-size: 270%;
  text-align: center;
  font-family: 'Montserrat', sans-serif;
  color: white;
  padding-top: 7px;
  margin-top: -20px;
  background-image: url("../../public/img/home_greeting_background.jpg");
  background-size: cover;
  background-position: center;
  padding: 20px; /* Add spacing inside the container */
  z-index: 1; /* Ensure content is above the overlay */
}

.greeting::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5); 
  z-index: -1; 
}

</style>

