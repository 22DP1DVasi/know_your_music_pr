<template>
    <div class="greeting">
      <p>Improve your music experience.</p>
      <p>Make new discoveries, learn the background of your favorite music and share your tastes.</p>
    </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@800&display=swap');

.greeting {
  display: flex;
  flex-direction: column; /* stack items vertically */
  justify-content: center; /* center items vertically */
  align-items: left; /* center items horizontally */
  width: 60%;
  margin: auto; /* center the container horizontally */
  font-size: 4rem;
  text-align: justify; /* Center-align the text */
  font-family: 'Montserrat', sans-serif;
  color: black;
  padding-top: 10%;
}

@media (max-width: 1363px) {
  .greeting {
    width: 90%;
  }
}

@media (max-width: 768px) {
  .greeting {
    font-size: 2rem; /* Smaller font for mobile */
  }
}

@media (max-width: 480px) {
  .greeting {
    font-size: 2.5rem; /* Smallest font for very small screens */
    width: 90%;
  }
}

</style>

