<template>
  <footer class="footer">
    <div class="footer-sections">
      <ul class="footer-links">
        <li><a href="#">FAQ</a></li>
        <li><a href="#">User Agreement</a></li>
        <li><a href="#">Rules</a></li>
      </ul>
      <ul class="footer-links">
        <li><a href="#">Copyright</a></li>
        <li><a href="#">Privacy Policy</a></li>
        <li><a href="#">Terms of Service</a></li>
      </ul>
    </div>
    <div class="footer-branding">
      <span>Made by Danon © 2025 Know Your Music. All rights reserved.</span>
    </div>
  </footer>
</template>

<style scoped>
/* General Footer Styles */
.footer {
  font-family: Arial, Helvetica, sans-serif;
  background-color: rgb(185, 225, 255);
  text-align: center;
  padding: 20px;
  width: 100%;
  box-shadow: rgba(0, 0, 0, 0.35) 0px 2px 15px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px; /* Add spacing between sections */
}

/* Section container */
.footer-sections {
  display: flex;
  justify-content: center;
  gap: 40px; /* Space between columns */
  flex-wrap: wrap; /* Wrap on smaller screens */
}

/* Footer Links */
.footer-links {
  list-style-type: none;
  padding: 0;
  margin: 0;
}

.footer-links li {
  margin: 5px 0; /* Add vertical spacing between items */
}

.footer a {
  color: #000000;
  transition: color 0.3s ease;
  text-decoration: none;
}

.footer a:hover {
  color: #002a77ed;
  text-decoration: underline;
}

/* Footer Branding */
.footer-branding {
  font-size: 0.9rem;
  color: #555;
}

/* Responsive Design */
@media screen and (max-width: 768px) {
  .footer-sections {
    flex-direction: column; /* Stack columns vertically */
    align-items: center; /* Center-align content */
    gap: 20px;
  }
}

@media screen and (max-width: 480px) {
  .footer {
    padding: 15px;
  }

  .footer-branding {
    font-size: 0.8rem; /* Reduce text size for smaller devices */
  }
}
</style>
