<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>MKS Wonders - Full E-commerce Site</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f5f5f5;
      transition: background-color 0.3s, color 0.3s;
    }
    header {
      background: linear-gradient(to right, #ff6f61, #ffcc70);
      color: white;
      padding: 20px;
      text-align: center;
    }
    .banner {
      background-image: url('https://via.placeholder.com/1200x200?text=Happy+Festive+Shopping+at+MKS+Wonders');
      background-size: cover;
      background-position: center;
      padding: 60px 20px;
      color: white;
      text-align: center;
      font-size: 24px;
    }
    .search-bar {
      text-align: center;
      padding: 10px;
    }
    .search-bar input {
      padding: 10px;
      width: 50%;
      border-radius: 10px;
      border: 1px solid #ccc;
    }
    .product {
      border: 1px solid #ccc;
      border-radius: 8px;
      padding: 16px;
      background: white;
      margin: 20px;
      width: 250px;
      display: inline-block;
      vertical-align: top;
    }
    .product img {
      width: 100%;
      height: 200px;
      object-fit: cover;
    }
    .tags {
      margin: 5px 0;
    }
    .best-seller, .discount, .stock-warning {
      display: inline-block;
      margin-right: 5px;
      padding: 2px 6px;
      border-radius: 5px;
      font-size: 12px;
      color: white;
    }
    .best-seller { background: red; }
    .discount { background: green; }
    .stock-warning { background: orange; }
    .review {
      font-size: 14px;
      color: #333;
    }
    .wishlist {
      color: red;
      cursor: pointer;
    }
    .faq, .gift-option {
      background: #fff;
      padding: 20px;
      margin: 20px;
      border-radius: 10px;
    }
    .dark-mode {
      background-color: #222;
      color: white;
    }
    footer {
      text-align: center;
      padding: 20px;
      background: #333;
      color: white;
    }
  </style>
</head>
<body>
  <header>
    <h1>MKS Wonders 🛍️</h1>
    <p>Books, Toys, Stationery, Gifts & Birthday Items</p>
    <button onclick="toggleDarkMode()">🌙 Toggle Dark/Light Mode</button>
  </header>  <div class="banner">
    ✨ Celebrate Your Moments With MKS Wonders – Festive Offers Running! ✨
  </div>  <div class="search-bar">
    <input type="text" id="search" placeholder="Search for products..." onkeyup="filterProducts()" />
  </div>  <!-- Product Example -->  <div class="product" data-name="Magic Birthday Kit">
    <div class="tags">
      <span class="best-seller">Best Seller</span>
      <span class="discount">10% OFF</span>
      <span class="stock-warning">Only 2 left!</span>
    </div>
    <img src="https://via.placeholder.com/250x200" alt="Product Image">
    <h3>Magic Birthday Kit</h3>
    <p class="review"><strong>Ayushi Verma:</strong> Loved it! 💖</p>
    <p class="wishlist" onclick="alert('Added to wishlist')">❤️ Add to Wishlist</p>
    <div class="gift-option">
      <label><input type="checkbox"> 🎁 Want Gift Wrapping?</label>
    </div>
    <button onclick="placeOrder()">Place Order via WhatsApp</button>
  </div>  <!-- FAQ Section -->  <div class="faq">
    <h2>Frequently Asked Questions</h2>
    <p><strong>Shipping Time?</strong> 3-5 Days across India.</p>
    <p><strong>Return Policy?</strong> Easy 7-day return policy.</p>
    <p><strong>Payment Options?</strong> UPI, Paytm, COD.</p>
  </div>  <footer>
    <p>© 2025 MKS Wonders. All rights reserved.</p>
    <p>Customer of the Week: <strong>Khushi Goyal</strong> 🎉</p>
  </footer>  <script>
    function toggleDarkMode() {
      document.body.classList.toggle("dark-mode");
    }

    function placeOrder() {
      let message = "Hello MKS Wonders! I want to place an order for Magic Birthday Kit. My details are: Name, Address, Phone.";
      let whatsappNumber = "918433076349"; // Add your number here e.g. 91xxxxxxxxxx
      window.open(`https://wa.me/${whatsappNumber}?text=${encodeURIComponent(message)}`, '_blank');
    }

    function filterProducts() {
      const input = document.getElementById("search").value.toLowerCase();
      const products = document.querySelectorAll(".product");
      products.forEach(product => {
        const name = product.getAttribute("data-name").toLowerCase();
        product.style.display = name.includes(input) ? "inline-block" : "none";
      });
    }
  </script></body>
</html>
