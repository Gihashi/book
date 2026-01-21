<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Readora Books</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, Helvetica, sans-serif;
      background-color: #f8f8f8;
    }
    header {
      background-color: #2c2c54;
      color: white;
      padding: 20px;
      text-align: center;
    }
    nav {
      background-color: #40407a;
      padding: 10px;
      text-align: center;
    }
    nav a {
      color: white;
      margin: 0 15px;
      text-decoration: none;
      font-weight: bold;
    }
    .hero {
      padding: 60px 20px;
      text-align: center;
      background-color: #ffffff;
    }
    .hero h1 {
      color: #2c2c54;
    }
    .books {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 20px;
      padding: 40px;
    }
    .book-card {
      background-color: white;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
      text-align: center;
    }
    .book-card img {
      width: 100%;
      height: 280px;
      object-fit: cover;
      border-radius: 6px;
    }
    .book-card h3 {
      margin: 15px 0 5px;
    }
    .book-card button {
      background-color: #2c2c54;
      color: white;
      border: none;
      padding: 10px 15px;
      border-radius: 5px;
      cursor: pointer;
    }
    footer {
      background-color: #2c2c54;
      color: white;
      text-align: center;
      padding: 15px;
      margin-top: 40px;
    }
  </style>
</head>
<body>

<header>
  <h1>Readora Books</h1>
  <p>Your online bookstore for knowledge & gifts</p>
</header>

<nav>
  <a href="#">Home</a>
  <a href="#books">Books</a>
  <a href="#about">About</a>
  <a href="#contact">Contact</a>
</nav>

<section class="hero">
  <h1>Discover Your Next Favorite Book</h1>
  <p>Novels • Educational • Gift Books</p>
</section>

<section id="books" class="books">
  <div class="book-card">
    <img src="https://via.placeholder.com/200x280" alt="Book 1">
    <h3>Book Title One</h3>
    <p>Rs. 1,200</p>
    <button onclick="addToCart('Book Title One',1200)">Add to Cart</button>
  </div>

  <div class="book-card">
    <img src="https://via.placeholder.com/200x280" alt="Book 2">
    <h3>Book Title Two</h3>
    <p>Rs. 1,500</p>
    <button onclick="addToCart('Book Title Two',1500)">Add to Cart</button>
  </div>

  <div class="book-card">
    <img src="https://via.placeholder.com/200x280" alt="Book 3">
    <h3>Book Title Three</h3>
    <p>Rs. 980</p>
    <button onclick="addToCart('Book Title Three',980)">Add to Cart</button>
  </div>
  <div class="book-card">
    <img src="https://via.placeholder.com/200x280" alt="Book 1">
    <h3>Book Title One</h3>
    <p>Rs. 1,200</p>
    <button>Add to Cart</button>
  </div>

  <div class="book-card">
    <img src="https://via.placeholder.com/200x280" alt="Book 2">
    <h3>Book Title Two</h3>
    <p>Rs. 1,500</p>
    <button>Add to Cart</button>
  </div>

  <div class="book-card">
    <img src="https://via.placeholder.com/200x280" alt="Book 3">
    <h3>Book Title Three</h3>
    <p>Rs. 980</p>
    <button>Add to Cart</button>
  </div>
</section>

<section style="background:#fff;padding:30px;max-width:500px;margin:40px auto;border-radius:8px;box-shadow:0 2px 8px rgba(0,0,0,0.1)">
  <h2>Your Cart</h2>
  <ul id="cart-items"></ul>
  <p id="cart-total">Total: Rs. 0</p>
  <button onclick="checkoutWhatsApp()" style="background:#25D366;color:white;border:none;padding:12px 20px;border-radius:6px;cursor:pointer;font-size:16px">Checkout via WhatsApp</button>
</section>

<footer id="contact">
  <p>📞 WhatsApp: +94XXXXXXXXX | 📧 readora@gmail.com</p>
  <p>© 2026 Readora Books</p>
</footer>

<script>
  let cart = [];

  function addToCart(title, price) {
    cart.push({ title, price });
    updateCart();
    alert(title + ' added to cart');
  }

  function updateCart() {
    const cartList = document.getElementById('cart-items');
    const totalEl = document.getElementById('cart-total');
    cartList.innerHTML = '';
    let total = 0;

    cart.forEach(item => {
      const li = document.createElement('li');
      li.textContent = `${item.title} - Rs. ${item.price}`;
      cartList.appendChild(li);
      total += item.price;
    });

    totalEl.textContent = 'Total: Rs. ' + total;
  }

  function checkoutWhatsApp() {
    if (cart.length === 0) {
      alert('Your cart is empty');
      return;
    }
    let message = 'Hello, I would like to order:%0A';
    let total = 0;
    cart.forEach(item => {
      message += `- ${item.title} (Rs. ${item.price})%0A`;
      total += item.price;
    });
    message += `%0ATotal: Rs. ${total}`;
    window.open('https://wa.me/94XXXXXXXXX?text=' + message, '_blank');
  }
</script>
</body>
</html>
# book
