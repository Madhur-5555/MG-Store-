<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
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
      background-color: black;
      height: 300px;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    .text-box {
      background-color: white;
      color: black;
      padding: 30px 60px;
      border-radius: 12px;
      font-size: 28px;
      font-weight: bold;
      box-shadow: 0 0 15px rgba(0, 0, 0, 0.3);
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
      text-align: center;
    }
    .product img {
      width: 100%;
      height: 200px;
      object-fit: cover;
    }
    .btn {
      background-color: #28a745;
      color: white;
      padding: 8px 12px;
      border: none;
      border-radius: 6px;
      cursor: pointer;
      margin-top: 10px;
    }
    .cart {
      max-width: 600px;
      margin: auto;
      padding: 20px;
      border-top: 2px dashed #aaa;
    }
    .cart-item {
      display: flex;
      justify-content: space-between;
      margin: 10px 0;
    }
    input, textarea {
      width: 100%;
      margin: 8px 0;
      padding: 8px;
      border-radius: 5px;
      border: 1px solid #ccc;
    }
  </style>
</head>
<body>
  <header>
    <h1>MKS Wonders 🛍️</h1>
    <p>Books, Toys, Stationery, Gifts & More</p>
    <button onclick="toggleDarkMode()">🌙 Toggle Dark Mode</button>
  </header>

  <div class="banner">
    <div class="text-box">🎉 Celebrate Special Moments with MKS Wonders 🎉</div>
  </div>

  <div class="search-bar">
    <input type="text" id="search" onkeyup="filterProducts()" placeholder="Search products...">
  </div>

  <div class="products" id="product-list"></div>

  <div class="cart" id="cart">
    <h2>Your Cart</h2>
    <div id="cart-items"></div>
    <h3 id="total">Total: ₹0</h3>
    <h3>Place Your Order</h3>
    <input type="text" id="name" placeholder="Your Name" required>
    <input type="tel" id="phone" placeholder="Your Phone Number" required>
    <textarea id="address" placeholder="Delivery Address" required></textarea>
    <button class="btn" onclick="placeOrder()">🟢 Place Order on WhatsApp</button>
  </div>

  <footer>
    <p>📞 Customer Care: +91XXXXXXXXXX</p>
    <p>© 2025 MKS Wonders | Powered by Madhur Gupta</p>
  </footer>

  <script>
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
      div.setAttribute('data-name', prod.name);
      div.innerHTML = `
        <img src="https://via.placeholder.com/260x200?text=${prod.name.replace(/ /g, "+")}" />
        <h3>${prod.name}</h3>
        <p>₹${prod.price}</p>
        <button class="btn" onclick="addToCart(${index})">➕ Add to Cart</button>
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
        div.innerHTML = `${item.name} - ₹${item.price} <button onclick="removeItem(${i})">❌ Remove</button>`;
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
        alert('Please fill all fields and add at least one item to cart.');
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
  </script>
</body>
</html>
