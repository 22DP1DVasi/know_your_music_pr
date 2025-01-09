<template>
    <nav class="navbar navbar-inverse">
        <div class="container-fluid">
            <div class="navbar-header">
                <button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#myNavbar">
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                </button>
                <img src="/public/favicon.png" alt="Logo" width="50" height="52">
            </div>
            <div class="collapse navbar-collapse" id="myNavbar">
                <ul class="nav navbar-nav">
                    <li class="navbar-button"><a href="#" style="color:black;">Home</a></li>
                    <!-- <li>
                        <a href="#" class="dropdown-toggle navbar-dropdown-button" data-toggle="dropdown" style="color: white;">Music <span class="caret"></span></a>
                        <ul class="dropdown-menu navbar-custom-dropdown">
                            <li><a href="../html/pages/music_explore.html">Explore</a></li>
                            <li><a href="#">Live</a></li>
                        </ul>
                    </li> -->
                    <li class="navbar-button"><a href="#" style="color:black;">Explore</a></li>
                    <li class="navbar-button"><a href="#" style="color:black;">Lyrics</a></li>
                </ul>
                <form class="navbar-form navbar-left" action="/action_page.php">
                    <div class="form-group">
                        <input type="text" class="form-control" placeholder="Search" name="search">
                    </div>
                    <button type="submit" class="btn btn-default">Submit</button>
                </form>
                <ul class="nav navbar-nav navbar-right">
                    <li><a href="#" style="color:black"><span class="glyphicon glyphicon-user"></span> Sign Up</a></li>
                    <li><a href="#" style="color:black"><span class="glyphicon glyphicon-log-in"></span> Login</a></li>
                    <li>
                        <button id="darkModeToggle" class="btn btn-default navbar-btn" @click="toggleDarkMode">
                            <img src="/public/img/darkmodefavicon.png" alt="Dark Mode" width="22" height="22">
                        </button>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<style scoped>

.container-fluid {
  background-color: rgb(185, 225, 255);
}

/*change Bootstrap dropdown*/
.navbar-dropdown-button {
  padding: 15px 20px;
  border-radius: 5px;
  font-size: 16px;
  font-size: 100%;
}

.navbar-button {
  border-radius: 5px;
}

.navbar-button:hover {
  background-color: rgb(185, 225, 255) !important;
}

.navbar-dropdown-button:hover {
  background-color: #2598b4ed !important;
}

.navbar-custom-dropdown {
  background-color: #ffffffed !important;
  border: 2px solid #2598b4ed !important;
  border-radius: 5px;
  min-width: 200px;
  padding: 10px 0;
}

.navbar-custom-dropdown li a {
  color: #000000;
  padding: 10px 20px;
  text-decoration: none;
}

.navbar-custom-dropdown li a:hover {
  background-color: #e9e9e9 !important;
}

.dropdown-toggle {
  background-color: #007c9ced !important;
}
</style>

<script>

export default {
  data() {
    return {
      isDarkMode: localStorage.getItem('darkMode') === 'true',
    };
  },
  mounted() {
    if (this.isDarkMode) {
      document.documentElement.classList.add('dark-mode');
    }
  },
  methods: {
    toggleDarkMode() {
      this.isDarkMode = !this.isDarkMode;
      document.documentElement.classList.toggle('dark-mode', this.isDarkMode);
      localStorage.setItem('darkMode', this.isDarkMode);
    },
  },
};

</script>