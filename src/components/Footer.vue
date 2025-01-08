<template>
    <footer class="footer">
    <ul>
        <li><a href="#">FAQ</a></li>
        <li><a href="#">User Agreement</a></li>
        <li><a href="#">Rules</a></li>
    </ul>
    <ul>
        <li><a href="#">Copyright</a></li>
        <li><a href="#">Privacy Policy</a></li>
        <li><a href="#">Terms of Service</a></li>
    </ul>
</footer>
</template>

<style scoped>

.footer {
  background-color: #007c9ced;
  text-align: center;
  padding: 10px 0;
  width: 100%;
  margin-top: auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.footer ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}

.footer ul li {
  margin: 0 10px; 
}

.footer a {
  color: #e2fdff;
  transition: color 0.3s ease;
  text-decoration: none;
}

.footer a:hover {
  color: #aacacf;
  text-decoration: underline;
}


</style>