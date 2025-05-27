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
