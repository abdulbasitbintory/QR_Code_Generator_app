# 🔍 QR Code Generator  
*A responsive web application that generates QR codes from text or URLs*

## 🌟 Overview  
This project is a **modern QR code generator** that instantly converts text, URLs, or data into scannable QR codes. Built with HTML, CSS, and JavaScript, it features a sleek gradient UI, smooth animations, input validation, and responsive design for seamless use across mobile, tablet, and desktop devices. Powered by the **QRServer API**, it ensures reliable code generation without server-side dependencies.

---

## ✨ Key Features  

### 🚀 Core Functionality  
- **Instant QR Generation**: Generates QR codes in real-time as users type.  
- **API Integration**: Uses [QRServer API](https://api.qrserver.com/v1/create-qr-code/) for reliable code generation.  
- **Input Validation**: Prevents empty submissions with visual feedback.  
- **Error Handling**: Shake animation for invalid inputs and clear error states.  

### 🎨 UI/UX Highlights  
- **Modern Gradient Design**: Stylish blue-green gradient background (`linear-gradient(135deg, #74ebd5, #ACB6E5)`).  
- **Interactive Elements**:  
  - Button hover effects with gradient transitions.  
  - QR code scaling animation on hover.  
- **Visual Feedback**:  
  - Input field shake animation for empty submissions.  
  - Smooth transitions for QR code appearance.  
- **Responsive Layout**: Works seamlessly on mobile, tablet, and desktop.  

### ⚙️ Technical Implementation  
- **Efficient API Usage**: Direct image source integration with `encodeURIComponent` for safe URL handling.  
- **Client-Side Validation**: Ensures non-empty input before triggering API requests.  
- **CSS Animations**: Keyframe animations for error states and interactive elements.  
- **Progressive Enhancement**: Graceful degradation for older browsers.  

---

## 🛠️ Tech Stack  
| Technology | Purpose |  
|----------|---------|  
| **HTML5** | Semantic structure and accessibility |  
| **CSS3** | Animations, gradients, and responsive design |  
| **JavaScript** | API integration and DOM manipulation |  
| **QRServer API** | QR code generation service |  
| **Git/GitHub** | Version control and collaboration |  

---

## 📁 Project Structure  
```
qr-generator/
├── index.html          # Main HTML structure  
├── style.css           # Styling with animations and gradients  
├── script.js           # QR generation logic  
├── images/             # Optional icon assets  
│   └── qr-icon.png     # App icon (if applicable)  
├── README.md           # This documentation  
└── LICENSE             # MIT License  
```

---

## 🚀 Installation & Setup  

### Prerequisites  
- A modern web browser (Chrome, Firefox, Safari, Edge)  
- Basic knowledge of HTML/CSS/JavaScript  

### Steps  
1. **Clone the Repository**  
```bash
git clone https://github.com/abdulbasitbintory/qr-code-generator.git
cd qr-code-generator
```

2. **Run the App**  
- Open `index.html` directly in your browser.  
- No server setup required (works offline except for API calls).  

3. **Customization (Optional)**  
- Modify QR size in `script.js`:  
  ```javascript
  // Change QR code size (default: 150x150)
  let qrUrl = `https://api.qrserver.com/v1/create-qr-code/?size=200x200&data=${encodeURIComponent(qrText.value)}`;
  ```
- Update color scheme in `style.css`:  
  ```css
  --accent-color: #00e676; /* Green accent */
  ```

---

## 🧪 Usage Guide  

### 1. **Generate a QR Code**  
- Enter text or a URL in the input field.  
- Click the **"Generate QR Code"** button.  
- The QR code appears instantly below.  

### 2. **Use the QR Code**  
- **Download**: Right-click the QR code and select "Save Image As...".  
- **Scan**: Use a smartphone camera or QR scanner app.  

### 3. **Error Handling**  
- If the input is empty:  
  - The input field shakes with a red border.  
  - No QR code is generated.  

---

## 🧠 How It Works  

### QR Generation Logic  
```javascript
function generateQR() {
  let qrText = document.getElementById("qrText");
  let qrImage = document.getElementById("qrImage");
  let imgBox = document.querySelector(".qr-code");

  if (qrText.value.trim().length > 0) {
    // API call with user input
    let qrUrl = `https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=${encodeURIComponent(qrText.value)}`;
    
    // Display generated QR code
    qrImage.src = qrUrl;
    imgBox.classList.add("show-image");
  } else {
    // Error animation
    qrText.classList.add("error");
    setTimeout(() => qrText.classList.remove("error"), 1000);
  }
}
```

### UI Animations  
```css
/* Input error shake animation */
@keyframes shake {
  0% { transform: translateX(0); }
  25% { transform: translateX(-5px); }
  50% { transform: translateX(5px); }
  75% { transform: translateX(-5px); }
  100% { transform: translateX(0); }
}

/* QR code hover effect */
#qrImage:hover {
  transform: scale(1.05);
  transition: transform 0.3s ease;
}
```

---

## 🌍 Browser Compatibility  
- ✅ Chrome (latest)  
- ✅ Firefox (latest)  
- ✅ Safari (iOS 12+)  
- ✅ Edge (Chromium-based)  

---

## 🎨 Design Features  

### Gradient Background  
```css
body {
  background: linear-gradient(135deg, #74ebd5 0%, #ACB6E5 100%);
}
```

### Card Design  
```css
.card {
  background: #fff;
  border-radius: 15px;
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
  padding: 30px;
}
```

### Interactive Elements  
- Button hover effects:  
  ```css
  .generate-btn {
    background: linear-gradient(45deg, #00e676, #00c95f);
  }
  ```
- Input border color transition:  
  ```css
  input:focus {
    border-color: #00e676;
    transition: border-color 0.3s ease;
  }
  ```

---

## 📈 Future Enhancements  
- [ ] Add custom QR code color options  
- [ ] Enable download QR code as PNG  
- [ ] Implement QR code scanning functionality  
- [ ] Add history of generated codes  
- [ ] Add size customization options  
- [ ] Dark mode toggle  

---

## 💡 Contributing  
Contributions are welcome! Follow these steps:  
1. Fork the repository  
2. Create a feature branch (`git checkout -b feature-name`)  
3. Commit your changes (`git commit -m 'Add feature'`)  
4. Push to the branch (`git push origin feature-name`)  
5. Submit a pull request  

---

## 📄 License  
This project is licensed under the [MIT License](LICENSE).  

---

## 📬 Contact  
Abdul Basit Bin Tariq  
📧 Email: abdulbasitnotmain@gmail.com  
🌐 GitHub: [github.com/abdulbasitbintory](https://github.com/abdulbasitbintory)  

---

## 🙌 Acknowledgments  
- [QRServer API](https://api.qrserver.com/v1/create-qr-code/)  
- [W3C HTML/CSS Validation Tools](https://validator.w3.org/)  
- [Google Fonts (Poppins)](https://fonts.google.com/specimen/Poppins)  

---

**🔗 Generate. Scan. Connect.**
```

---

### ✅ To Use This README:
1. **Replace** `screenshot.png` with your actual project screenshot.  
2. **Add** a `LICENSE` file (MIT recommended).  
3. **Update** contact details, GitHub profile, and acknowledgments.  
4. **Customize** QR size or color schemes in code snippets if modified.  

This README includes:  
- Technical architecture  
- Code examples  
- Installation steps  
- Contribution guidelines  
- Browser compatibility  
- Roadmap for future features  

