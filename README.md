<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>MKS Wonders - E-commerce</title>
  <style>
    * { box-sizing: border-box; }
    body { font-family: Arial, sans-serif; margin: 0; padding: 0; background: #f2f2f2; }
    header { background: #222; color: white; padding: 1rem; text-align: center; }
    .container { padding: 20px; max-width: 1000px; margin: auto; }
    .product-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 20px; }
    .product { background: white; padding: 10px; border-radius: 10px; box-shadow: 0 0 5px rgba(0,0,0,0.1); }
    .product img { max-width: 100%; border-radius: 8px; }
    .product h3, .product p { margin: 5px 0; }
    button { background: #007bff; color: white; padding: 8px 12px; border: none; border-radius: 5px; cursor: pointer; }
    button:hover { background: #0056b3; }
    .cart { margin-top: 40px; background: #fff; padding: 20px; border-radius: 10px; }
    .cart-item { display: flex; justify-content: space-between; margin-bottom: 10px; }
    input, textarea { width: 100%; padding: 10px; margin-top: 10px; border-radius: 5px; border: 1px solid #ccc; }
  </style>
</head>
<body>
  <header>
    <h1>MKS Wonders</h1>
    <p>Books | Toys | Stationery | Gifts | Birthday Items</p>
  </header>  <div class="container">
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

      const whatsappNumber = '918433076349'; // <-- Put your number here like 919876543210
      window.open(`https://wa.me/${qr/LWVNIF3SLAU7K1}?text=${orderMsg}`, '_blank');
    }
  </script></body>
</html>
