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
    .Add-to-cart { color: red; cursor: pointer; }
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
  </header>
    .banner {
      background-color: black;    /* Outer black margin */
      height: 300px;              /* Banner height */
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .text-box {
      background-color: white;    /* Text ke peeche white background */
      color: black;               /* Text color */
      padding: 30px 60px;         /* Andar ka gap */
      border-radius: 12px;        /* Round corners (optional) */
      font-size: 28px;
      font-weight: bold;
      box-shadow: 0 0 15px rgba(0, 0, 0, 0.3); /* Thoda shadow effect */
    }
  </style>
</head>
<body>

  <div class="banner">
    <div class="text-box">
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
      <p class="Add-to-cart" onclick="alert('Added to cart!')">❤️ Add to cart</p>
      <div class="gift-option">
        <input type="checkbox"> 🎁 Gift Wrap
      </div>
      <input type="text" id="custName" placeholder="Your Name" style="width: 100%; margin-top: 8px;"><br>
      <input type="text" id="custAddress" placeholder="Your Address" style="width: 100%; margin-top: 8px;"><br>
      <input type="number" id="custPhone" placeholder="Your Phone" style="width: 100%; margin-top: 8px;"><br>
      <button class="btn" onclick="placeOrder()">🛒 Place Order via WhatsApp</button>
    </div>
  </div>  <footer>
    <p>📞 Customer Care: +91XXXXXXXXXX</p>
    <p>© 2025 MKS Wonders | Powered with Madhur Gupta</p>
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

<div class="container">
    <div class="product-grid" id="product-list"></div><div class="cart" id="cart">
  <h2>Your Cart</h2>
  <div id="cart-items"></div>
  <h3 id="total">Total: ₹0</h3>

  <h3>Place Your Order</h3>
  <input type="text" id="name" placeholder="Your Name" required>
  <input type="tel" id="phone" placeholder="Your Phone Number" required>
  <textarea id="address" placeholder="Delivery Address" required></textarea>
  <button onclick="placeOrder()">Place Order on WhatsApp</button>
</div>

  </div>  <script>
    const products = [
      { name: "The Magic of Words", price: 299 },
      { name: "Robotic Toy Car", price: 499 },
      { name: "Birthday Gift Box", price: 399 },
      { name: "Color Stationery Set", price: 199 },
      { name: "Fun Story Book", price: 249 }
    ];

    const productList = document.getElementById('product-list');
    const cartItems = document.getElementById('cart-items');
    const totalDisplay = document.getElementById('total');

    let cart = [];

    products.forEach((prod, index) => {
      const div = document.createElement('div');
      div.className = 'product';
      div.innerHTML = `
        <img src="https://via.placeholder.com/200x150?text=${prod.name.replace(/ /g, "+")}" />
        <h3>${prod.name}</h3>
        <p>₹${prod.price}</p>
        <button onclick="addToCart(${index})">Add to Cart</button>
      `;
      productList.appendChild(div);
    });

    function addToCart(index) {
      const item = products[index];
      cart.push(item);
      displayCart();
    }

    function displayCart() {
      cartItems.innerHTML = '';
      let total = 0;
      cart.forEach((item, i) => {
        total += item.price;
        const div = document.createElement('div');
        div.className = 'cart-item';
        div.innerHTML = `${item.name} - ₹${item.price} <button onclick="removeItem(${i})">Remove</button>`;
        cartItems.appendChild(div);
      });
      totalDisplay.innerText = `Total: ₹${total}`;
    }

    function removeItem(index) {
      cart.splice(index, 1);
      displayCart();
    }

    function placeOrder() {
      const name = document.getElementById('name').value.trim();
      const phone = document.getElementById('phone').value.trim();
      const address = document.getElementById('address').value.trim();
      if (!name || !phone || !address || cart.length === 0) {
        alert('Please fill all fields and add items to cart.');
        return;
      }

      let orderMsg = `New Order from MKS Wonders%0A%0AName: ${name}%0APhone: ${phone}%0AAddress: ${address}%0AItems:`;
      let total = 0;
      cart.forEach(item => {
        orderMsg += `%0A- ${item.name} (₹${item.price})`;
        total += item.price;
      });
      orderMsg += `%0A%0ATotal: ₹${total}`;

      const whatsappNumber = '918433076349';
      window.open(`https://wa.me/${whatsappNumber}?text=${orderMsg}`, '_blank');
    }
  </script></body>
</html>
