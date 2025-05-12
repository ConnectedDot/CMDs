# Beginner Frontend Assignments (HTML, CSS, JavaScript)

Welcome to your next coding challenges! Now that you've built a simple calculator, it's time to explore fun and useful real-world mini-projects that strengthen your JavaScript and DOM manipulation skills.

---

## **1. To-Do List App**

### **Project Goal**
Build a task management tool where users can:
- Add a task
- Mark it as done
- Delete it

### **What You'll Learn**
- DOM manipulation
- Arrays and loops
- Events (click, input)
- Optional: localStorage

### **Features**
- Input box to type a task
- Add button to push task into a list
- Each task shows:
  - Task text
  - "Complete" button (toggles a line-through effect)
  - "Delete" button

### **Tips**
- Use `document.createElement()` to dynamically create list items.
- Store tasks in an array to manage them better.
- Loop through your array to re-render tasks when needed.
- Use `.classList.toggle("completed")` to toggle styles.
- Optional: Use `localStorage.setItem()` and `getItem()` to persist tasks across reloads.

---

## **2. Digital Clock / Countdown Timer**

### **Project Goal**
Build a real-time clock or a countdown timer.

### **What You'll Learn**
- `Date` object
- `setInterval()`
- Time formatting

### **Features for Clock**
- Shows current time in HH:MM:SS
- Updates every second

### **Features for Countdown (Optional)**
- Input: number of seconds/minutes
- Start countdown
- Display remaining time
- "Reset" and "Pause" buttons

### **Tips**
- Use `new Date()` for real-time clock.
- Use `setInterval(() => { ... }, 1000)` to update time every second.
- Use `clearInterval()` to stop countdowns.
- Format numbers with `.padStart(2, '0')` to display 01, 02, etc.

---

## **3. Quiz App (Multiple Choice)**

### **Project Goal**
Build a quiz system that shows one question at a time and calculates the score.

### **What You'll Learn**
- Arrays and objects
- Loops and conditionals
- Event handling
- DOM updates

### **Features**
- Array of questions and answers
- Show question + 4 options
- On button click, show next question
- Show final score at the end

### **Tips**
- Create a `questions` array like:
  ```js
  const questions = [
    {
      question: "What is 2 + 2?",
      options: ["2", "3", "4", "5"],
      answer: "4"
    },
    ...
  ];