# Ex04 Simple Calculator - React Project
## Date:21-11-2025

## AIM
To  develop a Simple Calculator using React.js with clean and responsive design, ensuring a smooth user experience across different screen sizes.

## ALGORITHM
### STEP 1
Create a React App by the command npm create vite@latest.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app simple-calculator</li>
  <li>cd simple-calculator</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, create a new file Calculator.js and define the basic structure.

### STEP 4
Plan the UI: Display screen, number buttons (0-9), operators (+, -, *, /), clear (C), and equal (=).

### STEP 5
Create a new file Calculator.css in src/ and add the styling.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 9
Test the calculator by entering numbers and operations.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM
````
import { useState } from "react";

export default function App() {
  const [input, setInput] = useState("");

  const handleClick = (value) => {
    setInput(input + value);
  };

  const calculate = () => {
    try {
      setInput(String(eval(input)));
    } catch {
      setInput("Error");
    }
  };

  const clearAll = () => setInput("");

  return (
    <div style={styles.container}>
      <div style={styles.calc}>
        <input style={styles.display} value={input} readOnly />

        <div style={styles.buttons}>
          {[
            "7","8","9","/",
            "4","5","6","*",
            "1","2","3","-",
            "0",".","=","+",
          ].map((item) => (
            <button
              key={item}
              style={styles.btn}
              onClick={() =>
                item === "=" ? calculate() : handleClick(item)
              }
            >
              {item}
            </button>
          ))}

          <button style={styles.clearBtn} onClick={clearAll}>
            CLEAR
          </button>
        </div>
      </div>
    </div>
  );
}

const styles = {
  container: {
    width: "100vw",
    height: "100vh",
    background: "#0f172a",
    display: "flex",
    justifyContent: "center",
    alignItems: "center",
  },

  calc: {
    width: "100vw",
    height: "100vh",
    background: "#1e293b",
    display: "flex",
    flexDirection: "column",
    justifyContent: "center",
    padding: "20px",
  },

  display: {
    width: "100%",
    height: "100px",
    background: "#0f172a",
    color: "white",
    fontSize: "40px",
    padding: "20px",
    border: "none",
    borderRadius: "10px",
    marginBottom: "20px",
  },

  buttons: {
    flex: 1,
    display: "grid",
    gridTemplateColumns: "repeat(4, 1fr)",
    gap: "14px",
  },

  btn: {
    background: "#334155",
    color: "white",
    border: "none",
    padding: "20px",
    fontSize: "28px",
    borderRadius: "12px",
    cursor: "pointer",
  },

  clearBtn: {
    gridColumn: "span 4",
    background: "#ef4444",
    color: "white",
    border: "none",
    padding: "22px",
    fontSize: "26px",
    borderRadius: "12px",
    cursor: "pointer",
    marginTop: "10px",
  },
};

````

## OUTPUT
<img width="1898" height="1022" alt="image" src="https://github.com/user-attachments/assets/fefa3a09-be10-4018-ad0f-91f875174134" />


## RESULT
The program for developing a simple calculator in React.js is executed successfully.
