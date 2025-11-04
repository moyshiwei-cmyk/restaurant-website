<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Savory Bites - Order Online</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #e74c3c;
            --primary-dark: #c0392b;
            --secondary: #f39c12;
            --dark: #2c3e50;
            --light: #ecf0f1;
            --success: #27ae60;
            --warning: #f1c40f;
            --danger: #e74c3c;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f9f9f9;
            color: #333;
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header Styles */
        header {
            background-color: white;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .logo i {
            color: var(--primary);
            font-size: 28px;
        }
        
        .logo h1 {
            font-size: 24px;
            color: var(--dark);
        }
        
        .logo span {
            color: var(--primary);
        }
        
        nav ul {
            display: flex;
            list-style: none;
            gap: 25px;
        }
        
        nav a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            transition: color 0.3s;
        }
        
        nav a:hover {
            color: var(--primary);
        }
        
        .cart-icon {
            position: relative;
            cursor: pointer;
        }
        
        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background-color: var(--primary);
            color: white;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 12px;
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), url('https://images.unsplash.com/photo-1504674900247-0877df9cc836?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80');
            background-size: cover;
            background-position: center;
            color: white;
            padding: 80px 0;
            text-align: center;
        }
        
        .hero h2 {
            font-size: 42px;
            margin-bottom: 20px;
        }
        
        .hero p {
            font-size: 18px;
            max-width: 700px;
            margin: 0 auto 30px;
        }
        
        .btn {
            display: inline-block;
            background-color: var(--primary);
            color: white;
            padding: 12px 25px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: background-color 0.3s;
            border: none;
            cursor: pointer;
        }
        
        .btn:hover {
            background-color: var(--primary-dark);
        }
        
        .btn-secondary {
            background-color: var(--secondary);
        }
        
        .btn-secondary:hover {
            background-color: #e67e22;
        }
        
        /* QR Section */
        .qr-section {
            padding: 60px 0;
            background-color: white;
            text-align: center;
        }
        
        .qr-container {
            max-width: 500px;
            margin: 0 auto;
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .qr-code {
            width: 250px;
            height: 250px;
            margin: 20px auto;
            background-color: #f5f5f5;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 10px;
        }
        
        .qr-code img {
            max-width: 100%;
            max-height: 100%;
        }
        
        /* Menu Section */
        .menu-section {
            padding: 60px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 40px;
        }
        
        .section-title h2 {
            font-size: 32px;
            color: var(--dark);
            margin-bottom: 10px;
        }
        
        .section-title p {
            color: #777;
            max-width: 600px;
            margin: 0 auto;
        }
        
        .category-tabs {
            display: flex;
            justify-content: center;
            margin-bottom: 30px;
            flex-wrap: wrap;
            gap: 10px;
        }
        
        .category-tab {
            padding: 10px 20px;
            background-color: white;
            border: 1px solid #ddd;
            border-radius: 30px;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .category-tab.active {
            background-color: var(--primary);
            color: white;
            border-color: var(--primary);
        }
        
        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
        }
        
        .menu-item {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: transform 0.3s;
        }
        
        .menu-item:hover {
            transform: translateY(-5px);
        }
        
        .item-image {
            height: 180px;
            background-color: #f5f5f5;
            background-size: cover;
            background-position: center;
        }
        
        .item-content {
            padding: 20px;
        }
        
        .item-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 10px;
        }
        
        .item-title {
            font-size: 18px;
            font-weight: 600;
            color: var(--dark);
        }
        
        .item-price {
            font-weight: 700;
            color: var(--primary);
        }
        
        .item-description {
            color: #777;
            font-size: 14px;
            margin-bottom: 15px;
        }
        
        .item-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .quantity-controls {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .quantity-btn {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            background-color: #f5f5f5;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .quantity-btn:hover {
            background-color: #e0e0e0;
        }
        
        .add-to-cart {
            background-color: var(--primary);
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 20px;
            cursor: pointer;
            transition: background-color 0.3s;
            font-weight: 500;
        }
        
        .add-to-cart:hover {
            background-color: var(--primary-dark);
        }
        
        /* Cart Modal */
        .cart-modal {
            position: fixed;
            top: 0;
            right: -400px;
            width: 380px;
            height: 100vh;
            background-color: white;
            box-shadow: -5px 0 15px rgba(0,0,0,0.1);
            transition: right 0.3s ease;
            z-index: 1000;
            display: flex;
            flex-direction: column;
        }
        
        .cart-modal.open {
            right: 0;
        }
        
        .cart-header {
            padding: 20px;
            border-bottom: 1px solid #eee;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .close-cart {
            background: none;
            border: none;
            font-size: 20px;
            cursor: pointer;
            color: #777;
        }
        
        .cart-items {
            flex: 1;
            overflow-y: auto;
            padding: 20px;
        }
        
        .cart-item {
            display: flex;
            margin-bottom: 20px;
            padding-bottom: 20px;
            border-bottom: 1px solid #eee;
        }
        
        .cart-item-image {
            width: 80px;
            height: 80px;
            border-radius: 8px;
            background-color: #f5f5f5;
            background-size: cover;
            background-position: center;
            margin-right: 15px;
        }
        
        .cart-item-details {
            flex: 1;
        }
        
        .cart-item-title {
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .cart-item-price {
            color: var(--primary);
            font-weight: 600;
        }
        
        .cart-item-controls {
            display: flex;
            align-items: center;
            margin-top: 10px;
        }
        
        .cart-quantity {
            margin: 0 10px;
        }
        
        .remove-item {
            color: var(--danger);
            background: none;
            border: none;
            cursor: pointer;
            margin-left: auto;
        }
        
        .cart-footer {
            padding: 20px;
            border-top: 1px solid #eee;
        }
        
        .cart-total {
            display: flex;
            justify-content: space-between;
            margin-bottom: 20px;
            font-weight: 600;
            font-size: 18px;
        }
        
        .checkout-btn {
            width: 100%;
            padding: 15px;
            background-color: var(--primary);
            color: white;
            border: none;
            border-radius: 5px;
            font-weight: 600;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .checkout-btn:hover {
            background-color: var(--primary-dark);
        }
        
        /* Footer */
        footer {
            background-color: var(--dark);
            color: white;
            padding: 60px 0 30px;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .footer-column h3 {
            font-size: 18px;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-column h3::after {
            content: '';
            position: absolute;
            left: 0;
            bottom: 0;
            width: 40px;
            height: 2px;
            background-color: var(--primary);
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 10px;
        }
        
        .footer-links a {
            color: #bbb;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-links a:hover {
            color: white;
        }
        
        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }
        
        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: rgba(255,255,255,0.1);
            border-radius: 50%;
            color: white;
            transition: background-color 0.3s;
        }
        
        .social-links a:hover {
            background-color: var(--primary);
        }
        
        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255,255,255,0.1);
            color: #bbb;
            font-size: 14px;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 15px;
            }
            
            .hero h2 {
                font-size: 32px;
            }
            
            .cart-modal {
                width: 100%;
                right: -100%;
            }
            
            .menu-grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <i class="fas fa-utensils"></i>
                    <h1>Savory <span>Bites</span></h1>
                </div>
                <nav>
                    <ul>
                        <li><a href="#home">Home</a></li>
                        <li><a href="#menu">Menu</a></li>
                        <li><a href="#about">About</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </nav>
                <div class="cart-icon" id="cartIcon">
                    <i class="fas fa-shopping-cart"></i>
                    <span class="cart-count">0</span>
                </div>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <h2>Delicious Food Delivered To Your Table</h2>
            <p>Order your favorite meals using our QR code system for a contactless dining experience. Scan, order, and enjoy!</p>
            <a href="#menu" class="btn">View Menu</a>
        </div>
    </section>

    <!-- QR Section -->
    <section class="qr-section">
        <div class="container">
            <h2>Scan to Order</h2>
            <p>Use your phone's camera to scan the QR code and access our digital menu</p>
            <div class="qr-container">
                <div class="qr-code">
                    <!-- In a real implementation, this would be a generated QR code -->
                    <img src="https://api.qrserver.com/v1/create-qr-code/?size=200x200&data=https://savorybites.com/menu" alt="QR Code">
                </div>
                <p>Point your camera at the QR code to order</p>
            </div>
        </div>
    </section>

    <!-- Menu Section -->
    <section class="menu-section" id="menu">
        <div class="container">
            <div class="section-title">
                <h2>Our Menu</h2>
                <p>Discover our delicious selection of dishes made with the freshest ingredients</p>
            </div>
            
            <div class="category-tabs">
                <div class="category-tab active" data-category="all">All</div>
                <div class="category-tab" data-category="appetizers">Appetizers</div>
                <div class="category-tab" data-category="mains">Main Courses</div>
                <div class="category-tab" data-category="desserts">Desserts</div>
                <div class="category-tab" data-category="drinks">Drinks</div>
            </div>
            
            <div class="menu-grid" id="menuGrid">
                <!-- Menu items will be dynamically inserted here -->
            </div>
        </div>
    </section>

    <!-- Cart Modal -->
    <div class="cart-modal" id="cartModal">
        <div class="cart-header">
            <h3>Your Order</h3>
            <button class="close-cart" id="closeCart">&times;</button>
        </div>
        <div class="cart-items" id="cartItems">
            <!-- Cart items will be dynamically inserted here -->
        </div>
        <div class="cart-footer">
            <div class="cart-total">
                <span>Total:</span>
                <span id="cartTotal">$0.00</span>
            </div>
            <button class="checkout-btn" id="checkoutBtn">Proceed to Checkout</button>
        </div>
    </div>

    <!-- Footer -->
    <footer id="contact">
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>Savory Bites</h3>
                    <p>We serve delicious, high-quality food in a comfortable atmosphere. Our QR ordering system makes dining safe and convenient.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                    </div>
                </div>
                <div class="footer-column">
                    <h3>Quick Links</h3>
                    <ul class="footer-links">
                        <li><a href="#home">Home</a></li>
                        <li><a href="#menu">Menu</a></li>
                        <li><a href="#about">About Us</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Contact Info</h3>
                    <ul class="footer-links">
                        <li><i class="fas fa-map-marker-alt"></i> 123 Restaurant St, Food City</li>
                        <li><i class="fas fa-phone"></i> (555) 123-4567</li>
                        <li><i class="fas fa-envelope"></i> info@savorybites.com</li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Opening Hours</h3>
                    <ul class="footer-links">
                        <li>Monday - Friday: 11am - 10pm</li>
                        <li>Saturday: 10am - 11pm</li>
                        <li>Sunday: 10am - 9pm</li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 Savory Bites Restaurant. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Sample menu data
        const menuItems = [
            {
                id: 1,
                name: "Bruschetta",
                category: "appetizers",
                price: 8.99,
                description: "Toasted bread topped with tomatoes, garlic, and fresh basil",
                image: "https://images.unsplash.com/photo-1572695157366-5e585ab2b69f?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1471&q=80"
            },
            {
                id: 2,
                name: "Mozzarella Sticks",
                category: "appetizers",
                price: 7.99,
                description: "Crispy breaded mozzarella served with marinara sauce",
                image: "https://images.unsplash.com/photo-1563379926898-05f4575a45d8?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80"
            },
            {
                id: 3,
                name: "Grilled Salmon",
                category: "mains",
                price: 18.99,
                description: "Fresh salmon fillet with lemon butter sauce and seasonal vegetables",
                image: "https://images.unsplash.com/photo-1467003909585-2f8a72700288?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=687&q=80"
            },
            {
                id: 4,
                name: "Beef Burger",
                category: "mains",
                price: 14.99,
                description: "Juicy beef patty with cheese, lettuce, tomato, and special sauce",
                image: "https://images.unsplash.com/photo-1568901346375-23c9450c58cd?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=699&q=80"
            },
            {
                id: 5,
                name: "Vegetable Pasta",
                category: "mains",
                price: 12.99,
                description: "Penne pasta with fresh vegetables in a light tomato sauce",
                image: "https://images.unsplash.com/photo-1551183053-bf91a1d81141?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1632&q=80"
            },
            {
                id: 6,
                name: "Chocolate Cake",
                category: "desserts",
                price: 6.99,
                description: "Rich chocolate cake with a creamy chocolate frosting",
                image: "https://images.unsplash.com/photo-1578985545062-69928b1d9587?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1089&q=80"
            },
            {
                id: 7,
                name: "Cheesecake",
                category: "desserts",
                price: 7.99,
                description: "Creamy New York style cheesecake with berry compote",
                image: "https://images.unsplash.com/photo-1535920527002-b35e96722206?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=687&q=80"
            },
            {
                id: 8,
                name: "Iced Coffee",
                category: "drinks",
                price: 4.99,
                description: "Chilled coffee with milk and sweetener of your choice",
                image: "https://images.unsplash.com/photo-1517701604599-bb29b565090c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=687&q=80"
            },
            {
                id: 9,
                name: "Fresh Lemonade",
                category: "drinks",
                price: 3.99,
                description: "Freshly squeezed lemons with a hint of mint",
                image: "https://images.unsplash.com/photo-1621506289937-a8e4df240d0b?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=686&q=80"
            }
        ];

        // Cart functionality
        let cart = [];
        const cartIcon = document.getElementById('cartIcon');
        const cartModal = document.getElementById('cartModal');
        const closeCart = document.getElementById('closeCart');
        const cartItems = document.getElementById('cartItems');
        const cartTotal = document.getElementById('cartTotal');
        const checkoutBtn = document.getElementById('checkoutBtn');
        const menuGrid = document.getElementById('menuGrid');
        const categoryTabs = document.querySelectorAll('.category-tab');

        // Initialize the menu
        function initializeMenu() {
            menuGrid.innerHTML = '';
            menuItems.forEach(item => {
                const menuItemElement = document.createElement('div');
                menuItemElement.className = 'menu-item';
                menuItemElement.dataset.category = item.category;
                menuItemElement.innerHTML = `
                    <div class="item-image" style="background-image: url('${item.image}')"></div>
                    <div class="item-content">
                        <div class="item-header">
                            <h3 class="item-title">${item.name}</h3>
                            <span class="item-price">$${item.price.toFixed(2)}</span>
                        </div>
                        <p class="item-description">${item.description}</p>
                        <div class="item-footer">
                            <div class="quantity-controls">
                                <div class="quantity-btn minus" data-id="${item.id}">-</div>
                                <span class="quantity" data-id="${item.id}">0</span>
                                <div class="quantity-btn plus" data-id="${item.id}">+</div>
                            </div>
                            <button class="add-to-cart" data-id="${item.id}">Add to Cart</button>
                        </div>
                    </div>
                `;
                menuGrid.appendChild(menuItemElement);
            });

            // Add event listeners for quantity controls and add to cart buttons
            document.querySelectorAll('.quantity-btn.plus').forEach(btn => {
                btn.addEventListener('click', function() {
                    const id = parseInt(this.dataset.id);
                    increaseQuantity(id);
                });
            });

            document.querySelectorAll('.quantity-btn.minus').forEach(btn => {
                btn.addEventListener('click', function() {
                    const id = parseInt(this.dataset.id);
                    decreaseQuantity(id);
                });
            });

            document.querySelectorAll('.add-to-cart').forEach(btn => {
                btn.addEventListener('click', function() {
                    const id = parseInt(this.dataset.id);
                    addToCart(id);
                });
            });
        }

        // Category filtering
        categoryTabs.forEach(tab => {
            tab.addEventListener('click', function() {
                const category = this.dataset.category;
                
                // Update active tab
                categoryTabs.forEach(t => t.classList.remove('active'));
                this.classList.add('active');
                
                // Filter menu items
                const allMenuItems = document.querySelectorAll('.menu-item');
                allMenuItems.forEach(item => {
                    if (category === 'all' || item.dataset.category === category) {
                        item.style.display = 'block';
                    } else {
                        item.style.display = 'none';
                    }
                });
            });
        });

        // Cart functions
        function addToCart(id) {
            const item = menuItems.find(i => i.id === id);
            const existingItem = cart.find(i => i.id === id);
            
            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                cart.push({
                    ...item,
                    quantity: 1
                });
            }
            
            updateCart();
            updateQuantityDisplay(id);
        }

        function increaseQuantity(id) {
            const item = cart.find(i => i.id === id);
            if (item) {
                item.quantity += 1;
            } else {
                addToCart(id);
            }
            updateCart();
            updateQuantityDisplay(id);
        }

        function decreaseQuantity(id) {
            const itemIndex = cart.findIndex(i => i.id === id);
            if (itemIndex !== -1) {
                if (cart[itemIndex].quantity > 1) {
                    cart[itemIndex].quantity -= 1;
                } else {
                    cart.splice(itemIndex, 1);
                }
            }
            updateCart();
            updateQuantityDisplay(id);
        }

        function removeFromCart(id) {
            const itemIndex = cart.findIndex(i => i.id === id);
            if (itemIndex !== -1) {
                cart.splice(itemIndex, 1);
            }
            updateCart();
            updateQuantityDisplay(id);
        }

        function updateQuantityDisplay(id) {
            const quantityElement = document.querySelector(`.quantity[data-id="${id}"]`);
            const cartItem = cart.find(i => i.id === id);
            quantityElement.textContent = cartItem ? cartItem.quantity : 0;
        }

        function updateCart() {
            // Update cart count
            const cartCount = document.querySelector('.cart-count');
            const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
            cartCount.textContent = totalItems;
            
            // Update cart items
            cartItems.innerHTML = '';
            if (cart.length === 0) {
                cartItems.innerHTML = '<p style="text-align: center; padding: 20px;">Your cart is empty</p>';
            } else {
                cart.forEach(item => {
                    const cartItemElement = document.createElement('div');
                    cartItemElement.className = 'cart-item';
                    cartItemElement.innerHTML = `
                        <div class="cart-item-image" style="background-image: url('${item.image}')"></div>
                        <div class="cart-item-details">
                            <div class="cart-item-title">${item.name}</div>
                            <div class="cart-item-price">$${item.price.toFixed(2)}</div>
                            <div class="cart-item-controls">
                                <div class="quantity-btn minus" data-id="${item.id}">-</div>
                                <span class="cart-quantity">${item.quantity}</span>
                                <div class="quantity-btn plus" data-id="${item.id}">+</div>
                                <button class="remove-item" data-id="${item.id}"><i class="fas fa-trash"></i></button>
                            </div>
                        </div>
                    `;
                    cartItems.appendChild(cartItemElement);
                });
                
                // Add event listeners for cart controls
                document.querySelectorAll('.cart-item .quantity-btn.plus').forEach(btn => {
                    btn.addEventListener('click', function() {
                        const id = parseInt(this.dataset.id);
                        increaseQuantity(id);
                    });
                });
                
                document.querySelectorAll('.cart-item .quantity-btn.minus').forEach(btn => {
                    btn.addEventListener('click', function() {
                        const id = parseInt(this.dataset.id);
                        decreaseQuantity(id);
                    });
                });
                
                document.querySelectorAll('.remove-item').forEach(btn => {
                    btn.addEventListener('click', function() {
                        const id = parseInt(this.dataset.id);
                        removeFromCart(id);
                    });
                });
            }
            
            // Update total
            const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            cartTotal.textContent = `$${total.toFixed(2)}`;
        }

        // Event listeners for cart modal
        cartIcon.addEventListener('click', function() {
            cartModal.classList.add('open');
        });

        closeCart.addEventListener('click', function() {
            cartModal.classList.remove('open');
        });

        checkoutBtn.addEventListener('click', function() {
            if (cart.length === 0) {
                alert('Your cart is empty!');
                return;
            }
            alert('Thank you for your order! Your food will be prepared shortly.');
            cart = [];
            updateCart();
            document.querySelectorAll('.quantity').forEach(el => {
                el.textContent = '0';
            });
            cartModal.classList.remove('open');
        });

        // Initialize the application
        initializeMenu();
    </script>
</body>
</html>
