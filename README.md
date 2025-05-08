# ⏰ Theme-Based-Clock ⏱️

<div align="center">
  
![Theme Clock Preview](https://via.placeholder.com/800x200?text=Elegant+Theme+Based+Clock)

[![Live Demo](https://img.shields.io/badge/✨%20Live%20Demo-Visit%20Site-brightgreen?style=for-the-badge)](https://sainikith07.github.io/Theme-Based-Clock/)

</div>

<p align="center">
  <b>A beautiful and customizable clock with light/dark themes and elegant animations!</b>
</p>

---

## 🌟 Overview
This repository hosts an elegant, interactive analog & digital clock application with theme-switching capabilities. Toggle between light and dark modes for different visual experiences while enjoying smooth animations and minimalist design.

## ✨ Features

- 🌓 **Light/Dark Theme Toggle** - Switch between themes with a single click
- 🕰️ **Dual Clock Display** - Beautiful analog clock with hands + digital time display
- 📅 **Date Display** - Shows current day and date in a stylish format
- 🔄 **Smooth Animations** - Fluid transitions for clock hands and theme changes
- 📱 **Responsive Design** - Works perfectly on desktop and mobile devices

## 🔍 Live Demo

<div align="center">
  <a href="https://sainikith07.github.io/Theme-Based-Clock/" target="_blank">
    <img src="https://via.placeholder.com/600x100?text=Click+to+View+Live+Demo" alt="Demo Banner" width="600px"/>
  </a>
</div>

### 🎨 Theme Showcase

<div align="center">
  <table>
    <tr>
      <td>
        <img src="https://i.ibb.co/8X3QtM6/light-mode.jpg" alt="Light Theme" width="400px"/>
        <p align="center">✨ Light Theme</p>
      </td>
      <td>
        <img src="https://i.ibb.co/ypkZrQ3/dark-mode.jpg" alt="Dark Theme" width="400px"/>
        <p align="center">🌙 Dark Theme</p>
      </td>
    </tr>
  </table>
</div>

👉 **[Try it yourself!](https://sainikith07.github.io/Theme-Based-Clock/)** - Switch between light and dark modes

## 🛠️ Tech Stack
<div align="center">
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white"/>
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white"/>
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"/>
</div>

## 📁 Project Structure
```
📦 Theme-Based-Clock
 ┣ 📜 index.html     # Main HTML structure with clock layout
 ┣ 📜 style.css      # CSS styling with light/dark theme variables
 ┗ 📜 script.js      # JavaScript for clock functionality and theme toggle
```

## 💡 How It Works

- **⏱️ Clock Mechanics**: JavaScript calculates the angles for the hour, minute, and second hands based on the current time and updates them in real-time.
- **🔄 Theme Switching**: A toggle button switches between themes by adding/removing a 'dark' class from the document body.
- **🎨 CSS Variables**: Theme colors are managed through CSS custom properties (variables) for easy customization.
- **📱 Responsive Design**: The clock adjusts appropriately for various screen sizes using flexible layouts.

## 🚀 Quick Start

### 🔧 Installation

```bash
# Clone the repository
git clone https://github.com/sainikith07/Theme-Based-Clock.git

# Navigate to the project directory
cd Theme-Based-Clock

# Open the index.html file in your browser
# No build process or dependencies required!
```

### 💻 Usage

1. 🌐 Open `index.html` in your web browser
2. 🖱️ Click the "Dark mode" or "Light mode" button to switch themes
3. 👀 Watch as the clock shows the current time with smooth animations
4. 📱 Try it on different devices - fully responsive!

## 🔮 Future Enhancements

<div align="center">
  <table>
    <tr>
      <td align="center">🎨</td>
      <td><b>Additional Themes:</b> More color schemes like sunset, neon, or seasonal themes</td>
    </tr>
    <tr>
      <td align="center">🌍</td>
      <td><b>Timezone Support:</b> View time in different locations worldwide</td>
    </tr>
    <tr>
      <td align="center">⏰</td>
      <td><b>Alarm Feature:</b> Set and manage alarms with browser notifications</td>
    </tr>
    <tr>
      <td align="center">🧩</td>
      <td><b>Customizable Clock Faces:</b> Options for different clock styles and designs</td>
    </tr>
    <tr>
      <td align="center">📊</td>
      <td><b>Time Analytics:</b> Track time spent on tasks or activities</td>
    </tr>
  </table>
</div>

## 👥 Contributing

Contributions are welcome! Feel free to enhance this clock with new features or improvements.

1. 🍴 Fork the repository
2. 🌿 Create your feature branch (`git checkout -b feature/amazing-feature`)
3. 💾 Commit your changes (`git commit -m 'Add some amazing feature'`)
4. 📤 Push to the branch (`git push origin feature/amazing-feature`)
5. 🔄 Open a Pull Request

## 📝 Implementation Details

<details>
<summary>🔄 Click to see how the clock works</summary>
<br>

The clock combines several key technologies:

```javascript
// Key functions from script.js
function setTime() {
  const now = new Date();
  const seconds = now.getSeconds();
  const minutes = now.getMinutes();
  const hours = now.getHours();
  const timeInSeconds = hours * 3600 + minutes * 60 + seconds;
  
  // Calculate rotation angles for each hand
  const secondsDegrees = (seconds / 60) * 360;
  const minutesDegrees = (minutes / 60) * 360 + (seconds / 60) * 6;
  const hoursDegrees = (hours / 12) * 360 + (minutes / 60) * 30;
  
  // Apply rotations to clock hands
  secondHand.style.transform = `rotate(${secondsDegrees}deg)`;
  minuteHand.style.transform = `rotate(${minutesDegrees}deg)`;
  hourHand.style.transform = `rotate(${hoursDegrees}deg)`;
  
  // Update digital time display
  timeElement.innerHTML = `${hours % 12 || 12}:${minutes < 10 ? '0' + minutes : minutes} ${hours >= 12 ? 'PM' : 'AM'}`;
  dateElement.innerHTML = `${days[now.getDay()]}, ${months[now.getMonth()]} <span class="circle">${now.getDate()}</span>`;
}

// Theme toggle functionality
toggle.addEventListener('click', (e) => {
  document.body.classList.toggle('dark');
  toggle.innerText = document.body.classList.contains('dark') ? 'Light mode' : 'Dark mode';
});
```

The CSS uses variables for easy theme switching:

```css
:root {
  --primary-color: #000;
  --secondary-color: #fff;
  --highlight-color: #e74c3c;
}

body.dark {
  --primary-color: #fff;
  --secondary-color: #333;
}
```

</details>

## 📜 License
This project is licensed under the MIT License - see the LICENSE file for details.

## 👨‍💻 Author

<div align="center">
  <a href="https://github.com/sainikith07">
    <img src="https://github.com/sainikith07.png" width="100px;" style="border-radius:50%;"/><br />
    <sub><b>Sainikith</b></sub>
  </a>
</div>
<br/>
<div align="center">
  <a href="https://github.com/sainikith07">
    <img src="https://img.shields.io/badge/GitHub-sainikith07-181717?style=for-the-badge&logo=github"/>
  </a>
</div>

---

<div align="center">
  <h3>📌 Why Star This Repository?</h3>
  <p>If you found this clock useful or interesting, consider giving it a star! ⭐<br>
  Your support helps motivate further development and improvements.</p>
  
  <p>
    <a href="https://sainikith07.github.io/Theme-Based-Clock/"><img src="https://img.shields.io/badge/🔴%20Live%20Demo-Try%20it%20now!-blue?style=for-the-badge"/></a>
    <a href="#"><img src="https://img.shields.io/badge/⭐%20Star%20this%20repo-yellow?style=for-the-badge"/></a>
    <a href="#"><img src="https://img.shields.io/badge/🐛%20Report%20Bug-red?style=for-the-badge"/></a>
  </p>
  
  <p>© 2024 Sainikith. All Rights Reserved.</p>
</div>
