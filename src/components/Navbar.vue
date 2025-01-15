<template>
    <nav>
      <img src="/public/favicon.png" alt="Logo" width="50" height="52">
        <ul>
          <li>
            <div class="wrap">
              <div class="search">
                  <input type="text" class="searchTerm" placeholder="What are you looking for?">
                  <button type="submit" class="searchButton">
                    <i class="fa fa-search"></i>
                </button>
              </div>
            </div>
          </li>
          <li><a href="/">Home</a></li>
          <li><a href="/about">About</a></li>
          <li><a href="/contact">Contacts</a></li>
          <li><a href="/tutor">Tutorials</a></li>
          <li><a href="/market">Market</a></li>
          <li><a href="/login">Login</a></li>
        </ul>
        <!-- hamburger menu -->
        <div class="hamburger" @click="toggleNav">
            <span class="line"></span>
            <span class="line"></span>
            <span class="line"></span>
        </div>
    </nav>
    <!-- menubar for mobiles -->
    <div class="menubar" :class="{ active: isMenuActive }">
        <ul>
          <li><a href="/">Home</a></li>
          <li><a href="/about">About</a></li>
          <li><a href="/contact">Contacts</a></li>
          <li><a href="/tutor">Tutorials</a></li>
          <li><a href="/market">Market</a></li>
          <li><a href="/login">Login</a></li>
        </ul>
    </div>
</template>

<style scoped>

.search {
  width: 100%;
  position: relative;
  display: flex;
}

.searchTerm {
  width: 100%;
  border: 3px solid #00B4CC;
  border-right: none;
  padding: 5px;
  height: 20px;
  border-radius: 5px 0 0 5px;
  outline: none;
  color: #9DBFAF;
}

.searchTerm:focus{
  color: #00B4CC;
}

.searchButton {
  width: 40px;
  height: 36px;
  border: 1px solid #00B4CC;
  background: #00B4CC;
  text-align: center;
  color: #fff;
  border-radius: 0 5px 5px 0;
  cursor: pointer;
  font-size: 20px;
}

/*Resize the wrap to see the search bar change!*/
.wrap{
  width: 30%;
  position: absolute;
  top: 3.5%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.menubar ul {
    list-style-type: none;
    padding: 0;
    margin: 0;
    display: flex;
    flex-direction: column; /* stack items vertically */
    align-items: center; /* center items horizontally */
    justify-content: center; /* center items vertically */
}

.menubar li {
    margin: 10px;
}

nav {
    background-color: rgb(185, 225, 255);
    padding: 5px 2%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
    z-index: 1;
    height: 55px;
}

nav ul {
    list-style: none;
    display: flex;
}

nav ul li {
    margin-left: 0.5rem;
}

nav ul li a {
  text-decoration: none;
  background-color: rgb(185, 225, 255);
  color: #000000;
  font-family: Arial, Helvetica, sans-serif;
  font-weight: 400;
  padding: 4px 8px;
  border-radius: 5px;
}

nav ul li a:hover {
  background-color: #91e3f8ed;
}

.hamburger {
    display: none;
    cursor: pointer;
}

.hamburger .line {
    width: 25px;
    height: 2px;
    background-color: #ffffff;
    display: block;
    margin: 7px auto;
    transition: all 0.3s ease-in-out;
}

.menubar {
    position: absolute;
    top: 0;
    left: -60%;
    display: flex;
    justify-content: center;
    align-items: flex-start;
    width: 60%;
    height: 100vh;
    padding: 20% 0;
    background: rgba(255, 255, 255);
    transition: all 0.5s ease-in;
    z-index: 2;
}
.menubar.active {
    left: 0;
    box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
}

.menubar ul {
    padding: 0;
    list-style: none;
}
.menubar ul li {
    margin-bottom: 32px;
}

.menubar ul li a {
    text-decoration: none;
    color: #000;
    font-size: 95%;
    font-weight: 400;
    padding: 5px 10px;
    border-radius: 5px;
}

.icon {
    font-size: 1.2rem;
}

.menubar ul li a:hover {
    background-color: #ac60bf;
}

/* Media Query for Mobile */
@media screen and (max-width: 790px) {
    .hamburger {
        display: block;
    }
    nav ul {
        display: none;
    }
}
</style>

<script>

import { ref } from 'vue';

export default {
  setup() {
    // Dark mode state
    const isDarkMode = ref(localStorage.getItem('darkMode') === 'true');

    // Menu state
    const isMenuActive = ref(false);

    // Toggle dark mode function
    const toggleDarkMode = () => {
      isDarkMode.value = !isDarkMode.value;
      document.documentElement.classList.toggle('dark-mode', isDarkMode.value);
      localStorage.setItem('darkMode', isDarkMode.value);
    };

    // Toggle navigation menu function
    const toggleNav = () => {
      isMenuActive.value = !isMenuActive.value;
    };

    // Apply dark mode on mount if it's active
    if (isDarkMode.value) {
      document.documentElement.classList.add('dark-mode');
    }

    return {
      isDarkMode,
      toggleDarkMode,
      isMenuActive,
      toggleNav,
    };
  },
};

</script>