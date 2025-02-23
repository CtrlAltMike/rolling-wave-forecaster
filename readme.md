# Rolling Wave Forecasting Tool

A browser-based proof-of-concept (POC) tool for Rolling Wave Forecasting designed to help agile teams refine their iteration forecasts. This tool allows users to dynamically set up a forecast table, input iteration-specific data (including iteration names, planned work in Story Points, and actual delivered Story Points for completed iterations), and update future forecasts based on historical performance.

---

## Overview

Rolling Wave Forecasting is a planning technique where detailed planning is performed for near-term iterations while longer-term iterations are kept at a higher level of estimation. As actual performance data becomes available for completed iterations, forecasts for future iterations are adjusted to reflect historical deviations. This tool uses the average error (the difference between Actual Delivered and the Initial Forecast in Story Points) from completed iterations to update future forecasts.

<img width="873" alt="image" src="https://github.com/user-attachments/assets/8ffecfc3-4366-4fc6-a7e8-1aded2eefff9" />

---

## Features

- **Dynamic Iteration Setup:**  
  - Choose the number of iterations (up to 12) for your planning horizon.
  - Customize iteration names for clarity.
  
- **Input Fields:**  
  - **Initial Forecast:** Planned work expressed in Story Points for each iteration.
  - **Actual Delivered:** Actual Story Points delivered for completed iterations.
  
- **Forecast Update:**  
  - When updated, the tool calculates the average error from completed iterations.
  - For iterations with available actual data, the Revised Forecast is set to the actual value.
  - For future iterations, the Revised Forecast is computed as:
    - **Revised Forecast = Initial Forecast + (Average Error)**
  
- **Detailed Output and Recommendations:**  
  - The tool displays the revised forecasts alongside the original inputs.
  - A detailed explanation is provided, including the calculated average error.
  - Recommendations are offered based on whether the team is consistently over- or under-performing relative to the initial forecasts.

---

## How to Use

1. **Set Up Iterations:**  
   - Enter the desired number of iterations (maximum of 12) in the provided input field.
   - Click **"Generate Table"** to create a table for data entry.

2. **Input Data:**  
   - For each iteration, modify the default iteration name if needed.
   - Enter the **Initial Forecast** (in Story Points) for each iteration.
   - For iterations that are completed, enter the **Actual Delivered** Story Points.

3. **Update Forecast:**  
   - Click the **"Update Forecast"** button.
   - The tool calculates the average error from the completed iterations.
   - Revised forecasts are computed:
     - Completed iterations display the actual delivered value.
     - Future iterations show an updated forecast (Initial Forecast adjusted by the average error).

4. **Review Outputs:**  
   - The table displays the **Revised Forecast** for each iteration.
   - An explanation is provided below the table detailing what the average error indicates and offering recommendations to improve future estimates.

---

## Potential Uses

- **Agile Release Planning:**  
  Adjust sprint or iteration estimates based on historical performance.
  
- **Capacity Planning:**  
  Refine resource allocation by understanding deviations between planned and actual outcomes.
  
- **Risk Management:**  
  Identify and mitigate risks by detecting forecast variances early in the planning process.
  
- **Continuous Improvement:**  
  Use the feedback from past iterations to adjust and improve estimation techniques over time.

---

## Getting Started

Simply open the `index.html` file in your web browser. No server setup or additional installations are required since this is a client-side tool built using HTML, CSS, and JavaScript.

---

## Contributing

Contributions to improve this tool are welcome. If you have ideas for enhancements, bug fixes, or additional features, please open an issue or submit a pull request.

---

## License

This project is open-source and distributed under the MIT License.

---

## Contact

For any questions, feedback, or support, please open an issue in the repository or contact the project maintainer.

Happy Forecasting!
