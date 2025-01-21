<template>
    <nav>
      <!-- <img src="/public/favicon.png" alt="Logo" width="50" height="52"> -->
       <p>Know Your Music</p>
        <ul>
          <li>
            <div class="wrap">
              <div class="search">
                <input type="text" class="searchTerm" placeholder="Search...">
                <button type="submit" class="searchButton">
                  <i class="fa fa-search"></i>
                </button>
              </div>
            </div>
          </li>
          <li><a href="/">Home</a></li>
          <li><a href="/explore">Explore</a></li>
          <li><a href="/about">About</a></li>
          <li><a href="/login">Login</a></li>
        </ul>
      <!-- search button for mobile -->
      <button class="mobile-search-button" @click="toggleMobileSearch" v-show="isMobile">
        <i class="fa fa-search"></i>
      </button>
      <!-- hamburger menu -->
      <div class="hamburger" @click="toggleNav">
          <span class="line"></span>
          <span class="line"></span>
          <span class="line"></span>
      </div>
    </nav>
    <!-- menubar for mobiles -->
    <div 
      class="overlay" 
      :class="{ active: isMenuActive }" 
      @click="toggleNav"
    ></div>
    <div class="menubar" :class="{ active: isMenuActive }">
      <ul>
        <li><a href="/">Home</a></li>
        <li><a href="/explore">Explore</a></li>
        <li><a href="/about">About</a></li>
        <li><a href="/login">Login</a></li>
      </ul>
    </div>
    <!-- search bar for mobile -->
  <div v-show="isMobileSearchActive" class="mobile-search-container">
    <div class="search">
      <input type="text" class="searchTerm" placeholder="Search..." />
      <button type="submit" class="searchButton">
        <i class="fa fa-search"></i>
      </button>
    </div>
  </div>
</template>

<style scoped>

.search {
  margin: 0 auto;
  width: 70%;
  position: relative;
  display: flex;
}

.searchTerm {
  width: 100%;
  border: 3px solid #54b3ebed;
  border-right: none;
  padding: 5px;
  height: 20px;
  border-radius: 7px 0 0 7px;
  outline: none;
  color: #000000;
}

.searchButton {
  position: relative; /* Ensure a positioned ancestor for the ::after pseudo-element */
  width: 40px;
  height: 36px;
  border: 1px solid #54b3ebed;
  background: #54b3ebed;
  text-align: center;
  color: #fff;
  border-radius: 0 7px 7px 0;
  cursor: pointer;
  font-size: 20px;
  overflow: hidden; /* Prevent visual overflow */
}

/* Transition the icon */
.searchButton i {
  transition: transform 0.3s ease, opacity 0.3s ease;
}

/* change to music icon on hover */
.searchButton:hover i {
  opacity: 0; /* fade out the search icon */
  transform: scale(0.5); /* shrink the search icon */
}

/* add the music icon after hover */
.searchButton:hover::after {
  content: "\f001"; /* Unicode for FontAwesome fa-music */
  font-family: "FontAwesome";
  font-size: 20px;
  color: #fff;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%) scale(1); /* Center the icon and scale it up */
  opacity: 1;
  transition: opacity 0.3s ease, transform 0.3s ease; /* Smooth appearance */
}

/* Initially, the music icon is hidden */
.searchButton::after {
  content: "";
  opacity: 0;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%) scale(0.5); /* Start small */
}

.wrap{
  width: 30%;
  position: absolute;
  top: 3.5%;
  left: 50%;
  transform: translate(-50%, -50%);
}

/* Mobile search container */
.mobile-search-container {
  background-color: rgb(185, 225, 255);
  padding: 10px;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  box-shadow: rgba(0, 0, 0, 0.2) 0px 4px 8px;
}

/* Mobile search button */
.mobile-search-button {
  background: none;
  border: none;
  font-size: 23px;
  cursor: pointer;
  color: #000;
  margin-left: 10px;
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

/* Overlay to cover the screen when the menu is active */
.overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5); /* Semi-transparent background */
  z-index: 1; /* Same as the menubar z-index or slightly lower */
  opacity: 0;
  visibility: hidden;
  transition: opacity 0.3s ease, visibility 0.3s ease;
}

.overlay.active {
  opacity: 1;
  visibility: visible;
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
    width: 40%;
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
@media screen and (max-width: 1370px){
  .search {
    width: 90%;
  }
}

@media screen and (max-width: 790px) {
  .hamburger {
    display: block;
  }

  nav ul {
    display: none; /* Completely remove the nav elements from the layout */
  }

  .mobile-search-button {
    position: absolute;
    right: 55px; /* move it closer to the hamburger menu */
    width: auto;
  }
}

@media screen and (max-width: 600px){
  .menubar.active {
    width: 60%;
  }
}

@media screen and (max-width: 430px){
  .menubar.active {
    width: 85%;
  }
}

</style>

<script>
import { ref, onMounted } from "vue";

export default {
  setup() {
    // Dark mode state
    const isDarkMode = ref(localStorage.getItem("darkMode") === "true");

    // Menu state
    const isMenuActive = ref(false);

    // Mobile state
    const isMobile = ref(false);
    const isMobileSearchActive = ref(false);

    // Toggle dark mode function
    const toggleDarkMode = () => {
      isDarkMode.value = !isDarkMode.value;
      document.documentElement.classList.toggle("dark-mode", isDarkMode.value);
      localStorage.setItem("darkMode", isDarkMode.value);
    };

    // Toggle navigation menu function
    const toggleNav = () => {
      isMenuActive.value = !isMenuActive.value;
    };

    // Toggle mobile search bar visibility
    const toggleMobileSearch = () => {
      isMobileSearchActive.value = !isMobileSearchActive.value;
    };

    // Handle screen size changes to detect mobile view
    const handleResize = () => {
      isMobile.value = window.innerWidth <= 790;
    };

    // Apply dark mode on mount if it's active
    if (isDarkMode.value) {
      document.documentElement.classList.add("dark-mode");
    }

    // Add resize event listener on mount
    onMounted(() => {
      window.addEventListener("resize", handleResize);
      handleResize(); // Check screen size on initial load
    });

    return {
      isDarkMode,
      toggleDarkMode,
      isMenuActive,
      toggleNav,
      isMobile,
      isMobileSearchActive,
      toggleMobileSearch,
    };
  },
};
</script>