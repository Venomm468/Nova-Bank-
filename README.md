# Nova-Bank-
Banking Network 
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Nova Bank</title>

<style>
:root {
    --primary: #1a56db;
    --primary-dark: #1e429f;
    --primary-light: #e1effe;
    --success: #0e9f6e;
    --danger: #f05252;
    --warning: #faca15;
    --bg: #f3f4f6;
    --surface: #ffffff;
    --text: #111827;
    --text-secondary: #6b7280;
    --border: #e5e7eb;
    --shadow-sm: 0 1px 2px 0 rgba(0,0,0,0.05);
    --shadow: 0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -2px rgba(0,0,0,0.1);
    --shadow-lg: 0 10px 15px -3px rgba(0,0,0,0.1), 0 4px 6px -4px rgba(0,0,0,0.1);
    --radius: 16px;
    --radius-sm: 12px;
    --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
    -webkit-tap-highlight-color: transparent;
}

body {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    padding: 20px;
}

.phone {
    width: 375px;
    height: 812px;
    background: var(--bg);
    border-radius: 40px;
    overflow: hidden;
    position: relative;
    box-shadow: 0 25px 50px -12px rgba(0,0,0,0.25), 0 0 0 12px rgba(255,255,255,0.1);
}

.screen {
    height: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    padding-bottom: 90px;
    scrollbar-width: none;
}

.screen::-webkit-scrollbar { display: none; }

/* LOGIN SCREEN */
.login {
    background: var(--surface);
    padding: 0;
    display: flex;
    flex-direction: column;
}

