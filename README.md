<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Our Menu</title>
    <style>
        body { font-family: 'Segoe UI', system-ui, -apple-system, sans-serif; background: #f4f6f9; padding: 20px; color: #2d3748; display: flex; justify-content: center; margin: 0; }
        .container { width: 100%; max-width: 600px; }
        h2 { color: #1a202c; text-align: center; }
        .category-title { font-size: 18px; font-weight: 600; color: #2b6cb0; margin: 20px 0 10px 0; border-bottom: 2px solid #bee3f8; padding-bottom: 4px; }
        .menu-card { background: white; padding: 15px; border-radius: 10px; box-shadow: 0 2px 8px rgba(0,0,0,0.03); border: 1px solid #edf2f7; margin-bottom: 10px; display: flex; justify-content: space-between; align-items: center; }
        .item-info { font-size: 15px; font-weight: 600; color: #2d3748; }
        .item-price { color: #718096; font-size: 14px; margin-top: 4px; }
        .btn-add { background: #2ed573; color: white; border: none; padding: 8px 14px; border-radius: 6px; font-weight: 600; cursor: pointer; font-size: 13px; }
        .btn-add:hover { background: #26af5f; }
        .checkout-bar { position: fixed; bottom: 0; left: 0; width: 100%; background: white; padding: 15px; box-shadow: 0 -4px 12px rgba(0,0,0,0.05); text-align: center; box-sizing: border-box; }
        .btn-checkout { background: #3182ce; color: white; border: none; padding: 12px 20px; border-radius: 8px; font-weight: 600; font-size: 16px; cursor: pointer; width: 100%; max-width: 560px; }
    </style>
</head>
<body>

 <div class="container" style="padding-bottom: 80px;">
        <h2>🍽️ Restaurant Menu</h2>
        <div id="customerMenuDisplay">Loading live menu...</div>
    </div>

 <div class="checkout-bar">
        <button class="btn-checkout" onclick="goToCheckout()">Proceed to Checkout 🛒</button>
    </div>

<script>
    const FIREBASE_URL = "https://test-d34cf-default-rtdb.europe-west1.firebasedatabase.app";
    
    const phone = localStorage.getItem('activeCustomerPhone') || 'Customer_' + Math.floor(Math.random() * 9000 + 1000);
    localStorage.setItem('activeCustomerPhone', phone);
    let cartKey = 'cart_' + phone;
    let cart = JSON.parse(localStorage.getItem(cartKey) || '{}');

    async function loadCustomerMenu() {
        const container = document.getElementById('customerMenuDisplay');
        let menu = { categories: [] };

        try {
            let res = await fetch(`${FIREBASE_URL}/menu.json`);
            let data = await res.json();
            if (data && data.categories) {
                menu = data;
            }
        } catch (e) {
            container.innerHTML = '<p style="text-align:center; color:#e53e3e;">Failed to load menu. Check your internet connection.</p>';
            return;
        }

        if (!menu.categories || menu.categories.length === 0) {
            container.innerHTML = '<p style="text-align:center; color:#718096; margin-top:40px;">Menu is currently being updated. Please check back soon!</p>';
            return;
        }

        let html = '';
        menu.categories.forEach((cat, catIndex) => {
            html += `<div class="category-title">${cat.name}</div>`;

            if (!cat.items || cat.items.length === 0) {
                html += `<p style="font-size:13px; color:#a0aec0; margin: 5px 0;">No items available in this category.</p>`;
            } else {
                cat.items.forEach((item, itemIndex) => {
                    let uniqueId = `${catIndex}_${itemIndex}`;
                    html += `
                        <div class="menu-card">
                            <div>
                                <div class="item-info">${item.name}</div>
                                <div class="item-price">₹${item.price}</div>
                            </div>
                            <button class="btn-add" onclick="addToCart('${uniqueId}', '${item.name}', ${item.price})">Add +</button>
                        </div>
                    `;
                });
            }
        });

        container.innerHTML = html;
    }

    function addToCart(id, name, price) {
        if (!cart[id]) {
            cart[id] = { name: name, price: price, quantity: 0 };
        }
        cart[id].quantity += 1;
        localStorage.setItem(cartKey, JSON.stringify(cart));
        alert(`${name} added to cart!`);
    }

    function goToCheckout() {
        window.location.href = 'checkout.html';
    }

    // Auto-refresh the menu every 3 seconds so changes made on the admin page instantly show up on customer phones
    setInterval(loadCustomerMenu, 3000);
    loadCustomerMenu();
</script>
</body>
</html>
