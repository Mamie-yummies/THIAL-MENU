# THIAL-MENU
Menu
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Thilal - Menu Digital</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #7B1FA2;
            --primary-light: #9C27B0;
            --primary-dark: #4A148C;
            --accent: #E1BEE7;
            --white: #ffffff;
            --gray: #f5f5f5;
            --text: #333333;
            --success: #4CAF50;
            --warning: #FF9800;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            min-height: 100vh;
        }

        .header {
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-dark) 100%);
            color: white;
            padding: 1rem;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 4px 20px rgba(0,0,0,0.1);
        }

        .header-content {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .logo svg {
            height: 60px;
            width: auto;
        }

        .logo-text h1 {
            font-size: 1.8rem;
            font-weight: 700;
            letter-spacing: 2px;
        }

        .logo-text p {
            font-size: 0.9rem;
            opacity: 0.9;
        }

        .cart-icon {
            position: relative;
            cursor: pointer;
            padding: 10px;
            background: rgba(255,255,255,0.2);
            border-radius: 50%;
            transition: all 0.3s;
        }

        .cart-icon:hover {
            background: rgba(255,255,255,0.3);
            transform: scale(1.1);
        }

        .cart-count {
            position: absolute;
            top: -5px;
            right: -5px;
            background: #ff4081;
            color: white;
            border-radius: 50%;
            width: 24px;
            height: 24px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.8rem;
            font-weight: bold;
        }

        .nav-categories {
            position: fixed;
            top: 90px;
            left: 0;
            right: 0;
            background: white;
            padding: 1rem;
            z-index: 999;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            overflow-x: auto;
            white-space: nowrap;
        }

        .nav-categories::-webkit-scrollbar {
            display: none;
        }

        .category-btn {
            display: inline-block;
            padding: 0.6rem 1.2rem;
            margin: 0 0.5rem;
            background: var(--gray);
            border: none;
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: 500;
            color: var(--text);
        }

        .category-btn.active, .category-btn:hover {
            background: var(--primary);
            color: white;
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(123, 31, 162, 0.3);
        }

        .main-content {
            margin-top: 160px;
            padding: 2rem 1rem;
            max-width: 1200px;
            margin-left: auto;
            margin-right: auto;
        }

        .section-title {
            font-size: 2rem;
            color: var(--primary-dark);
            margin: 2rem 0 1rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .section-title::after {
            content: '';
            flex: 1;
            height: 2px;
            background: linear-gradient(to right, var(--primary), transparent);
            margin-left: 10px;
        }

        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .menu-item {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            position: relative;
        }

        .menu-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
        }

        .item-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
            background: linear-gradient(45deg, var(--accent), var(--primary-light));
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
            position: relative;
        }

        .item-badge {
            position: absolute;
            top: 10px;
            right: 10px;
            background: #ff4081;
            color: white;
            padding: 5px 10px;
            border-radius: 15px;
            font-size: 0.8rem;
            font-weight: bold;
        }

        .item-content {
            padding: 1.5rem;
        }

        .item-header {
            display: flex;
            justify-content: space-between;
            align-items: start;
            margin-bottom: 0.5rem;
        }

        .item-title {
            font-size: 1.2rem;
            font-weight: 600;
            color: var(--text);
            flex: 1;
        }

        .item-price {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--primary);
        }

        .item-description {
            color: #666;
            font-size: 0.9rem;
            margin-bottom: 1rem;
            line-height: 1.4;
        }

        .add-to-cart {
            width: 100%;
            padding: 0.8rem;
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-dark) 100%);
            color: white;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 600;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .add-to-cart:hover {
            transform: scale(1.02);
            box-shadow: 0 5px 15px rgba(123, 31, 162, 0.4);
        }

        .add-to-cart.added {
            background: var(--success);
        }

        .cart-sidebar {
            position: fixed;
            right: -400px;
            top: 0;
            width: 400px;
            height: 100vh;
            background: white;
            box-shadow: -5px 0 30px rgba(0,0,0,0.2);
            z-index: 2000;
            transition: right 0.3s ease;
            display: flex;
            flex-direction: column;
        }

        .cart-sidebar.open {
            right: 0;
        }

        .cart-header {
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-dark) 100%);
            color: white;
            padding: 1.5rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .close-cart {
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }

        .cart-items {
            flex: 1;
            overflow-y: auto;
            padding: 1rem;
        }

        .cart-item {
            display: flex;
            gap: 1rem;
            padding: 1rem;
            background: var(--gray);
            border-radius: 10px;
            margin-bottom: 1rem;
            align-items: center;
        }

        .cart-item-image {
            width: 60px;
            height: 60px;
            background: linear-gradient(45deg, var(--accent), var(--primary-light));
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.5rem;
        }

        .cart-item-details {
            flex: 1;
        }

        .cart-item-title {
            font-weight: 600;
            margin-bottom: 0.2rem;
        }

        .cart-item-price {
            color: var(--primary);
            font-weight: 700;
        }

        .quantity-controls {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-top: 0.5rem;
        }

        .qty-btn {
            width: 28px;
            height: 28px;
            border-radius: 50%;
            border: none;
            background: var(--primary);
            color: white;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .remove-item {
            color: #f44336;
            cursor: pointer;
            padding: 5px;
        }

        .cart-footer {
            padding: 1.5rem;
            border-top: 2px solid var(--gray);
            background: white;
        }

        .cart-total {
            display: flex;
            justify-content: space-between;
            font-size: 1.3rem;
            font-weight: 700;
            margin-bottom: 1rem;
            color: var(--primary-dark);
        }

        .checkout-btn {
            width: 100%;
            padding: 1rem;
            background: linear-gradient(135deg, var(--success) 0%, #2E7D32 100%);
            color: white;
            border: none;
            border-radius: 10px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
        }

        .checkout-btn:hover {
            transform: scale(1.02);
            box-shadow: 0 5px 15px rgba(76, 175, 80, 0.4);
        }

        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.5);
            z-index: 1500;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s;
        }

        .overlay.active {
            opacity: 1;
            visibility: visible;
        }

        .order-type-container {
            display: flex;
            gap: 1rem;
            margin-bottom: 1.5rem;
        }

        .order-type-btn {
            flex: 1;
            padding: 1rem;
            border: 2px solid #ddd;
            background: white;
            border-radius: 15px;
            cursor: pointer;
            transition: all 0.3s;
            text-align: center;
        }

        .order-type-btn i {
            font-size: 2rem;
            margin-bottom: 0.5rem;
            color: var(--primary);
        }

        .order-type-btn.active {
            border-color: var(--primary);
            background: var(--accent);
        }

        .order-type-btn:hover {
            border-color: var(--primary-light);
        }

        .modal {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%) scale(0.8);
            background: white;
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            z-index: 3000;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s;
            max-width: 500px;
            width: 90%;
            max-height: 90vh;
            overflow-y: auto;
        }

        .modal.active {
            opacity: 1;
            visibility: visible;
            transform: translate(-50%, -50%) scale(1);
        }

        .modal-header {
            text-align: center;
            margin-bottom: 1.5rem;
        }

        .modal-header h2 {
            color: var(--primary-dark);
            margin-bottom: 0.5rem;
        }

        .form-group {
            margin-bottom: 1rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--text);
            font-weight: 500;
        }

        .form-group input, .form-group textarea, .form-group select {
            width: 100%;
            padding: 0.8rem;
            border: 2px solid #ddd;
            border-radius: 10px;
            font-family: inherit;
            transition: border-color 0.3s;
            font-size: 1rem;
        }

        .form-group input:focus, .form-group textarea:focus, .form-group select:focus {
            outline: none;
            border-color: var(--primary);
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1rem;
        }

        .modal-buttons {
            display: flex;
            gap: 1rem;
            margin-top: 1.5rem;
        }

        .btn {
            flex: 1;
            padding: 0.8rem;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
        }

        .btn-primary {
            background: var(--primary);
            color: white;
        }

        .btn-secondary {
            background: var(--gray);
            color: var(--text);
        }

        .btn:hover {
            transform: scale(1.02);
        }

        .success-message {
            position: fixed;
            top: 100px;
            right: -400px;
            background: var(--success);
            color: white;
            padding: 1rem 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.2);
            z-index: 4000;
            transition: right 0.3s;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .success-message.show {
            right: 20px;
        }

        .info-banner {
            background: linear-gradient(135deg, var(--warning) 0%, #F57C00 100%);
            color: white;
            padding: 0.8rem;
            text-align: center;
            font-size: 0.9rem;
            margin-bottom: 1rem;
            border-radius: 10px;
        }

        @media (max-width: 768px) {
            .cart-sidebar {
                width: 100%;
                right: -100%;
            }
            
            .menu-grid {
                grid-template-columns: 1fr;
            }
            
            .logo svg {
                height: 40px;
            }
            
            .logo-text h1 {
                font-size: 1.2rem;
            }

            .form-row {
                grid-template-columns: 1fr;
            }

            .order-type-container {
                flex-direction: column;
            }
        }

        .empty-cart {
            text-align: center;
            padding: 3rem 1rem;
            color: #999;
        }

        .empty-cart i {
            font-size: 4rem;
            margin-bottom: 1rem;
            color: #ddd;
        }

        .hidden {
            display: none !important;
        }

        .table-input {
            font-size: 1.2rem;
            text-align: center;
            font-weight: bold;
            border: 3px solid var(--primary) !important;
        }
    </style>
</head>
<body>

    <header class="header">
        <div class="header-content">
            <div class="logo">
                <svg width="60" height="60" viewBox="0 0 200 200" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M100 180C144.183 180 180 144.183 180 100C180 55.8172 144.183 20 100 20C55.8172 20 20 55.8172 20 100C20 144.183 55.8172 180 100 180Z" stroke="white" stroke-width="8" fill="none"/>
                    <path d="M60 80C60 60 75 45 95 45C115 45 130 60 130 80" stroke="white" stroke-width="6" fill="none" stroke-linecap="round"/>
                    <path d="M50 85C50 65 70 50 90 50C110 50 125 65 125 85L120 95C120 75 105 60 85 60C65 60 55 75 55 95L50 85Z" fill="white"/>
                    <text x="100" y="145" text-anchor="middle" fill="white" font-family="Arial" font-size="36" font-weight="bold" font-style="italic">Thilal</text>
                    <line x1="115" y1="110" x2="115" y2="140" stroke="white" stroke-width="4" stroke-linecap="round"/>
                    <path d="M115 110L125 110L125 115L120 120L125 125L120 130" stroke="white" stroke-width="3" fill="none"/>
                </svg>
                <div class="logo-text">
                    <h1>THILAL</h1>
                    <p>Restaurant & Fast Food</p>
                </div>
            </div>
            <div class="cart-icon" onclick="toggleCart()">
                <i class="fas fa-shopping-cart fa-lg"></i>
                <span class="cart-count" id="cartCount">0</span>
            </div>
        </div>
    </header>

    <nav class="nav-categories">
        <button class="category-btn active" onclick="filterCategory('all', this)">Tout</button>
        <button class="category-btn" onclick="filterCategory('viennoiseries', this)">Viennoiseries</button>
        <button class="category-btn" onclick="filterCategory('fastfood', this)">Fast Food</button>
        <button class="category-btn" onclick="filterCategory('gastronomique', this)">Gastronomique</button>
        <button class="category-btn" onclick="filterCategory('pizzas', this)">Pizzas</button>
        <button class="category-btn" onclick="filterCategory('africain', this)">Plats Africains</button>
        <button class="category-btn" onclick="filterCategory('accompagnement', this)">Accompagnements</button>
    </nav>

    <main class="main-content" id="menuContainer">
    </main>

    <div class="overlay" onclick="toggleCart()"></div>
    <aside class="cart-sidebar" id="cartSidebar">
        <div class="cart-header">
            <h3><i class="fas fa-shopping-cart"></i> Votre Commande</h3>
            <button class="close-cart" onclick="toggleCart()">
                <i class="fas fa-times"></i>
            </button>
        </div>
        <div class="cart-items" id="cartItems">
            <div class="empty-cart">
                <i class="fas fa-shopping-basket"></i>
                <p>Votre panier est vide</p>
            </div>
        </div>
        <div class="cart-footer">
            <div class="cart-total">
                <span>Total:</span>
                <span id="cartTotal">0 FCFA</span>
            </div>
            <button class="checkout-btn" onclick="openOrderModal()">
                <i class="fas fa-check-circle"></i> Commander
            </button>
        </div>
    </aside>

    <div class="overlay" id="modalOverlay" onclick="closeOrderModal()"></div>
    <div class="modal" id="orderModal">
        <div class="modal-header">
            <h2><i class="fas fa-clipboard-list"></i> Finaliser la commande</h2>
            <p>Choisissez votre mode de commande</p>
        </div>

        <div class="info-banner">
            <i class="fas fa-info-circle"></i> Commande envoyée au +223 66 72 72 93
        </div>

        <div class="order-type-container">
            <div class="order-type-btn active" onclick="selectOrderType('surplace', this)">
                <i class="fas fa-utensils"></i>
                <div>Sur place</div>
                <small>Au restaurant</small>
            </div>
            <div class="order-type-btn" onclick="selectOrderType('livraison', this)">
                <i class="fas fa-motorcycle"></i>
                <div>Livraison</div>
                <small>A domicile</small>
            </div>
        </div>

        <form id="orderForm" onsubmit="submitOrder(event)">
            <div id="surplaceFields">
                <div class="form-group">
                    <label><i class="fas fa-chair"></i> Numéro de table *</label>
                    <input type="text" id="tableNumber" class="table-input" required placeholder="Ex: 5, A12, Terrasse 3...">
                </div>
            </div>

            <div id="livraisonFields" class="hidden">
                <div class="form-row">
                    <div class="form-group">
                        <label><i class="fas fa-user"></i> Nom complet *</label>
                        <input type="text" id="clientName" placeholder="Votre nom">
                    </div>
                    <div class="form-group">
                        <label><i class="fas fa-phone"></i> Téléphone *</label>
                        <input type="tel" id="clientPhone" placeholder="07 XX XX XX XX">
                    </div>
                </div>
                <div class="form-group">
                    <label><i class="fas fa-map-marker-alt"></i> Quartier *</label>
                    <input type="text" id="quartier" placeholder="Ex: Cocody, Marcory, Plateau...">
                </div>
                <div class="form-group">
                    <label><i class="fas fa-home"></i> Adresse détaillée *</label>
                    <textarea id="adresse" rows="2" placeholder="Rue, lot, bâtiment, étage..."></textarea>
                </div>
                <div class="form-group">
                    <label><i class="fas fa-map-pin"></i> Point de repère</label>
                    <input type="text" id="repere" placeholder="Ex: Près de la pharmacie...">
                </div>
            </div>

            <div class="form-group">
                <label><i class="fas fa-comment"></i> Instructions spéciales (optionnel)</label>
                <textarea id="instructions" rows="2" placeholder="Ex: Sans piment, sauce à part..."></textarea>
            </div>

            <div class="modal-buttons">
                <button type="button" class="btn btn-secondary" onclick="closeOrderModal()">
                    <i class="fas fa-times"></i> Annuler
                </button>
                <button type="submit" class="btn btn-primary">
                    <i class="fab fa-whatsapp"></i> Envoyer sur WhatsApp
                </button>
            </div>
        </form>
    </div>

    <div class="success-message" id="successMessage">
        <i class="fas fa-check-circle"></i>
        <span id="successText">Article ajouté au panier !</span>
    </div>

    <script>
        const WHATSAPP_NUMBER = '22366727293';

        const menuData = {
            viennoiseries: [
                { id: 1, name: "Croissant", price: 500, icon: "🥐", desc: "Croissant au beurre frais" },
                { id: 2, name: "Pâté", price: 500, icon: "🥧", desc: "Pâté chaud maison" },
                { id: 3, name: "Pain au raisin", price: 500, icon: "🍇", desc: "Pain aux raisins secs" },
                { id: 4, name: "Pain au chocolat", price: 500, icon: "🍫", desc: "Pain au chocolat noir" },
                { id: 5, name: "Pain au lait", price: 500, icon: "🥛", desc: "Pain moelleux au lait" },
                { id: 6, name: "Panini", price: 500, icon: "🥪", desc: "Panini grillé" }
            ],
            fastfood: [
                { id: 7, name: "Nems", price: 1000, icon: "🥢", desc: "6 nems croustillants" },
                { id: 8, name: "Tacos viande", price: 2500, icon: "🌮", desc: "Tacos avec viande hachée" },
                { id: 9, name: "Tacos poulet", price: 3500, icon: "🌮", desc: "Tacos avec poulet pané" },
                { id: 10, name: "Tacos THILAL", price: 4500, icon: "🌮", desc: "Tacos spécial maison", badge: "SPECIAL" },
                { id: 11, name: "Chawarma viande", price: 1500, icon: "🥙", desc: "Chawarma viande hachée" },
                { id: 12, name: "Chawarma poulet", price: 2000, icon: "🥙", desc: "Chawarma poulet grillé" },
                { id: 13, name: "Chawarma THILAL", price: 3500, icon: "🥙", desc: "Chawarma spécial maison", badge: "SPECIAL" },
                { id: 14, name: "Sandwich viande", price: 1000, icon: "🥪", desc: "Sandwich viande hachée" },
                { id: 15, name: "Sandwich poulet", price: 1500, icon: "🥪", desc: "Sandwich poulet grillé" },
                { id: 16, name: "Hamburger", price: 1500, icon: "🍔", desc: "Burger classique" },
                { id: 17, name: "Chicken burger", price: 2000, icon: "🍔", desc: "Burger au poulet croustillant" },
                { id: 18, name: "THILAL burger", price: 3500, icon: "🍔", desc: "Burger signature maison", badge: "SIGNATURE" },
                { id: 19, name: "KFC", price: 4000, icon: "🍗", desc: "Bucket poulet pané" }
            ],
            gastronomique: [
                { id: 20, name: "½ Poulet", price: 2500, icon: "🍗", desc: "Demi poulet rôti" },
                { id: 21, name: "Poulet entier", price: 5000, icon: "🍗", desc: "Poulet rôti entier" },
                { id: 22, name: "Carpe grillé", price: 4000, icon: "🐟", desc: "Carpe fraîche grillée" },
                { id: 23, name: "Filet de bœuf", price: 6000, icon: "🥩", desc: "Filet de bœuf sauce au choix" },
                { id: 24, name: "Spaghetti bolognaise", price: 5000, icon: "🍝", desc: "Pâtes sauce bolognaise" },
                { id: 25, name: "Kedjenou au poulet", price: 5000, icon: "🍲", desc: "Kedjenou traditionnel" },
                { id: 26, name: "Brochette de bœuf", price: 4000, icon: "🍢", desc: "Brochette de bœuf mariné" },
                { id: 27, name: "Brochette de poulet", price: 5000, icon: "🍢", desc: "Brochette de poulet mariné" }
            ],
            pizzas: [
                { id: 28, name: "Orientale", price: 5000, icon: "🍕", desc: "Pizza sauce tomate, merguez" },
                { id: 29, name: "Margherita", price: 5000, icon: "🍕", desc: "Pizza tomate, mozzarella" },
                { id: 30, name: "Végétarien", price: 6000, icon: "🍕", desc: "Pizza légumes frais" },
                { id: 31, name: "THILAL", price: 6500, icon: "🍕", desc: "Pizza spéciale maison", badge: "SPECIAL" }
            ],
            africain: [
                { id: 32, name: "Sauce tomate", price: 2000, icon: "🍅", desc: "Sauce tomate avec viande" },
                { id: 33, name: "Sauce yassa", price: 2000, icon: "🧅", desc: "Yassa au poulet ou poisson" },
                { id: 34, name: "Sauce arachide", price: 2000, icon: "🥜", desc: "Sauce graine avec viande" },
                { id: 35, name: "Sauce Fakoye", price: 2000, icon: "🌿", desc: "Sauce aux feuilles de fakoye" },
                { id: 36, name: "Sauce gombo", price: 2000, icon: "🥬", desc: "Sauce gombo avec viande" },
                { id: 37, name: "Riz au gras", price: 2000, icon: "🍚", desc: "Riz gras avec légumes" }
            ],
            accompagnement: [
                { id: 38, name: "Riz blanc", price: 500, icon: "🍚", desc: "Riz blanc nature" },
                { id: 39, name: "Frites", price: 500, icon: "🍟", desc: "Frites de pommes de terre" },
                { id: 40, name: "Aloco", price: 500, icon: "🍌", desc: "Banane plantain frite" },
                { id: 41, name: "Pomme sauté", price: 500, icon: "🥔", desc: "Pommes de terre sautées" },
                { id: 42, name: "Légumes", price: 500, icon: "🥗", desc: "Légumes sautés" }
            ]
        };

        let cart = [];
        let currentCategory = 'all';
        let orderType = 'surplace';

        document.addEventListener('DOMContentLoaded', () => {
            renderMenu();
        });

        function renderMenu() {
            const container = document.getElementById('menuContainer');
            container.innerHTML = '';

            const categories = currentCategory === 'all' 
                ? Object.keys(menuData) 
                : [currentCategory];

            categories.forEach(cat => {
                const items = menuData[cat];
                if (!items) return;

                const sectionTitle = {
                    viennoiseries: '🥐 Viennoiseries',
                    fastfood: '🍔 Fast Food',
                    gastronomique: '🍽️ Plats Gastronomiques',
                    pizzas: '🍕 Pizzas',
                    africain: '🍲 Plats Africains',
                    accompagnement: '🥗 Accompagnements'
                }[cat];

                const section = document.createElement('div');
                section.innerHTML = `
                    <h2 class="section-title">${sectionTitle}</h2>
                    <div class="menu-grid">
                        ${items.map(item => `
                            <div class="menu-item" data-id="${item.id}">
                                <div class="item-image">
                                    ${item.badge ? `<span class="item-badge">${item.badge}</span>` : ''}
                                    <span style="font-size: 4rem;">${item.icon}</span>
                                </div>
                                <div class="item-content">
                                    <div class="item-header">
                                        <h3 class="item-title">${item.name}</h3>
                                        <span class="item-price">${item.price.toLocaleString()} FCFA</span>
                                    </div>
                                    <p class="item-description">${item.desc}</p>
                                    <button class="add-to-cart" onclick="addToCart(${item.id}, '${cat}')">
                                        <i class="fas fa-plus"></i> Ajouter
                                    </button>
                                </div>
                            </div>
                        `).join('')}
                    </div>
                `;
                container.appendChild(section);
            });
        }

        function filterCategory(category, btn) {
            currentCategory = category;
            
            document.querySelectorAll('.category-btn').forEach(b => b.classList.remove('active'));
            btn.classList.add('active');
            
            renderMenu();
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function addToCart(itemId, category) {
            const item = menuData[category].find(i => i.id === itemId);
            const existingItem = cart.find(i => i.id === itemId);

            if (existingItem) {
                existingItem.quantity++;
            } else {
                cart.push({ ...item, quantity: 1, category });
            }

            updateCart();
            showSuccess(`"${item.name}" ajouté au panier !`);
            
            const btn = event.target.closest('.add-to-cart');
            btn.innerHTML = '<i class="fas fa-check"></i> Ajouté !';
            btn.classList.add('added');
            setTimeout(() => {
                btn.innerHTML = '<i class="fas fa-plus"></i> Ajouter';
                btn.classList.remove('added');
            }, 1500);
        }

        function updateCart() {
            const cartCount = document.getElementById('cartCount');
            const cartItems = document.getElementById('cartItems');
            const cartTotal = document.getElementById('cartTotal');

            const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
            const totalPrice = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);

            cartCount.textContent = totalItems;
            cartTotal.textContent = totalPrice.toLocaleString() + ' FCFA';

            if (cart.length === 0) {
                cartItems.innerHTML = `
                    <div class="empty-cart">
                        <i class="fas fa-shopping-basket"></i>
                        <p>Votre panier est vide</p>
                    </div>
                `;
            } else {
                cartItems.innerHTML = cart.map(item => `
                    <div class="cart-item">
                        <div class="cart-item-image">
                            <span style="font-size: 1.5rem;">${item.icon}</span>
                        </div>
                        <div class="cart-item-details">
                            <div class="cart-item-title">${item.name}</div>
                            <div class="cart-item-price">${item.price.toLocaleString()} FCFA</div>
                            <div class="quantity-controls">
                                <button class="qty-btn" onclick="updateQuantity(${item.id}, -1)">-</button>
                                <span>${item.quantity}</span>
                                <button class="qty-btn" onclick="updateQuantity(${item.id}, 1)">+</button>
                            </div>
                        </div>
                        <div class="remove-item" onclick="removeFromCart(${item.id})">
                            <i class="fas fa-trash"></i>
                        </div>
                    </div>
                `).join('');
            }
        }

        function updateQuantity(itemId, change) {
            const item = cart.find(i => i.id === itemId);
            if (item) {
                item.quantity += change;
                if (item.quantity <= 0) {
                    removeFromCart(itemId);
                } else {
                    updateCart();
                }
            }
        }

        function removeFromCart(itemId) {
            cart = cart.filter(i => i.id !== itemId);
            updateCart();
            showSuccess('Article retiré du panier');
        }

        function toggleCart() {
            document.getElementById('cartSidebar').classList.toggle('open');
            document.querySelector('.overlay:not(#modalOverlay)').classList.toggle('active');
        }

        function selectOrderType(type, btn) {
            orderType = type;
            
            document.querySelectorAll('.order-type-btn').forEach(b => b.classList.remove('active'));
            btn.classList.add('active');

            const surplaceFields = document.getElementById('surplaceFields');
            const livraisonFields = document.getElementById('livraisonFields');
            const tableInput = document.getElementById('tableNumber');
            const nameInput = document.getElementById('clientName');
            const phoneInput = document.getElementById('clientPhone');
            const quartierInput = document.getElementById('quartier');
            const adresseInput = document.getElementById('adresse');

            if (type === 'surplace') {
                surplaceFields.classList.remove('hidden');
                livraisonFields.classList.add('hidden');
                
                tableInput.required = true;
                nameInput.required = false;
                phoneInput.required = false;
                quartierInput.required = false;
                adresseInput.required = false;
            } else {
                surplaceFields.classList.add('hidden');
                livraisonFields.classList.remove('hidden');
                
                tableInput.required = false;
                nameInput.required = true;
                phoneInput.required = true;
                quartierInput.required = true;
                adresseInput.required = true;
            }
        }

        function openOrderModal() {
            if (cart.length === 0) {
                showSuccess('Votre panier est vide !');
                return;
            }
            document.getElementById('orderModal').classList.add('active');
            document.getElementById('modalOverlay').classList.add('active');
        }

        function closeOrderModal() {
            document.getElementById('orderModal').classList.remove('active');
            document.getElementById('modalOverlay').classList.remove('active');
        }

        function submitOrder(e) {
            e.preventDefault();
            
            const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            const orderDetails = cart.map(item => 
                `• ${item.name} x${item.quantity} = ${(item.price * item.quantity).toLocaleString()} FCFA`
            ).join('\n');

            const instructions = document.getElementById('instructions').value || 'Aucune';

            let message = '';

            if (orderType === 'surplace') {
                const table = document.getElementById('tableNumber').value;
                
                message = `*🍽️ COMMANDE SUR PLACE - TABLE ${table}*%0A%0A` +
                    `*🛒 Détails:*%0A${orderDetails.replace(/\n/g, '%0A')}%0A%0A` +
                    `*💰 Total:* ${total.toLocaleString()} FCFA%0A` +
                    `*📝 Instructions:* ${instructions}%0A%0A` +
                    `---%0A📍 Client au restaurant`;
            } else {
                const name = document.getElementById('clientName').value;
                const phone = document.getElementById('clientPhone').value;
                const quartier = document.getElementById('quartier').value;
                const adresse = document.getElementById('adresse').value;
                const repere = document.getElementById('repere').value || 'Non précisé';

                message = `*🛵 COMMANDE LIVRAISON*%0A%0A` +
                    `*👤 Client:* ${name}%0A` +
                    `*📞 Téléphone:* ${phone}%0A%0A` +
                    `*📍 Adresse:*%0A` +
                    `Quartier: ${quartier}%0A` +
                    `Adresse: ${adresse}%0A` +
                    `Repère: ${repere}%0A%0A` +
                    `*🛒 Commande:*%0A${orderDetails.replace(/\n/g, '%0A')}%0A%0A` +
                    `*💰 Total:* ${total.toLocaleString()} FCFA%0A` +
                    `*📝 Instructions:* ${instructions}%0A%0A` +
                    `---%0A🚀 Livraison demandée`;
            }

            window.open(`https://wa.me/${WHATSAPP_NUMBER}?text=${message}`, '_blank');
            
            cart = [];
            updateCart();
            closeOrderModal();
            toggleCart();
            document.getElementById('orderForm').reset();
            showSuccess('Commande envoyée avec succès !');
        }

        function showSuccess(text) {
            const msg = document.getElementById('successMessage');
            document.getElementById('successText').textContent = text;
            msg.classList.add('show');
            setTimeout(() => msg.classList.remove('show'), 3000);
        }
    </script>
</body>
</html>
