# Rolling Wave Forecasting Tool Specification

This document outlines the specifications for the Rolling Wave Forecasting Tool—a browser-based, client-side application designed to help agile teams refine their iteration forecasts by updating future estimates based on historical performance data.

---

## 1. Overview

Rolling Wave Forecasting is a planning technique in which detailed planning is performed for near-term iterations while longer-term iterations are planned at a higher level. As actual performance data becomes available, future forecasts are updated to reflect the historical deviation between planned and actual work.

This tool allows users to:
- Dynamically select the number of iterations (up to a maximum of 12).
- Modify iteration names for clarity.
- Input an **Initial Forecast** (in Story Points) representing the planned work for each iteration.
- Enter **Actual Delivered** Story Points for completed iterations.
- Compute a **Revised Forecast** by adjusting future iterations with the average error calculated from completed iterations.

---

## 2. Functional Requirements

### 2.1. Iteration Configuration
- **Iteration Count Input:**
  - Users can specify the number of iterations (minimum 1, maximum 12).
  - A control (number input) allows selection and a button ("Generate Table") creates the iteration table.
  
- **Iteration Naming:**
  - Each iteration row has an editable text field for the iteration name.
  - Default names (e.g., "Iteration 1", "Iteration 2", etc.) are provided.

### 2.2. Data Input
- **Initial Forecast:**
  - Input field for each iteration where users enter the planned work in Story Points.
  - Labeled clearly as "Initial Forecast (Story Points)".
  
- **Actual Delivered:**
  - Input field for each iteration where users enter the actual delivered work (in Story Points) for completed iterations.
  - If no actual value is provided (blank input), the iteration is considered as a future iteration.

### 2.3. Calculation of Revised Forecast
- **Error Calculation:**
  - For iterations with actual data, compute the error as:
    ```
    Error = Actual Delivered - Initial Forecast
    ```
  - Calculate the average error from all completed iterations (iterations with actual data).

- **Revised Forecast Calculation:**
  - For completed iterations (actual data is provided):  
    The Revised Forecast is set to the Actual Delivered value.
  - For future iterations (no actual data):  
    The Revised Forecast is computed as:
    ```
    Revised Forecast = Initial Forecast + Average Error
    ```
  - The tool updates the Revised Forecast column accordingly.

### 2.4. Output and Explanation
- **Revised Forecast Display:**
  - The table includes a "Revised Forecast (Story Points)" column for each iteration.
  - Completed iterations show the actual delivered value; future iterations display the forecast adjusted by the average error.
  
- **Explanation and Recommendations:**
  - After the forecast is updated, a detailed explanation is provided.
  - The explanation includes:
    - The number of completed iterations used in the calculation.
    - The calculated average error (in Story Points).
    - A description of what the revised forecast means.
  - Recommendations are provided based on the average error:
    - If the team consistently over-delivers (positive error), recommend revising the estimation upward.
    - If the team consistently under-delivers (negative error), recommend revising the estimation downward.
    - If the error is minimal, recommend maintaining current forecasting practices.

---

## 3. Non-Functional Requirements

- **Platform:**  
  - The application is fully browser-based and runs on all modern web browsers.
  
- **Performance:**  
  - All calculations are performed client-side using JavaScript with immediate feedback when the "Update Forecast" button is clicked.

- **Usability:**  
  - The interface should be intuitive, with clear labels and instructions.
  - Input fields and buttons must be easily accessible and legible on both desktop and mobile devices.

- **Maintainability:**  
  - Code should be modular and well-commented for future enhancements.
  - The design should allow for easy modifications, such as changing the maximum number of iterations.

---

## 4. User Stories

- **As an Agile Team Member:**  
  I want to enter my planned work (in Story Points) and actual performance for each iteration so that I can see how my forecasts compare to actual outcomes.

- **As a Scrum Master:**  
  I want to update future iteration forecasts based on historical deviations, so that I can improve sprint planning and adjust resource allocation.

- **As a Product Owner:**  
  I want to review revised forecasts and recommendations to understand the team's performance trends and adjust backlog priorities accordingly.

---

## 5. Example Flow

1. **Iteration Setup:**
   - The user enters "6" into the iteration count field and clicks "Generate Table".
   - A table is generated with 6 rows, each with default iteration names ("Iteration 1", "Iteration 2", ...).

2. **Data Entry:**
   - For each iteration, the user enters an Initial Forecast (e.g., 55, 60, etc.) in Story Points.
   - For completed iterations (e.g., Iterations 1-3), the user enters the Actual Delivered Story Points.

3. **Forecast Update:**
   - The user clicks "Update Forecast".
   - The tool calculates the average error from completed iterations.
   - The Revised Forecast for completed iterations is set to the actual value; future iterations are adjusted by the average error.

4. **Output and Interpretation:**
   - The tool displays the revised forecasts in the table.
   - Below the table, an explanation details the average error and its implications.
   - Recommendations are provided for adjusting future forecasts.

---

## 6. Future Enhancements

- Allow users to specify different weights for iterations when calculating the average error.
- Provide options for exporting the forecast data (e.g., CSV or PDF).
- Integrate with project management tools to automatically import historical iteration data.
- Enhance the user interface with visualizations such as charts to display forecast trends over time.

---

## 7. License

This tool is open-source and distributed under the MIT License.

---

## 8. Contact

For questions, feature requests, or contributions, please open an issue in the repository or contact the project maintainer.

Happy Forecasting!
