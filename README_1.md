# 🤖 Aria — Customer Service Chatbot

A rule-based NLP chatbot for customer service, built with **vanilla HTML, CSS, and JavaScript** — no frameworks or external APIs needed. Features a live NLP pipeline visualizer so you can watch how each message is processed in real time.

![Chatbot Preview](https://img.shields.io/badge/Status-Live-brightgreen) ![HTML](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white) ![CSS](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black) ![NLP](https://img.shields.io/badge/NLP-Rule--Based-blue)

---

## ✨ Features

- **8 Intent categories** — Greeting, Order Tracking, Refund/Return, Payment, Account, Contact, Product Info, Thanks
- **Live NLP Pipeline** — watch tokenization, stopword removal, keyword matching, and intent detection animate in real time
- **Entity Extraction** — detects order IDs, email addresses, and phone numbers from user messages
- **Confidence scoring** — shows how confident the bot is about its detected intent
- **Quick suggestions** — context-aware suggestion chips after every response
- **Typing indicator** — simulates realistic response delay
- **Responsive design** — works on mobile and desktop
- **Zero dependencies** — pure HTML/CSS/JS, runs in any browser

---

## 🧠 How the NLP Pipeline Works

```
User Input
    │
    ▼
1. TOKENIZE        → "where is my order?" → ["where","is","my","order"]
    │
    ▼
2. NORMALIZE       → Remove stopwords    → ["order"]
    │
    ▼
3. KEYWORD MATCH   → Score against KB    → order_tracking: 1, refund: 0 ...
    │
    ▼
4. INTENT DETECT   → Highest score wins  → "order_tracking"
    │
    ▼
5. CONFIDENCE      → Relative score      → 87%
    │
    ▼
6. ENTITY EXTRACT  → Regex patterns      → "Order ID: #123456"
    │
    ▼
Rule-based Response Lookup → Bot Reply
```

---

## 🚀 Quick Start

### Option 1 — Open directly (no server needed)
```bash
git clone https://github.com/YOUR_USERNAME/customer-service-chatbot.git
cd customer-service-chatbot
open index.html        # macOS
# or double-click index.html in your file explorer
```

### Option 2 — Serve locally
```bash
# Python
python -m http.server 3000

# Node.js (npx)
npx serve .
```
Then open `http://localhost:3000`

---

## 🗂️ Project Structure

```
customer-service-chatbot/
├── index.html         # Complete app — all HTML, CSS, and JS in one file
└── README.md          # Documentation
```

---

## 🔧 Supported Intents

| Intent | Example Queries |
|---|---|
| `greeting` | "Hi", "Hello", "Hey there" |
| `order_tracking` | "Where is my order?", "Track my package", "Shipping status" |
| `refund` | "I want a refund", "Return policy", "Wrong item received" |
| `payment` | "Payment failed", "Update billing", "Subscription plans" |
| `account` | "Forgot password", "Login issues", "Reset my password" |
| `contact` | "Talk to a human", "Contact support", "Live agent" |
| `product` | "Product availability", "What's in stock?", "New arrivals" |
| `thanks` | "Thank you", "That was helpful", "Great!" |

---

## 🛠️ Extending the Bot

### Add a new intent
```javascript
// Inside the KB object in index.html
const KB = {
  // ...existing intents...

  shipping_cost: {
    keywords: ['shipping cost', 'delivery fee', 'free shipping', 'how much to ship'],
    responses: [
      "🚚 We offer free shipping on orders above ₹499. Standard rates apply below that.",
      "Delivery charges depend on your location. Free shipping is available on orders over ₹499!"
    ],
    suggestions: ['Check order total', 'Track my order', 'More info']
  }
};
```

### Upgrade to ML-based intent detection
Replace the `detectIntent()` function with a call to any NLP API:
- **Compromise.js** — lightweight client-side NLP
- **Wit.ai** — free intent classification API by Meta
- **Dialogflow** — Google's conversational AI platform
- **Rasa** — open-source ML chatbot framework

---

## 📚 Concepts Covered (Great for Learning!)

- **Tokenization** — splitting text into words
- **Stopword removal** — filtering common irrelevant words
- **Keyword-based intent classification** — rule-based NLP
- **Entity extraction** — using regex to find structured data
- **Confidence scoring** — normalizing match scores
- **Chatbot conversation design** — suggestion chips, fallback handling

---

## 🌐 Deploy for Free

### GitHub Pages
1. Push this repo to GitHub
2. Go to **Settings → Pages → Source: main branch**
3. Your chatbot is live at `https://YOUR_USERNAME.github.io/customer-service-chatbot`

### Netlify (drag & drop)
1. Go to [netlify.com](https://netlify.com)
2. Drag the project folder into the deploy area
3. Live in 30 seconds

---

## 🤝 Contributing

Pull requests are welcome! Ideas for improvement:
- [ ] Add more intents (FAQs, promotions, loyalty points)
- [ ] Integrate a real NLP API (Wit.ai, Dialogflow)
- [ ] Add conversation history / session storage
- [ ] Dark mode toggle
- [ ] Multi-language support

---

## 📄 License

MIT License — free to use, modify, and distribute.

---

## 👨‍💻 Author

Built as a learning project to understand **rule-based NLP** and **chatbot design patterns**.

⭐ Star this repo if it helped you learn something new!