.login-header {
    background: linear-gradient(135deg, var(--primary) 0%, #7c3aed 100%);
    padding: 60px 30px 80px;
    border-radius: 0 0 40px 40px;
    position: relative;
    overflow: hidden;
}

.login-header::before {
    content: '';
    position: absolute;
    top: -50%;
    right: -20%;
    width: 300px;
    height: 300px;
    background: rgba(255,255,255,0.1);
    border-radius: 50%;
}

.login-header::after {
    content: '';
    position: absolute;
    bottom: -30%;
    left: -10%;
    width: 200px;
    height: 200px;
    background: rgba(255,255,255,0.05);
    border-radius: 50%;
}

.login-header h1 {
    color: white;
    font-size: 36px;
    font-weight: 700;
    position: relative;
    z-index: 1;
}

.login-header p {
    color: rgba(255,255,255,0.8);
    margin-top: 8px;
    font-size: 16px;
    position: relative;
    z-index: 1;
}

.login-form {
    padding: 30px;
    margin-top: -40px;
    position: relative;
    z-index: 2;
}

.input-group {
    margin-bottom: 20px;
}

.input-group label {
    display: block;
    font-size: 14px;
    font-weight: 600;
    color: var(--text);
    margin-bottom: 8px;
}

.input-wrapper {
    position: relative;
}

.input-wrapper input {
    width: 100%;
    padding: 14px 16px;
    border: 2px solid var(--border);
    border-radius: var(--radius-sm);
    font-size: 15px;
    transition: var(--transition);
    background: var(--surface);
}

.input-wrapper input:focus {
    outline: none;
    border-color: var(--primary);
    box-shadow: 0 0 0 3px rgba(26, 86, 219, 0.1);
}

.input-wrapper input::placeholder {
    color: #9ca3af;
}

.toggle-password {
    position: absolute;
    right: 14px;
    top: 50%;
    transform: translateY(-50%);
    cursor: pointer;
    color: var(--text-secondary);
    font-size: 18px;
    user-select: none;
}

.remember-forgot {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 24px;
    font-size: 14px;
}

.remember {
    display: flex;
    align-items: center;
    gap: 8px;
    color: var(--text-secondary);
    cursor: pointer;
}

.remember input[type="checkbox"] {
    width: 18px;
    height: 18px;
    accent-color: var(--primary);
    cursor: pointer;
}

.forgot {
    color: var(--primary);
    text-decoration: none;
    font-weight: 600;
}

.btn-primary {
    width: 100%;
    padding: 16px;
    border: none;
    border-radius: var(--radius-sm);
    background: linear-gradient(135deg, var(--primary) 0%, #7c3aed 100%);
    color: white;
    font-size: 16px;
    font-weight: 600;
    cursor: pointer;
    transition: var(--transition);
    position: relative;
    overflow: hidden;
}

.btn-primary:hover {
    transform: translateY(-2px);
    box-shadow: var(--shadow-lg);
}

.btn-primary:active {
    transform: translateY(0);
}

.btn-primary.loading {
    color: transparent;
}

.btn-primary.loading::after {
    content: '';
    position: absolute;
    width: 20px;
    height: 20px;
    top: 50%;
    left: 50%;
    margin-left: -10px;
    margin-top: -10px;
    border: 2px solid rgba(255,255,255,0.3);
    border-radius: 50%;
    border-top-color: white;
    animation: spin 0.8s linear infinite;
}

@keyframes spin {
    to { transform: rotate(360deg); }
}

.biometric {
    text-align: center;
    margin-top: 24px;
}

.biometric-btn {
    width: 56px;
    height: 56px;
    border-radius: 50%;
    border: 2px solid var(--border);
    background: var(--surface);
    display: inline-flex;
    align-items: center;
    justify-content: center;
    font-size: 24px;
    cursor: pointer;
    transition: var(--transition);
    margin-bottom: 8px;
}

.biometric-btn:hover {
    border-color: var(--primary);
    background: var(--primary-light);
    transform: scale(1.05);
}

.biometric p {
    color: var(--text-secondary);
    font-size: 13px;
}

.signup-link {
    text-align: center;
    margin-top: 20px;
    color: var(--text-secondary);
    font-size: 14px;
}

.signup-link a {
    color: var(--primary);
    text-decoration: none;
    font-weight: 600;
}

/* DASHBOARD */
.dashboard {
    display: none;
    padding: 0;
}

.dashboard-header {
    background: linear-gradient(135deg, var(--primary) 0%, #7c3aed 100%);
    padding: 50px 24px 100px;
    position: relative;
    overflow: hidden;
}

.dashboard-header::before {
    content: '';
    position: absolute;
    top: -30%;
    right: -20%;
    width: 250px;
    height: 250px;
    background: rgba(255,255,255,0.08);
    border-radius: 50%;
}

.header-top {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 24px;
    position: relative;
    z-index: 1;
}

.profile {
    display: flex;
    align-items: center;
    gap: 12px;
}

.avatar {
    width: 44px;
    height: 44px;
    border-radius: 50%;
    background: rgba(255,255,255,0.2);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 20px;
    border: 2px solid rgba(255,255,255,0.3);
}

.profile-info h3 {
    color: white;
    font-size: 16px;
    font-weight: 600;
}

.profile-info p {
    color: rgba(255,255,255,0.7);
    font-size: 13px;
}

.notification-btn {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    background: rgba(255,255,255,0.15);
    border: none;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 18px;
    cursor: pointer;
    color: white;
    position: relative;
    transition: var(--transition);
}

.notification-btn:hover {
    background: rgba(255,255,255,0.25);
}

.notification-btn .badge {
    position: absolute;
    top: -2px;
    right: -2px;
    width: 18px;
    height: 18px;
    background: var(--danger);
    color: white;
    font-size: 10px;
    font-weight: 700;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 2px solid var(--primary);
}

.balance-card {
    background: rgba(255,255,255,0.15);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(255,255,255,0.2);
    border-radius: var(--radius);
    padding: 24px;
    position: relative;
    z-index: 1;
}

.balance-label {
    color: rgba(255,255,255,0.8);
    font-size: 14px;
    margin-bottom: 8px;
}

.balance-amount {
    color: white;
    font-size: 36px;
    font-weight: 700;
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 12px;
}

.balance-amount .currency {
    font-size: 20px;
    opacity: 0.8;
}

.eye-toggle {
    background: none;
    border: none;
    color: rgba(255,255,255,0.7);
    font-size: 20px;
    cursor: pointer;
    padding: 0;
    width: auto;
    transition: var(--transition);
}

.eye-toggle:hover {
    color: white;
}

.account-info {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.account-number {
    color: rgba(255,255,255,0.7);
    font-size: 13px;
    font-family: 'Courier New', monospace;
    letter-spacing: 1px;
}

.copy-btn {
    background: rgba(255,255,255,0.2);
    border: none;
    color: white;
    padding: 6px 12px;
    border-radius: 8px;
    font-size: 12px;
    cursor: pointer;
    transition: var(--transition);
    width: auto;
    margin: 0;
}

.copy-btn:hover {
    background: rgba(255,255,255,0.3);
}

.copy-btn.copied {
    background: var(--success);
}

/* QUICK ACTIONS */
.actions-section {
    padding: 0 24px;
    margin-top: -50px;
    position: relative;
    z-index: 2;
}

.actions-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 12px;
    background: var(--surface);
    padding: 20px;
    border-radius: var(--radius);
    box-shadow: var(--shadow);
}

.action-item {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    cursor: pointer;
    transition: var(--transition);
    padding: 8px 4px;
    border-radius: var(--radius-sm);
}

.action-item:hover {
    background: var(--bg);
    transform: translateY(-2px);
}

.action-icon {
    width: 48px;
    height: 48px;
    border-radius: 14px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 22px;
    transition: var(--transition);
}

.action-item:hover .action-icon {
    transform: scale(1.1);
}

.action-icon.transfer { background: #dbeafe; }
.action-icon.deposit { background: #d1fae5; }
.action-icon.withdraw { background: #fee2e2; }
.action-icon.airtime { background: #fef3c7; }
.action-icon.bills { background: #e0e7ff; }
.action-icon.cards { background: #fce7f3; }
.action-icon.crypto { background: #f3e8ff; }
.action-icon.more { background: #f3f4f6; }

.action-label {
    font-size: 12px;
    color: var(--text);
    font-weight: 500;
}

/* SECTIONS */
.section {
    padding: 24px;
}

.section-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 16px;
}

.section-title {
    font-size: 18px;
    font-weight: 700;
    color: var(--text);
}

.see-all {
    color: var(--primary);
    text-decoration: none;
    font-size: 14px;
    font-weight: 600;
}

/* CARDS PREVIEW */
.cards-preview {
    display: flex;
    gap: 16px;
    overflow-x: auto;
    padding-bottom: 8px;
    scrollbar-width: none;
}

.cards-preview::-webkit-scrollbar { display: none; }

.credit-card {
    min-width: 280px;
    height: 170px;
    border-radius: var(--radius);
    padding: 20px;
    color: white;
    position: relative;
    overflow: hidden;
    box-shadow: var(--shadow);
}

.credit-card.visa {
    background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
}

.credit-card.mastercard {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}

.card-chip {
    width: 40px;
    height: 30px;
    background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 100%);
    border-radius: 6px;
    margin-bottom: 20px;
    position: relative;
}

.card-chip::before {
    content: '';
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 30px;
    height: 20px;
    border: 1px solid rgba(0,0,0,0.2);
    border-radius: 4px;
}

.card-number {
    font-family: 'Courier New', monospace;
    font-size: 18px;
    letter-spacing: 2px;
    margin-bottom: 20px;
}

.card-footer {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
}

.card-holder {
    font-size: 13px;
    opacity: 0.9;
}

.card-expiry {
    font-size: 13px;
    opacity: 0.9;
}

.card-logo {
    position: absolute;
    top: 20px;
    right: 20px;
    font-size: 32px;
    opacity: 0.9;
}

/* TRANSACTIONS */
.transactions-list {
    display: flex;
    flex-direction: column;
    gap: 12px;
}

.transaction-item {
    background: var(--surface);
    padding: 16px;
    border-radius: var(--radius-sm);
    display: flex;
    align-items: center;
    gap: 14px;
    transition: var(--transition);
    cursor: pointer;
    border: 1px solid transparent;
}

.transaction-item:hover {
    border-color: var(--border);
    box-shadow: var(--shadow-sm);
    transform: translateX(4px);
}

.tx-icon {
    width: 44px;
    height: 44px;
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 20px;
    flex-shrink: 0;
}

.tx-icon.income { background: #d1fae5; }
.tx-icon.expense { background: #fee2e2; }
.tx-icon.transfer { background: #dbeafe; }
.tx-icon.bill { background: #fef3c7; }

.tx-details {
    flex: 1;
    min-width: 0;
}

.tx-title {
    font-weight: 600;
    color: var(--text);
    font-size: 14px;
    margin-bottom: 4px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}

.tx-meta {
    color: var(--text-secondary);
    font-size: 12px;
}

.tx-amount {
    font-weight: 700;
    font-size: 15px;
    text-align: right;
}

.tx-amount.positive { color: var(--success); }
.tx-amount.negative { color: var(--danger); }

/* NAVIGATION */
.nav {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    background: var(--surface);
    display: flex;
    justify-content: space-around;
    padding: 12px 0 24px;
    border-top: 1px solid var(--border);
    z-index: 10;
}

.nav-item {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 4px;
    cursor: pointer;
    padding: 4px 16px;
    border-radius: 12px;
    transition: var(--transition);
    color: var(--text-secondary);
}

.nav-item:hover, .nav-item.active {
    color: var(--primary);
}

.nav-item.active {
    background: var(--primary-light);
}

.nav-icon {
    font-size: 22px;
}

.nav-label {
    font-size: 11px;
    font-weight: 500;
}

/* TOAST NOTIFICATION */
.toast {
    position: fixed;
    top: 20px;
    left: 50%;
    transform: translateX(-50%) translateY(-100px);
    background: var(--text);
    color: white;
    padding: 12px 24px;
    border-radius: var(--radius-sm);
    font-size: 14px;
    font-weight: 500;
    z-index: 1000;
    opacity: 0;
    transition: all 0.4s cubic-bezier(0.68, -0.55, 0.265, 1.55);
    box-shadow: var(--shadow-lg);
}

.toast.show {
    transform: translateX(-50%) translateY(0);
    opacity: 1;
}

/* MODAL */
.modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.5);
    backdrop-filter: blur(4px);
    display: none;
    align-items: flex-end;
    justify-content: center;
    z-index: 100;
    opacity: 0;
    transition: opacity 0.3s ease;
}

.modal-overlay.active {
    display: flex;
    opacity: 1;
}

.modal {
    background: var(--surface);
    width: 100%;
    max-height: 80%;
    border-radius: var(--radius) var(--radius) 0 0;
    padding: 24px;
    transform: translateY(100%);
    transition: transform 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.modal-overlay.active .modal {
    transform: translateY(0);
}

.modal-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}

.modal-title {
    font-size: 20px;
    font-weight: 700;
}

.modal-close {
    width: 36px;
    height: 36px;
    border-radius: 50%;
    border: none;
    background: var(--bg);
    cursor: pointer;
    font-size: 18px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.amount-input {
    font-size: 32px;
    font-weight: 700;
    text-align: center;
    border: none;
    border-bottom: 2px solid var(--border);
    width: 100%;
    padding: 12px;
    margin: 20px 0;
    outline: none;
    color: var(--text);
}

.amount-input:focus {
    border-color: var(--primary);
}

/* ANIMATIONS */
@keyframes fadeIn {
    from { opacity: 0; transform: translateY(10px); }
    to { opacity: 1; transform: translateY(0); }
}

.animate-in {
    animation: fadeIn 0.5s ease forwards;
}

.stagger-1 { animation-delay: 0.1s; opacity: 0; }
.stagger-2 { animation-delay: 0.2s; opacity: 0; }
.stagger-3 { animation-delay: 0.3s; opacity: 0; }
.stagger-4 { animation-delay: 0.4s; opacity: 0; }
.stagger-5 { animation-delay: 0.5s; opacity: 0; }

/* PAGE TRANSITIONS */
.page {
    display: none;
    animation: fadeIn 0.3s ease;
}

.page.active {
    display: block;
}

/* STATS PAGE */
.stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
    margin-bottom: 24px;
}

.stat-card {
    background: var(--surface);
    padding: 20px;
    border-radius: var(--radius-sm);
    box-shadow: var(--shadow-sm);
}

.stat-label {
    font-size: 12px;
    color: var(--text-secondary);
    margin-bottom: 8px;
}

.stat-value {
    font-size: 24px;
    font-weight: 700;
    color: var(--text);
}

.stat-value.up { color: var(--success); }
.stat-value.down { color: var(--danger); }

/* CHART BAR */
.chart-container {
    background: var(--surface);
    padding: 20px;
    border-radius: var(--radius-sm);
    box-shadow: var(--shadow-sm);
}

.chart-bars {
    display: flex;
    align-items: flex-end;
    justify-content: space-around;
    height: 150px;
    gap: 8px;
    margin-top: 16px;
}

.chart-bar {
    flex: 1;
    background: linear-gradient(to top, var(--primary), #7c3aed);
    border-radius: 8px 8px 0 0;
    min-height: 20px;
    transition: var(--transition);
    position: relative;
    cursor: pointer;
}

.chart-bar:hover {
    opacity: 0.8;
}

.chart-bar-label {
    position: absolute;
    bottom: -20px;
    left: 50%;
    transform: translateX(-50%);
    font-size: 11px;
    color: var(--text-secondary);
    white-space: nowrap;
}

/* NOTIFICATIONS PAGE */
.notification-item {
    background: var(--surface);
    padding: 16px;
    border-radius: var(--radius-sm);
    margin-bottom: 12px;
    display: flex;
    gap: 12px;
    align-items: flex-start;
    border-left: 3px solid var(--primary);
}

.notification-item.unread {
    background: var(--primary-light);
}

.notif-icon {
    width: 36px;
    height: 36px;
    border-radius: 50%;
    background: var(--bg);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 16px;
    flex-shrink: 0;
}

.notif-content h4 {
    font-size: 14px;
    margin-bottom: 4px;
}

.notif-content p {
    font-size: 13px;
    color: var(--text-secondary);
}

.notif-time {
    font-size: 11px;
    color: var(--text-secondary);
    margin-top: 4px;
}

/* SETTINGS */
.settings-group {
    background: var(--surface);
    border-radius: var(--radius-sm);
    overflow: hidden;
    margin-bottom: 16px;
}

.settings-item {
    padding: 16px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 1px solid var(--bg);
    cursor: pointer;
    transition: var(--transition);
}

.settings-item:hover {
    background: var(--bg);
}

.settings-item:last-child {
    border-bottom: none;
}

.settings-left {
    display: flex;
    align-items: center;
    gap: 12px;
}

.settings-icon {
    width: 36px;
    height: 36px;
    border-radius: 10px;
    background: var(--bg);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 18px;
}

.settings-label {
    font-weight: 500;
    font-size: 14px;
}

.toggle-switch {
    width: 48px;
    height: 26px;
    background: var(--border);
    border-radius: 13px;
    position: relative;
    cursor: pointer;
    transition: var(--transition);
}

.toggle-switch.active {
    background: var(--primary);
}

.toggle-switch::after {
    content: '';
    position: absolute;
    width: 22px;
    height: 22px;
    background: white;
    border-radius: 50%;
    top: 2px;
    left: 2px;
    transition: var(--transition);
    box-shadow: var(--shadow-sm);
}

.toggle-switch.active::after {
    left: 24px;
}

.logout-btn {
    width: 100%;
    padding: 16px;
    border: 2px solid #fee2e2;
    border-radius: var(--radius-sm);
    background: transparent;
    color: var(--danger);
    font-size: 16px;
    font-weight: 600;
    cursor: pointer;
    transition: var(--transition);
}

.logout-btn:hover {
    background: #fee2e2;
}

/* RESPONSIVE */
@media (max-width: 400px) {
    .phone {
        width: 100%;
        height: 100vh;
        border-radius: 0;
        box-shadow: none;
    }
    
    body {
        padding: 0;
        background: var(--bg);
    }
}
</style>
</head>
<body>

<div class="phone">

    <!-- LOGIN SCREEN -->
    <div class="screen login page active" id="loginPage">
        <div class="login-header">
            <h1>Nova Bank</h1>
            <p>Secure Mobile Banking</p>
        </div>
        
        <div class="login-form">
            <div class="input-group">
                <label>Username</label>
                <div class="input-wrapper">
                    <input type="text" id="username" placeholder="Enter your username">
                </div>
            </div>
            
            <div class="input-group">
                <label>Password</label>
                <div class="input-wrapper">
                    <input type="password" id="password" placeholder="Enter your password">
                    <span class="toggle-password" onclick="togglePassword()">👁️</span>
                </div>
            </div>
            
            <div class="remember-forgot">
                <label class="remember">
                    <input type="checkbox" checked>
                    <span>Remember me</span>
                </label>
                <a href="#" class="forgot" onclick="showToast('Reset link sent!')">Forgot Password?</a>
            </div>
            
            <button class="btn-primary" id="loginBtn" onclick="login()">Sign In</button>
            
            <div class="biometric">
                <button class="biometric-btn" onclick="showToast('Fingerprint scanning...')">👆</button>
                <p>Use Biometric</p>
            </div>
            
            <div class="signup-link">
                Don't have an account? <a href="#">Sign Up</a>
            </div>
        </div>
    </div>

    <!-- DASHBOARD -->
    <div class="screen dashboard page" id="dashboard">
        <div class="dashboard-header">
            <div class="header-top">
                <div class="profile">
                    <div class="avatar">👤</div>
                    <div class="profile-info">
                        <h3 id="userDisplay">Customer</h3>
                        <p>Good morning</p>
                    </div>
                </div>
                <button class="notification-btn" onclick="showPage('notifications')">
                    🔔
                    <span class="badge">3</span>
                </button>
            </div>
            
            <div class="balance-card">
                <div class="balance-label">Total Balance</div>
                <div class="balance-amount">
                    <span class="currency">$</span>
                    <span id="balanceValue">12,450.75</span>
                    <button class="eye-toggle" onclick="toggleBalance()">👁️</button>
                </div>
                <div class="account-info">
                    <span class="account-number">**** 4892</span>
                    <button class="copy-btn" onclick="copyAccount()">Copy</button>
                </div>
            </div>
        </div>
        
        <div class="actions-section">
            <div class="actions-grid">
                <div class="action-item" onclick="openModal('Transfer')">
                    <div class="action-icon transfer">💸</div>
                    <span class="action-label">Transfer</span>
                </div>
                <div class="action-item" onclick="openModal('Deposit')">
                    <div class="action-icon deposit">📥</div>
                    <span class="action-label">Deposit</span>
                </div>
                <div class="action-item" onclick="openModal('Withdraw')">
                    <div class="action-icon withdraw">📤</div>
                    <span class="action-label">Withdraw</span>
                </div>
                <div class="action-item" onclick="showToast('Airtime purchase coming soon')">
                    <div class="action-icon airtime">📱</div>
                    <span class="action-label">Airtime</span>
                </div>
                <div class="action-item" onclick="showToast('Bills payment coming soon')">
                    <div class="action-icon bills">💡</div>
                    <span class="action-label">Bills</span>
                </div>
                <div class="action-item" onclick="showToast('Cards management coming soon')">
                    <div class="action-icon cards">💳</div>
                    <span class="action-label">Cards</span>
                </div>
                <div class="action-item" onclick="showToast('Crypto trading coming soon')">
                    <div class="action-icon crypto">₿</div>
                    <span class="action-label">Crypto</span>
                </div>
                <div class="action-item" onclick="showToast('More features coming soon')">
                    <div class="action-icon more">•••</div>
                    <span class="action-label">More</span>
                </div>
            </div>
        </div>
        
        <div class="section">
            <div class="section-header">
                <h3 class="section-title">My Cards</h3>
                <a href="#" class="see-all">See All</a>
            </div>
            <div class="cards-preview">
                <div class="credit-card visa">
                    <div class="card-logo">VISA</div>
                    <div class="card-chip"></div>
                    <div class="card-number">•••• •••• •••• 4521</div>
                    <div class="card-footer">
                        <span class="card-holder">JOHN DOE</span>
                        <span class="card-expiry">12/26</span>
                    </div>
                </div>
                <div class="credit-card mastercard">
                    <div class="card-logo">MC</div>
                    <div class="card-chip"></div>
                    <div class="card-number">•••• •••• •••• 8890</div>
                    <div class="card-footer">
                        <span class="card-holder">JOHN DOE</span>
                        <span class="card-expiry">08/25</span>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="section">
            <div class="section-header">
                <h3 class="section-title">Recent Transactions</h3>
                <a href="#" class="see-all">See All</a>
            </div>
            <div class="transactions-list" id="transactionsList">
                <div class="transaction-item animate-in stagger-1">
                    <div class="tx-icon income">💰</div>
                    <div class="tx-details">
                        <div class="tx-title">Salary Payment</div>
                        <div class="tx-meta">Today • Income</div>
                    </div>
                    <div class="tx-amount positive">+$2,000.00</div>
                </div>
                <div class="transaction-item animate-in stagger-2">
                    <div class="tx-icon expense">🎬</div>
                    <div class="tx-details">
                        <div class="tx-title">Netflix Subscription</div>
                        <div class="tx-meta">Yesterday • Entertainment</div>
                    </div>
                    <div class="tx-amount negative">-$15.99</div>
                </div>
                <div class="transaction-item animate-in stagger-3">
                    <div class="tx-icon transfer">👤</div>
                    <div class="tx-details">
                        <div class="tx-title">Transfer to John</div>
                        <div class="tx-meta">May 28 • Transfer</div>
                    </div>
                    <div class="tx-amount negative">-$250.00</div>
                </div>
                <div class="transaction-item animate-in stagger-4">
                    <div class="tx-icon bill">⚡</div>
                    <div class="tx-details">
                        <div class="tx-title">Electricity Bill</div>
                        <div class="tx-meta">May 27 • Utilities</div>
                    </div>
                    <div class="tx-amount negative">-$48.50</div>
                </div>
                <div class="transaction-item animate-in stagger-5">
                    <div class="tx-icon expense">🛒</div>
                    <div class="tx-details">
                        <div class="tx-title">Online Shopping</div>
                        <div class="tx-meta">May 26 • Shopping</div>
                    </div>
                    <div class="tx-amount negative">-$120.00</div>
                </div>
            </div>
        </div>
    </div>

    <!-- STATS PAGE -->
    <div class="screen page" id="statsPage">
        <div class="dashboard-header" style="padding-bottom: 30px;">
            <div class="header-top">
                <h3 style="color: white; font-size: 20px;">Analytics</h3>
            </div>
        </div>
        <div class="section" style="margin-top: -20px;">
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-label">Income</div>
                    <div class="stat-value up">$4,250</div>
                </div>
                <div class="stat-card">
                    <div class="stat-label">Expenses</div>
                    <div class="stat-value down">$1,890</div>
                </div>
            </div>
            <div class="chart-container">
                <h4 style="margin-bottom: 8px; font-size: 16px;">Spending Overview</h4>
                <div class="chart-bars">
                    <div class="chart-bar" style="height: 60%;"><span class="chart-bar-label">Mon</span></div>
                    <div class="chart-bar" style="height: 40%;"><span class="chart-bar-label">Tue</span></div>
                    <div class="chart-bar" style="height: 80%;"><span class="chart-bar-label">Wed</span></div>
                    <div class="chart-bar" style="height: 50%;"><span class="chart-bar-label">Thu</span></div>
                    <div class="chart-bar" style="height: 90%;"><span class="chart-bar-label">Fri</span></div>
                    <div class="chart-bar" style="height: 30%;"><span class="chart-bar-label">Sat</span></div>
                    <div class="chart-bar" style="height: 45%;"><span class="chart-bar-label">Sun</span></div>
                </div>
            </div>
        </div>
    </div>

    <!-- NOTIFICATIONS PAGE -->
    <div class="screen page" id="notificationsPage">
        <div class="dashboard-header" style="padding-bottom: 30px;">
            <div class="header-top">
                <h3 style="color: white; font-size: 20px;">Notifications</h3>
            </div>
        </div>
        <div class="section" style="margin-top: -20px;">
            <div class="notification-item unread">
                <div class="notif-icon">🔒</div>
                <div class="notif-content">
                    <h4>Security Alert</h4>
                    <p>New login detected from Chrome on Windows</p>
                    <div class="notif-time">2 min ago</div>
                </div>
            </div>
            <div class="notification-item unread">
                <div class="notif-icon">💰</div>
                <div class="notif-content">
                    <h4>Payment Received</h4>
                    <p>You received $500 from Sarah Johnson</p>
                    <div class="notif-time">1 hour ago</div>
                </div>
            </div>
            <div class="notification-item unread">
                <div class="notif-icon">💳</div>
                <div class="notif-content">
                    <h4>Card Update</h4>
                    <p>Your Visa ending in 4521 expires next month</p>
                    <div class="notif-time">3 hours ago</div>
                </div>
            </div>
            <div class="notification-item">
                <div class="notif-icon">📊</div>
                <div class="notif-content">
                    <h4>Monthly Report</h4>
                    <p>Your May spending report is ready</p>
                    <div class="notif-time">Yesterday</div>
                </div>
            </div>
        </div>
    </div>

    <!-- SETTINGS PAGE -->
    <div class="screen page" id="settingsPage">
        <div class="dashboard-header" style="padding-bottom: 30px;">
            <div class="header-top">
                <h3 style="color: white; font-size: 20px;">Settings</h3>
            </div>
        </div>
        <div class="section" style="margin-top: -20px;">
            <div class="settings-group">
                <div class="settings-item">
                    <div class="settings-left">
                        <div class="settings-icon">🔔</div>
                        <span class="settings-label">Push Notifications</span>
                    </div>
                    <div class="toggle-switch active" onclick="toggleSwitch(this)"></div>
                </div>
                <div class="settings-item">
                    <div class="settings-left">
                        <div class="settings-icon">🔒</div>
                        <span class="settings-label">Biometric Login</span>
                    </div>
                    <div class="toggle-switch active" onclick="toggleSwitch(this)"></div>
                </div>
                <div class="settings-item">
                    <div class="settings-left">
                        <div class="settings-icon">🌙</div>
                        <span class="settings-label">Dark Mode</span>
                    </div>
                    <div class="toggle-switch" onclick="toggleSwitch(this)"></div>
                </div>
            </div>
            
            <div class="settings-group">
                <div class="settings-item" onclick="showToast('Profile settings coming soon')">
                    <div class="settings-left">
                        <div class="settings-icon">👤</div>
                        <span class="settings-label">Edit Profile</span>
                    </div>
                    <span style="color: var(--text-secondary);">›</span>
                </div>
                <div class="settings-item" onclick="showToast('Security settings coming soon')">
                    <div class="settings-left">
                        <div class="settings-icon">🛡️</div>
                        <span class="settings-label">Security</span>
                    </div>
                    <span style="color: var(--text-secondary);">›</span>
                </div>
                <div class="settings-item" onclick="showToast('Help center coming soon')">
                    <div class="settings-left">
                        <div class="settings-icon">❓</div>
                        <span class="settings-label">Help & Support</span>
                    </div>
                    <span style="color: var(--text-secondary);">›</span>
                </div>
            </div>
            
            <button class="logout-btn" onclick="logout()">Log Out</button>
        </div>
    </div>

    <!-- NAVIGATION -->
    <div class="nav" id="bottomNav" style="display: none;">
        <div class="nav-item active" onclick="showPage('dashboard')" data-page="dashboard">
            <span class="nav-icon">🏠</span>
            <span class="nav-label">Home</span>
        </div>
        <div class="nav-item" onclick="showPage('stats')" data-page="stats">
            <span class="nav-icon">📈</span>
            <span class="nav-label">Stats</span>
        </div>
        <div class="nav-item" onclick="showPage('notifications')" data-page="notifications">
            <span class="nav-icon">🔔</span>
            <span class="nav-label">Alerts</span>
        </div>
        <div class="nav-item" onclick="showPage('settings')" data-page="settings">
            <span class="nav-icon">⚙️</span>
            <span class="nav-label">Settings</span>
        </div>
    </div>

    <!-- MODAL -->
    <div class="modal-overlay" id="modalOverlay" onclick="closeModal(event)">
        <div class="modal" onclick="event.stopPropagation()">
            <div class="modal-header">
                <h3 class="modal-title" id="modalTitle">Transfer</h3>
                <button class="modal-close" onclick="closeModal()">✕</button>
            </div>
            <input type="text" class="amount-input" placeholder="0.00" id="amountInput">
            <button class="btn-primary" onclick="processTransaction()">Confirm</button>
        </div>
    </div>

    <!-- TOAST -->
    <div class="toast" id="toast"></div>

</div>

<script>
let currentBalance = 12450.75;
let balanceHidden = false;

function login() {
    const user = document.getElementById('username').value || 'Customer';
    const btn = document.getElementById('loginBtn');
    
    btn.classList.add('loading');
    
    setTimeout(() => {
        document.getElementById('userDisplay').innerText = user;
        document.getElementById('loginPage').classList.remove('active');
        document.getElementById('dashboard').classList.add('active');
        document.getElementById('bottomNav').style.display = 'flex';
        btn.classList.remove('loading');
        
        // Animate transactions
        document.querySelectorAll('.transaction-item').forEach((item, i) => {
            item.style.animationDelay = `${i * 0.1}s`;
        });
    }, 1500);
}

function logout() {
    document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
    document.getElementById('loginPage').classList.add('active');
    document.getElementById('bottomNav').style.display = 'none';
    document.getElementById('username').value = '';
    document.getElementById('password').value = '';
}

function showPage(pageName) {
    document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
    document.querySelectorAll('.nav-item').forEach(n => n.classList.remove('active'));
    
    const pageMap = {
        'dashboard': 'dashboard',
        'stats': 'statsPage',
        'notifications': 'notificationsPage',
        'settings': 'settingsPage'
    };
    
    document.getElementById(pageMap[pageName]).classList.add('active');
    document.querySelector(`.nav-item[data-page="${pageName}"]`).classList.add('active');
}

function togglePassword() {
    const input = document.getElementById('password');
    const toggle = document.querySelector('.toggle-password');
    input.type = input.type === 'password' ? 'text' : 'password';
    toggle.textContent = input.type === 'password' ? '👁️' : '🙈';
}

function toggleBalance() {
    const value = document.getElementById('balanceValue');
    balanceHidden = !balanceHidden;
    value.textContent = balanceHidden ? '••••••' : currentBalance.toLocaleString('en-US', {minimumFractionDigits: 2});
}

function copyAccount() {
    navigator.clipboard.writeText('4892');
    const btn = document.querySelector('.copy-btn');
    btn.textContent = 'Copied!';
    btn.classList.add('copied');
    showToast('Account number copied!');
    setTimeout(() => {
        btn.textContent = 'Copy';
        btn.classList.remove('copied');
    }, 2000);
}

function showToast(message) {
    const toast = document.getElementById('toast');
    toast.textContent = message;
    toast.classList.add('show');
    setTimeout(() => toast.classList.remove('show'), 3000);
}

function openModal(title) {
    document.getElementById('modalTitle').textContent = title;
    document.getElementById('modalOverlay').classList.add('active');
    document.getElementById('amountInput').value = '';
    setTimeout(() => document.getElementById('amountInput').focus(), 300);
}

function closeModal(e) {
    if (!e || e.target === document.getElementById('modalOverlay')) {
        document.getElementById('modalOverlay').classList.remove('active');
    }
}

function processTransaction() {
    const amount = parseFloat(document.getElementById('amountInput').value);
    if (!amount || amount <= 0) {
        showToast('Please enter a valid amount');
        return;
    }
    
    const title = document.getElementById('modalTitle').textContent;
    
    if (title === 'Withdraw' && amount > currentBalance) {
        showToast('Insufficient funds');
        return;
    }
    
    closeModal();
    
    if (title === 'Deposit') {
        currentBalance += amount;
        addTransaction('Deposit', amount, 'income', '💰');
    } else if (title === 'Withdraw') {
        currentBalance -= amount;
        addTransaction('Withdrawal', -amount, 'expense', '💸');
    } else {
        currentBalance -= amount;
        addTransaction(`Transfer`, -amount, 'transfer', '👤');
    }
    
    document.getElementById('balanceValue').textContent = currentBalance.toLocaleString('en-US', {minimumFractionDigits: 2});
    showToast(`${title} of $${amount.toFixed(2)} successful!`);
}

function addTransaction(title, amount, type, icon) {
    const list = document.getElementById('transactionsList');
    const item = document.createElement('div');
    item.className = 'transaction-item animate-in';
    item.innerHTML = `
        <div class="tx-icon ${type}">${icon}</div>
        <div class="tx-details">
            <div class="tx-title">${title}</div>
            <div class="tx-meta">Just now • ${type.charAt(0).toUpperCase() + type.slice(1)}</div>
        </div>
        <div class="tx-amount ${amount > 0 ? 'positive' : 'negative'}">${amount > 0 ? '+' : ''}$${Math.abs(amount).toFixed(2)}</div>
    `;
    list.insertBefore(item, list.firstChild);
}

function toggleSwitch(el) {
    el.classList.toggle('active');
    const isActive = el.classList.contains('active');
    const label = el.closest('.settings-item').querySelector('.settings-label').textContent;
    showToast(`${label} ${isActive ? 'enabled' : 'disabled'}`);
}

// Greeting based on time
function setGreeting() {
    const hour = new Date().getHours();
    const greeting = hour < 12 ? 'Good morning' : hour < 18 ? 'Good afternoon' : 'Good evening';
    const el = document.querySelector('.profile-info p');
    if (el) el.textContent = greeting;
}

setGreeting();
</script>

</body>
</html>
