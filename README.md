# 📘 Pomodoro Timer – Explanation

This program is a **Pomodoro Timer** built using **Tkinter** and **ttkbootstrap** to provide a clean, modern UI. The Pomodoro technique alternates between focused work sessions and short/long breaks.

---

## 🔧 1. Importing Required Modules

- **tkinter** – Used to build the GUI  
- **ttk** – Modern themed widgets  
- **messagebox** – Popup notifications  
- **ttkbootstrap** – Stylish pre-built UI theme for Tkinter  

---

## ⏳ 2. Timer Duration Settings
```python
WORK_TIME = 25 * 60
SHORT_BREAK_TIME = 5 * 60
LONG_BREAK_TIME = 15 * 60


```
## 🏗️ 3. PomodoroTimer Class Structure

The entire timer logic is wrapped inside a class.

### **Window Setup**
- Creates a 400×400 window  
- Sets title **“My Timer”**  
- Applies **simplex** theme  

---

## 🖥️ 4. UI Components

### **Label**
Displays the countdown in **MM:SS** format.

### **Start Button**
Starts the timer and disables itself to prevent multiple starts.

### **Stop Button**
Pauses the timer and re-enables the Start button. Disabled initially.

---

## 🔄 5. Timer Behavior (`update_timer` method)

This method runs every **1000 ms (1 second)**:

### ✔ **Work Phase**
- Time decreases each second  
- When it reaches **0**:
  - Pomodoro count increases  
  - Decides whether next break is:
    - **Short break** (after normal work session)
    - **Long break** (every 4 pomodoros)
  - Shows motivational popup  

### ✔ **Break Phase**
- Time decreases each second  
- When it reaches **0**:
  - Switches back to work mode  
  - Resets the work timer  
  - Shows **“Get back to work!”** popup  

---

## 🕒 6. Time Display Formatting

To extract minutes and seconds:
```
minutes, seconds = divmod(time_left, 60)
```

Displayed using:
```

"{:02d}:{:02d}".format(minutes, seconds)
```

This ensures the timer shows proper digital format (e.g., 05:09).

