# ⚡ Bybit Futures Risk, RRR & Position Sizing Calculator

A web-based tool for Bybit USDT-Margined Perpetual Futures that calculates exact position sizing for fixed dollar risk, accounts for open/close trading fees, determines Bybit isolated margin liquidation prices, and provides real-time Risk-to-Reward Ratio (RRR) analysis.

![Screenshot](screenshot.png)

---

## 🚀 Key Features

* **🔒 Fixed Dollar Loss ($R$):** Sizes your trade so your loss at Stop Loss is guaranteed (e.g. exactly `$0.20 USDT`).
* **💰 True Net Risk (Fee-Adjusted):** Incorporates Bybit taker/maker opening and closing fees directly into the sizing denominator so you never overshoot your risk.
* **🔢 Whole Unit Precision:** Automatically floors order quantities to integer contracts to match Bybit altcoin constraints without order rejections.
* **🎯 Net Risk-to-Reward (RRR) & Win Rate:** Computes your true net RRR and the exact minimum win rate required to break even.
* **🪜 Interactive Vertical Price Ladder:** Real-time visual price ladder connecting Take Profit, Entry, Stop Loss, and Bybit Liquidation.
* **🛡️ Liquidation Safety & Max Safe Leverage:** Accurately models Bybit's isolated margin engine (including Maintenance Margin Rate and fee reserve buffers) and alerts if leverage causes liquidation before your Stop Loss.
* **📋 One-Click Order Copy:** Copies the complete formatted setup to your clipboard to paste into Bybit or trade journals.

---

## 🧮 Mathematical Formulas

### 1. True Net Fee-Adjusted Position Sizing
$$\text{Quantity} = \frac{\text{Target Risk } (R)}{|\text{Entry} - \text{SL}| + (\text{Entry} \times f_{\text{open}}) + (\text{SL} \times f_{\text{close}})}$$

### 2. Bybit Isolated Margin Liquidation Price
* **Long Position:**
  $$\text{LP}_{\text{Long}} = \text{Entry} \times \frac{1 - 1/L}{1 - B}$$
* **Short Position:**
  $$\text{LP}_{\text{Short}} = \text{Entry} \times \frac{1 + 1/L}{1 + B}$$

*(where $B = \text{MMR} + \text{Fee Buffer} \approx 0.02$ for Altcoins, $0.0056$ for BTC)*

### 3. Maximum Safe Leverage ($L_{\text{max}}$)
$$\text{Max Safe Leverage} = \frac{1}{1 - (1 - B)(\text{SL}/\text{Entry})}$$

### 4. Minimum Break-Even Win Rate
$$\text{Break-Even Win Rate} = \frac{1}{1 + \text{Net RRR}} \times 100\%$$

---

## 🌐 Quick Start

1. Clone or download this repository.
2. Open `index.html` in any web browser (Chrome, Edge, Safari, Firefox) on desktop or mobile.
3. No build tools, Node.js, or server required!

---

## 📄 License
MIT License
