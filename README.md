<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>MKS Wonders - Home</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    <h1>MKS Wonders</h1>
    <nav>
      <a href="#">Home</a>
      <a href="#books">Books</a>
      <a href="#toys">Toys</a>
      <a href="#stationery">Stationery</a>
      <a href="#gifts">Gifts</a>
      <a href="#birthday">Birthday Items</a>
      <a href="cart.html">Cart</a>
    </nav>
  </header>  <section class="hero">
    <h2>Welcome to MKS Wonders</h2>
    <p>Books, Toys, Stationery, Gifts & More – Delivered with Wonder!</p>
  </section>  <section id="products" class="product-grid">
    <!-- Sample Products -->
    <div class="product" data-category="books">
      <img src="https://via.placeholder.com/200x150" alt="Book">
      <h3>Magic of Words</h3>
      <p>Rs. 299</p>
      <button onclick="addToCart('Magic of Words', 299)">Add to Cart</button>
    </div><div class="product" data-category="toys">
  <img src="https://via.placeholder.com/200x150" alt="Toy">
  <h3>Robo Car</h3>
  <p>Rs. 499</p>
  <button onclick="addToCart('Robo Car', 499)">Add to Cart</button>
</div>

<div class="product" data-category="stationery">
  <img src="https://via.placeholder.com/200x150" alt="Stationery">
  <h3>Creative Pen Set</h3>
  <p>Rs. 199</p>
  <button onclick="addToCart('Creative Pen Set', 199)">Add to Cart</button>
</div>

<div class="product" data-category="gifts">
  <img src="https://via.placeholder.com/200x150" alt="Gift">
  <h3>Mini Teddy Gift Box</h3>
  <p>Rs. 349</p>
  <button onclick="addToCart('Mini Teddy Gift Box', 349)">Add to Cart</button>
</div>

<div class="product" data-category="birthday">
  <img src="https://via.placeholder.com/200x150" alt="Birthday">
  <h3>Birthday Decoration Kit</h3>
  <p>Rs. 599</p>
  <button onclick="addToCart('Birthday Decoration Kit', 599)">Add to Cart</button>
</div>

  </section>  <script>
    function addToCart(name, price) {
      let cart = JSON.parse(localStorage.getItem('cart')) || [];
      cart.push({ name, price });
      localStorage.setItem('cart', JSON.stringify(cart));
      alert(`${name} added to cart!`);
    }
  </script></body>
</html>
<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Madhur's Store</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background-color: #f4f4f4;
    }
    header {
      background-color: #00bcd4;
      color: white;
      padding: 15px;
      text-align: center;
      font-size: 24px;
      font-weight: bold;
    }
    .products {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 20px;
      padding: 20px;
    }
    .product {
      background: white;
      padding: 15px;
      border-radius: 8px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      text-align: center;
    }
    .product img {
      width: 100%;
      height: 150px;
      object-fit: cover;
      border-radius: 6px;
    }
    .product h3 {
      margin: 10px 0 5px;
    }
    .product p {
      margin: 5px 0;
    }
    .add-btn {
      background-color: #00bcd4;
      color: white;
      border: none;
      padding: 10px 15px;
      border-radius: 5px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <header>Madhur's E-Commerce Store</header>  <section class="products">
    <div class="product">
      <img src="https://via.placeholder.com/200x150" alt="Product 1">
      <h3>Smart Watch</h3>
      <p>Rs. 1999</p>
      <button class="add-btn" onclick="alert('Added Smart Watch to cart!')">Add to Cart</button>
    </div>
    <div class="product">
      <img src="https://via.placeholder.com/200x150" alt="Product 2">
      <h3>Bluetooth Speaker</h3>
      <p>Rs. 999</p>
      <button class="add-btn" onclick="alert('Added Speaker to cart!')">Add to Cart</button>
    </div>
    <div class="product">
      <img src="https://via.placeholder.com/200x150" alt="Product 3">
      <h3>Wireless Earbuds</h3>
      <p>Rs. 1499</p>
      <button class="add-btn" onclick="alert('Added Earbuds to cart!')">Add to Cart</button>
    </div>
  </section>
</body>
</html>
