<template>
    <footer class="footer">
      <div class="footer-container">
        <!-- Logo -->
        <div class="footer-logo">
          <img src="@/assets/LOGO.svg" alt="discussit logo" />
        </div>
  
        <!-- Social Icons -->
        <div class="footer-social">
          <a href="#" class="social-icon"><i class="fab fa-x-twitter"></i></a>
          <a href="#" class="social-icon"><i class="fab fa-instagram"></i></a>
          <a href="#" class="social-icon"><i class="fab fa-linkedin-in"></i></a>
        </div>
  
        <!-- Links -->
        <nav class="footer-links">
          <a href="#">About</a>
          <a href="#">Contact us</a>
          <a href="#">Terms & Conditions</a>
          <a href="#">Privacy Policy</a>
          <a href="#">FAQs</a>
          <a href="#">Feedback</a>
          <a href="#">Enterprise Solutions</a>
        </nav>
  
        <!-- Copyright -->
        <div class="footer-copyright">
          <p>&copy; 2024 discussit</p>
        </div>
      </div>
    </footer>
  </template>


<script>
export default {
    name: "Footer",
}
</script>

<style scoped>
.footer {
  background-color: #2d3237;
  color: #ffffff;
  padding: 20px 0;
  font-family: Arial, sans-serif;
}

.footer-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  gap: 10px;
}

.footer-logo img {
  width: 150px;
  height: auto;
  margin-bottom: 10px;
}

.footer-social {
  display: flex;
  justify-content: center;
  gap: 15px;
  margin: 10px 0;
}

.social-icon {
  color: #ffffff;
  font-size: 1.2rem;
  transition: color 0.3s ease;
}

.social-icon:hover {
  color: #ffa500;
}

.footer-links {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 15px;
  margin: 10px 0;
}

.footer-links a {
  color: #ffffff;
  text-decoration: none;
  font-size: 0.9rem;
  transition: color 0.3s ease;
}

.footer-links a:hover {
  color: #ffa500;
}

.footer-copyright {
  font-size: 0.8rem;
  margin-top: 10px;
  color: #b0b3b8;
}

</style>  