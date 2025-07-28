# Takeoff Performance Calculator - Pipistrel ALPHA Trainer

![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)

An interactive and visual web-based calculator to estimate the takeoff performance of the **Pipistrel ALPHA Trainer (LSA)** aircraft.

![Screenshot of the Takeoff Performance Calculator interface](webapp_screenshot.png)

---

> ⚠️ **IMPORTANT DISCLAIMER & WARNING**
>
> This calculator is an **educational and demonstrational tool only**. **DO NOT USE IT FOR REAL-WORLD FLIGHT PLANNING.**
>
> This is an **unofficial, third-party tool**. The author is not affiliated with, endorsed by, or sponsored by Pipistrel or its parent company, Textron Aviation.
>
> The calculations are based on performance data from the following specific document:
> - **Document No.:** POH-162-00-40-001
> - **Revision:** A07
> - **Date of Issue:** June 5th, 2024
>
> Always consult the official and current **Pilot's Operating Handbook (POH)** for your specific aircraft for accurate and authoritative performance data. **Any questions regarding the application of these calculations or the use of this tool in a training context should be directed to a qualified Certified Flight Instructor (CFI).**
>
> The author assumes no liability for any decisions made or actions taken based on the use of this tool.

---

## ✨ Key Features

*   **📊 Interactive Graph:** Visualize the ground roll, 50 ft obstacle clearance distance, and available runway length in a real-time updating graphical representation.
*   **🌐 Bilingual Support:** The interface is available in both English and Spanish, with automatic browser language detection.
*   **🔢 Flexible Inputs:** Adjust all key variables: elevation, temperature, headwind/tailwind, crosswind, and runway surface type.
*   **📏 Imperial & Metric Units:** Switch between unit systems with a single click.
*   **🔬 Calculation Breakdown:** Understand how the final result is achieved with a detailed section showing each step of the calculation, from the base distance to adjustments for density, wind, and surface.
*   **📱 Responsive Design:** Fully functional on both desktop and mobile devices.
*   **🚀 Self-Contained:** Built with a lightweight stack that runs entirely in the browser, with no server-side processing or external production dependencies.

## 🛠️ Tech Stack

*   **HTML5** (Semantic)
*   **[Tailwind CSS](https://tailwindcss.com/)** for rapid, modern UI development.
*   **[Alpine.js](https://alpinejs.dev/)** for UI reactivity and application logic.

## ⚙️ How It Works (The Calculation Logic)

The calculation is based on the interpolation method from the performance charts found in the Pipistrel ALPHA Trainer POH. The process is as follows:

1.  **Base Distance (Lo):** Starts with the standard distance at Sea Level (SL) and 15°C (ISA).
2.  **Density Correction:**
    *   Interpolates the distance for the current **temperature** at sea level (Lt).
    *   Interpolates the distance for the current **elevation** at 15°C (Lh).
    *   Combines these effects (`Lh + Lt - Lo`) to get the density altitude-corrected distance.
3.  **Safety Margin:** A 10% safety margin is applied to the density-corrected distance.
4.  **Wind Adjustment:** A fixed distance is added or subtracted based on the headwind or tailwind component.
5.  **Correction Factors:** The result is then multiplied by factors for:
    *   **Runway Surface** (+20% for grass/soft field).
    *   **Crosswind** (+10% for every 5 knots of crosswind).
6.  **Final Result:** The final ground roll and 50 ft / 15 m obstacle clearance distances are displayed.

## 🚀 Running Locally

No build process is required. Simply clone or download the repository and open the `index.html` file in your web browser.

```bash
# Clone the repository
git clone https://github.com/carlosplanchon/takeoff_performance_piat.git

# Navigate to the directory
cd takeoff_performance_piat

# Open the index.html file in your preferred browser
```

## 🤝 Contributing

Contributions are welcome! If you find a bug, have a suggestion for improvement, please open an *Issue* or submit a *Pull Request*.

## 📄 License

This project is distributed under the MIT License. See the `LICENSE` file for more information.

---
*Made with ♥️ in Dolores, Soriano, Uruguay.*
