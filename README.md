# UI-interface-for-supermarket
# Supermarket Web Interface with html language

This is a simple web interface for a supermarket, allowing users to view available items, add items to their shopping cart, and proceed to checkout. The project is built using HTML, CSS, and JavaScript.

## Features

- Display available supermarket items with their prices.
- Add items to a shopping cart.
- View the total price of items in the cart.
- Checkout and clear the cart.

## Getting Started

These instructions will help you set up and run the project on your local machine.

### Prerequisites

- A web browser (e.g., Google Chrome, Mozilla Firefox, Microsoft Edge).

### Installation

1. Clone the repository or download the `supermarket.html` file directly.

    ```bash
    git clone <repository-url>
    cd <repository-folder>
    ```

2. Ensure you have the 'supermarket.html` file saved on your local machine.

### Running the Application

1. Open the `supermarket.html` file in your preferred web browser. You can do this by double-clicking the file or right-clicking the file and selecting "Open with" and then choosing your web browser.

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Supermarket</title>
        <style>
            body {
                font-family: Arial, sans-serif;
            }
            .container {
                width: 80%;
                margin: auto;
                overflow: hidden;
            }
            #items {
                margin: 20px 0;
            }
            .item {
                border: 1px solid #ccc;
                margin: 10px 0;
                padding: 10px;
                display: flex;
                justify-content: space-between;
            }
            .item-details {
                flex: 1;
            }
            .item-actions {
                flex: 1;
                text-align: right;
            }
            #cart {
                margin: 20px 0;
                border: 1px solid #ccc;
                padding: 10px;
            }
            #cart-items {
                list-style: none;
                padding: 0;
            }
            #cart-items li {
                margin: 5px 0;
            }
            .cart-total {
                text-align: right;
            }
        </style>
    </head>
    <body>
        <div class="container">
            <h1>Welcome to the Supermarket!</h1>
            <h2>Available Items</h2>
            <div id="items">
                <div class="item">
                    <div class="item-details">
                        <h3>Bread</h3>
                        <p>Price: $2.50</p>
                    </div>
                    <div class="item-actions">
                        <button onclick="addToCart('Bread', 2.50)">Add to Cart</button>
                    </div>
                </div>
                <div class="item">
                    <div class="item-details">
                        <h3>Milk</h3>
                        <p>Price: $1.50</p>
                    </div>
                    <div class="item-actions">
                        <button onclick="addToCart('Milk', 1.50)">Add to Cart</button>
                    </div>
                </div>
                <div class="item">
                    <div class="item-details">
                        <h3>Eggs</h3>
                        <p>Price: $3.00</p>
                    </div>
                    <div class="item-actions">
                        <button onclick="addToCart('Eggs', 3.00)">Add to Cart</button>
                    </div>
                </div>
                <div class="item">
                    <div class="item-details">
                        <h3>Apple</h3>
                        <p>Price: $1.00</p>
                    </div>
                    <div class="item-actions">
                        <button onclick="addToCart('Apple', 1.00)">Add to Cart</button>
                    </div>
                </div>
            </div>

            <h2>Shopping Cart</h2>
            <div id="cart">
                <ul id="cart-items"></ul>
                <p class="cart-total">Total: $<span id="cart-total">0.00</span></p>
                <button onclick="checkout()">Checkout</button>
            </div>
        </div>

        <script>
            let cart = [];
            let total = 0;

            function addToCart(item, price) {
                cart.push({ item, price });
                total += price;
                updateCart();
            }

            function updateCart() {
                const cartItems = document.getElementById('cart-items');
                cartItems.innerHTML = '';
                cart.forEach((cartItem, index) => {
                    const li = document.createElement('li');
                    li.textContent = `${cartItem.item} - $${cartItem.price.toFixed(2)}`;
                    cartItems.appendChild(li);
                });
                document.getElementById('cart-total').textContent = total.toFixed(2);
            }

            function checkout() {
                alert(`Thank you for your purchase! Total: $${total.toFixed(2)}`);
                cart = [];
                total = 0;
                updateCart();
            }
        </script>
    </body>
    </html>
    ```

## Usage

- **View Items**: Browse the list of available items.
- **Add to Cart**: Click the "Add to Cart" button next to an item to add it to your shopping cart.
- **View Cart**: The shopping cart section displays all items added to the cart along with the total price.
- **Checkout**: Click the "Checkout" button to simulate a purchase and clear the cart.

## Contributing

If you would like to contribute to this project, please fork the repository and submit a pull request with your changes.

## Acknowledgements

This project is a simple demonstration of a web-based shopping interface using basic web technologies.
