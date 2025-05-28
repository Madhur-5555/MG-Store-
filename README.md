<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>MKS Wonders</title>
  <style>
    :root {
      --bg-color: #f5f5f5;
      --text-color: #000;
      --card-bg: #fff;
    }
    body {
      background-color: var(--bg-color);
      color: var(--text-color);
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      transition: background-color 0.3s, color 0.3s;
    }
    .dark-mode {
      --bg-color: #222;
      --text-color: #fff;
      --card-bg: #333;
    }
    header, footer {
      background-color: #ff6f61;
      color: white;
      padding: 20px;
      text-align: center;
    }
    .banner {
      background: url('https://via.placeholder.com/1200x200?text=Festive+Sale+on+MKS+Wonders') no-repeat center;
      background-size: cover;
      padding: 50px;
      text-align: center;
      color: white;
      font-size: 24px;
    }
    .search-bar {
      text-align: center;
      padding: 20px;
    }
    .search-bar input {
      padding: 10px;
      width: 60%;
      border-radius: 8px;
      border: 1px solid #ccc;
    }
    .products {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
    }
    .product {
      background: var(--card-bg);
      color: var(--text-color);
      border: 1px solid #ccc;
      border-radius: 10px;
      margin: 15px;
      padding: 15px;
      width: 260px;
    }
    .product img {
      width: 100%;
      height: 200px;
      object-fit: cover;
    }
    .product .tags span {
      font-size: 12px;
      margin-right: 5px;
      padding: 2px 5px;
      border-radius: 5px;
      color: white;
    }
    .best-seller { background: red; }
    .discount { background: green; }
    .stock-warning { background: orange; }
    .wishlist { color: red; cursor: pointer; }
    .gift-option { margin-top: 10px; }
    .btn {
      background-color: #28a745;
      color: white;
      padding: 8px 12px;
      border: none;
      border-radius: 6px;
      cursor: pointer;
      margin-top: 10px;
    }
    footer p {
      margin: 5px 0;
    }
  </style>
</head>
<body>
  <header>
    <h1>MKS Wonders 🛍️</h1>
    <p>Books, Toys, Stationery, Gifts & More</p>
    <button onclick="toggleDarkMode()">🌙 Toggle Dark Mode</button>
  </header>  <div class="banner">
    🎉 Celebrate Special Moments with MKS Wonders 🎉
  </div>  <div class="search-bar">
    <input type="text" id="search" onkeyup="filterProducts()" placeholder="Search products...">
  </div>  <div class="products" id="product-list">
    <div class="product" data-name="Toy Car">
      <div class="tags">
        <span class="best-seller">Best Seller</span>
        <span class="discount">15% OFF</span>
        <span class="stock-warning">Hurry! 3 left</span>
      </div>
      <img src="https://via.placeholder.com/260x200" alt="Toy Car">
      <h3>Toy Car</h3>
      <p>Customer: Somya ⭐⭐⭐⭐⭐</p>
      <p class="wishlist" onclick="alert('Added to wishlist!')">❤️ Add to Wishlist</p>
      <div class="gift-option">
        <input type="checkbox"> 🎁 Gift Wrap
      </div>
      <input type="text" id="custName" placeholder="Your Name" style="width: 100%; margin-top: 8px;"><br>
      <input type="text" id="custAddress" placeholder="Your Address" style="width: 100%; margin-top: 8px;"><br>
      <input type="number" id="custPhone" placeholder="Your Phone" style="width: 100%; margin-top: 8px;"><br>
      <button class="btn" onclick="placeOrder()">🛒 Place Order on WhatsApp</button>
    </div>
  </div>  <footer>
    <p>📞 Customer Care: +91XXXXXXXXXX</p>
    <p>© 2025 MKS Wonders | Powered with ❤️</p>
  </footer>  <script>
    function toggleDarkMode() {
      document.body.classList.toggle('dark-mode');
    }

    function filterProducts() {
      let input = document.getElementById("search").value.toLowerCase();
      let products = document.querySelectorAll(".product");
      products.forEach(p => {
        let name = p.getAttribute("data-name").toLowerCase();
        p.style.display = name.includes(input) ? "block" : "none";
      });
    }

    function placeOrder() {
      let name = document.getElementById('custName').value;
      let address = document.getElementById('custAddress').value;
      let phone = document.getElementById('custPhone').value;
      let msg = `Hello, I want to order Toy Car.\nName: ${name}\nAddress: ${address}\nPhone: ${phone}`;
      let number = "918433076349"; // Add your number here like 91XXXXXXXXXX
      window.open(`https://wa.me/${number}?text=${encodeURIComponent(msg)}`, '_blank');
    }
  </script></body>
</html>
