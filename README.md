
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Our Menu</title>
    <style>
        body { font-family: 'Segoe UI', system-ui, -apple-system, sans-serif; background: #f9f9f9; padding: 20px; color: #2d3748; display: flex; justify-content: center; margin: 0; }
        .container { width: 100%; max-width: 600px; }
        h2 { color: #1a202c; text-align: center; }
        .category-title { font-size: 18px; font-weight: 600; color: #2b6cb0; margin: 25px 0 12px 0; border-bottom: 2px solid #bee3f8; padding-bottom: 4px; scroll-margin-top: 20px; }
        
        /* Fixed Corner Category Dropdown */
        .category-dropdown-container { position: fixed; top: 15px; right: 15px; z-index: 1000; }
        .category-dropdown { background: white; border: 1px solid #cbd5e0; padding: 8px 12px; border-radius: 8px; font-size: 13px; font-weight: 600; color: #2b6cb0; box-shadow: 0 4px 12px rgba(0,0,0,0.08); cursor: pointer; outline: none; }
        .category-dropdown:hover { background: #f7fafc; }

        /* Grid layout to nicely display items with top images */
        .menu-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(260px, 1fr)); gap: 15px; }
        .menu-card { background: white; border-radius: 12px; overflow: hidden; box-shadow: 0 2px 8px rgba(0,0,0,0.04); border: 1px solid #edf2f7; display: flex; flex-direction: column; text-align: center; padding-bottom: 15px; }
        
        .item-img { width: 100%; height: 160px; object-fit: cover; background: #edf2f7; }
        .item-content { padding: 12px 15px; display: flex; flex-direction: column; align-items: center; flex-grow: 1; justify-content: space-between; gap: 10px; }
        
        .item-info { font-size: 16px; font-weight: 600; color: #2d3748; }
        .item-price { color: #718096; font-size: 14px; margin-top: 2px; }
        
        .btn-add { background: #2ed573; color: white; border: none; padding: 8px 20px; border-radius: 6px; font-weight: 600; cursor: pointer; font-size: 14px; width: 100%; }
        .btn-add:hover { background: #26af5f; }
        
        .qty-control { display: flex; align-items: center; justify-content: center; background: #edf2f7; border-radius: 6px; overflow: hidden; border: 1px solid #cbd5e0; width: 100%; }
        .qty-btn { background: #e2e8f0; border: none; padding: 6px 16px; font-weight: bold; cursor: pointer; color: #2d3748; font-size: 15px; }
        .qty-btn:hover { background: #cbd5e0; }
        .qty-display { padding: 0 16px; font-weight: 600; font-size: 14px; color: #1a202c; }

        .checkout-bar { position: fixed; bottom: 0; left: 0; width: 100%; background: white; padding: 15px; box-shadow: 0 -4px 12px rgba(0,0,0,0.05); text-align: center; box-sizing: border-box; z-index: 999; }
        .btn-checkout { background: #3182ce; color: white; border: none; padding: 12px 20px; border-radius: 8px; font-weight: 600; font-size: 16px; cursor: pointer; width: 100%; max-width: 560px; transition: background 0.2s; }
        .btn-checkout:hover { background: #2b6cb0; }
    </style>
</head>
<body>

  <!-- Fixed Corner Category Dropdown -->
  <div class="category-dropdown-container">
      <select id="cornerCategoryDropdown" class="category-dropdown" onchange="scrollToCategory(this.value)">
          <option value="">Menu 📖</option>
      </select>
  </div>

  <div style="text-align: center; width: 100%;">
      <img src="https://i.postimg.cc/SsSZBQ9q/1000037254-removebg-preview.png" alt="Description" style="width: 300px;">
  </div>
  <br>
  <h1>Contact Us On: 9741348438</h1>
  
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Google Map Button</title>
    <!-- Include Google Fonts (Roboto) and FontAwesome for the pin icon -->
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
  <style>
        body {
            font-family: 'Roboto', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f8f9fa;
        }

        /* Google Maps Button Styling */
        .gmap-btn {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            background-color: #ffffff;
            color: #3c4043;
            font-family: 'Roboto', sans-serif;
            font-size: 14px;
            font-weight: 500;
            padding: 10px 18px;
            border: 1px solid #dadce0;
            border-radius: 8px;
            cursor: pointer;
            box-shadow: 0 1px 3px rgba(60, 64, 67, 0.3);
            text-decoration: none;
            transition: all 0.2s ease-in-out;
        }

        /* Map Pin Icon styling matching Google Red */
        .gmap-btn i {
            color: #ea4335;
            font-size: 16px;
        }

        /* Hover effect */
        .gmap-btn:hover {
            background-color: #f8f9fa;
            box-shadow: 0 2px 6px rgba(60, 64, 67, 0.3);
            border-color: #d2d3d6;
        }

        /* Active / Click effect */
        .gmap-btn:active {
            background-color: #f1f3f4;
            box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3);
        }
    </style>
</head>
<body>
<!-- Replace 'Times+Square+New+York' with your desired location or latitude/longitude -->
    <a href="https://www.google.com/maps/search/?api=1&query=Times+Square+New+York" 
       target="_blank" 
       rel="noopener noreferrer" 
       class="gmap-btn">
        <i class="fa-solid fa-location-dot"></i>
        <span>View on Google Maps</span>
    </a>

</body>


  
  
  
  <br><br>
  
  <div class="container" style="padding-bottom: 90px;">
        <h2>🍽️ Restaurant Menu</h2>
        <div id="customerMenuDisplay">Loading live menu...</div>
  </div>

  <div class="checkout-bar">
       <button class="btn-checkout" onclick="goToCheckout()" id="checkoutBtnText">Proceed to Checkout 🛒 (0 items)</button>
  </div>

<script>
    const FIREBASE_URL = "https://test-d34cf-default-rtdb.europe-west1.firebasedatabase.app";
    
    const phone = localStorage.getItem('activeCustomerPhone') || 'Customer_' + Math.floor(Math.random() * 9000 + 1000);
    localStorage.setItem('activeCustomerPhone', phone);
    let cartKey = 'cart_' + phone;
    let cart = JSON.parse(localStorage.getItem(cartKey) || '{}');
    let currentMenuData = { categories: [] };

    async function loadCustomerMenu() {
        const container = document.getElementById('customerMenuDisplay');

        try {
            let res = await fetch(`${FIREBASE_URL}/menu.json`);
            let data = await res.json();
            if (data && data.categories) {
                currentMenuData = data;
            }
        } catch (e) {
            container.innerHTML = '<p style="text-align:center; color:#e53e3e;">Failed to load menu. Check your internet connection.</p>';
            return;
        }

        if (!currentMenuData.categories || currentMenuData.categories.length === 0) {
            container.innerHTML = '<p style="text-align:center; color:#718096; margin-top:40px;">Menu is currently being updated. Please check back soon!</p>';
            return;
        }

        renderMenuUI();
        updateCategoryDropdown();
    }

    function updateCategoryDropdown() {
        const dropdown = document.getElementById('cornerCategoryDropdown');
        let optionsHtml = '<option value="">Menu 📖</option>';

        currentMenuData.categories.forEach((cat, index) => {
            optionsHtml += `<option value="cat_${index}">${cat.name}</option>`;
        });

        dropdown.innerHTML = optionsHtml;
    }

    function scrollToCategory(categoryElementId) {
        if (!categoryElementId) return;
        const targetElement = document.getElementById(categoryElementId);
        if (targetElement) {
            targetElement.scrollIntoView({ behavior: 'smooth', block: 'start' });
        }
        document.getElementById('cornerCategoryDropdown').value = "";
    }

    function renderMenuUI() {
        const container = document.getElementById('customerMenuDisplay');
        let html = '';

        currentMenuData.categories.forEach((cat, catIndex) => {
            html += `<div id="cat_${catIndex}" class="category-title">${cat.name}</div>`;

            if (!cat.items || cat.items.length === 0) {
                html += `<p style="font-size:13px; color:#a0aec0; margin: 5px 0;">No items available in this category.</p>`;
            } else {
                html += `<div class="menu-grid">`;
                cat.items.forEach((item, itemIndex) => {
                    let uniqueId = `${catIndex}_${itemIndex}`;
                    let qty = cart[uniqueId] ? cart[uniqueId].quantity : 0;

                    let actionHtml = '';
                    if (qty === 0) {
                        actionHtml = `<button class="btn-add" onclick="updateQty('${uniqueId}', '${item.name}', ${item.price}, 1)">Add +</button>`;
                    } else {
                        actionHtml = `
                            <div class="qty-control">
                                <button class="qty-btn" onclick="updateQty('${uniqueId}', '${item.name}', ${item.price}, -1)">-</button>
                                <span class="qty-display">${qty}</span>
                                <button class="qty-btn" onclick="updateQty('${uniqueId}', '${item.name}', ${item.price}, 1)">+</button>
                            </div>
                        `;
                    }

                    let imgHtml = item.image ? `<img src="${item.image}" alt="${item.name}" class="item-img">` : `<div class="item-img" style="display:flex; align-items:center; justify-content:center; color:#a0aec0; font-size:12px;">No Image</div>`;

                    html += `
                        <div class="menu-card">
                            ${imgHtml}
                            <div class="item-content">
                                <div>
                                    <div class="item-info">${item.name}</div>
                                    <div class="item-price">₹${item.price}</div>
                                </div>
                                <div style="width: 100%;">${actionHtml}</div>
                            </div>
                        </div>
                    `;
                });
                html += `</div>`;
            }
        });

        container.innerHTML = html;
        updateCartCount();
    }

    function updateQty(id, name, price, change) {
        if (!cart[id]) {
            cart[id] = { name: name, price: price, quantity: 0 };
        }
        cart[id].quantity += change;

        if (cart[id].quantity <= 0) {
            delete cart[id];
        }

        localStorage.setItem(cartKey, JSON.stringify(cart));
        renderMenuUI();
    }

    function updateCartCount() {
        let totalItems = 0;
        for (let id in cart) {
            totalItems += cart[id].quantity;
        }
        document.getElementById('checkoutBtnText').innerText = `Proceed to Checkout 🛒 (${totalItems} items)`;
    }

    function goToCheckout() {
        let totalItems = 0;
        for (let id in cart) {
            totalItems += cart[id].quantity;
        }
        if (totalItems === 0) {
            alert('Your cart is empty! Add some items before proceeding.');
            return;
        }
        window.location.href = 'https://kshitij-bhuwania.github.io/Checkout/';
    }

    // Auto-refresh every 3 seconds to stay synced with admin changes
    setInterval(() => {
        fetch(`${FIREBASE_URL}/menu.json`)
            .then(res => res.json())
            .then(data => {
                if (data && data.categories) {
                    currentMenuData = data;
                    renderMenuUI();
                    updateCategoryDropdown();
                }
            }).catch(() => {});
    }, 3000);

    loadCustomerMenu();
</script>
</body>
</html>
