# 🎓 Exam Flow — College Exam Timetable Scheduling System Using Graph Theory

**A web-based college examination scheduling system that applies Graph Coloring and the Greedy Algorithm to generate conflict-free examination timetables.**

<p align="center">
  <img src="https://img.shields.io/badge/Project-Exam%20Flow-blue?style=for-the-badge" alt="Exam Flow"/>
  <img src="https://img.shields.io/badge/Domain-Advanced%20Graph%20Theory-purple?style=for-the-badge" alt="Advanced Graph Theory"/>
  <img src="https://img.shields.io/badge/HTML-CSS-JavaScript-orange?style=for-the-badge" alt="Web Technologies"/>
</p>

## 🌐 Live Demo

**Live Website:** [Open Exam Flow](https://afthab556.github.io/Exam_TimeTable_Sheduling_System_Using_Graph_Theory/)

**GitHub Repository:** [View Source Code](https://github.com/Afthab556/Exam_TimeTable_Scheduling_System_Using_Graph_Theory)

---

## 📌 Table of Contents

* [Project Overview](#-project-overview)
* [Problem Statement](#-problem-statement)
* [Project Objectives](#-project-objectives)
* [Proposed Solution](#-proposed-solution)
* [Graph Theory Concepts](#-graph-theory-concepts-used)
* [Graph Coloring](#-graph-coloring)
* [Greedy Algorithm](#-greedy-algorithm)
* [System Features](#-system-features)
* [System Workflow](#-system-workflow)
* [Technology Stack](#-technology-stack)
* [System Architecture](#-system-architecture)
* [Example Scenario](#-example-scenario)
* [How to Use the Application](#-how-to-use-the-application)
* [Installation and Setup](#-installation-and-setup)
* [Algorithm and Complexity](#-algorithm-and-complexity)
* [Advantages](#-advantages)
* [Limitations](#-limitations)
* [Future Enhancements](#-future-enhancements)
* [Learning Outcomes](#-learning-outcomes)
* [Project Information](#-project-information)
* [License](#-license)

---

## 📖 Project Overview

Exam Flow is a web-based **College Exam Timetable Scheduling System** developed as an academic project for Advanced Graph Theory.

Creating an examination timetable manually can be challenging when multiple classes, subjects, and examination sessions must be coordinated. If students in the same class have two examinations scheduled at the same time, a timetable conflict occurs.

Exam Flow addresses this problem by representing examinations as vertices in a graph and conflicts between examinations as edges. It applies the **Graph Coloring problem** and a **Greedy Coloring Algorithm** to assign examinations to time slots while avoiding conflicts between subjects belonging to the same class.

The application provides an interactive interface for managing classes and subjects, generating examination schedules, viewing subject conflicts, and understanding how graph theory can solve a practical scheduling problem.

The project demonstrates how mathematical concepts from graph theory can be applied to real-world timetable scheduling.

## ❗ Problem Statement

Preparing a college examination timetable requires careful coordination of subjects and classes. A poorly organized timetable can assign two examinations to the same class at the same time.

Manual scheduling can become difficult because:

* Multiple classes may have examinations during the same period.
* Subjects belonging to the same class must not overlap.
* The number of available examination sessions is limited.
* Changes to classes or subjects can require timetable adjustments.
* Identifying conflicts manually can be time-consuming.

Therefore, a systematic approach is needed to organize examinations into time slots while respecting class-level conflict constraints.

## 🎯 Project Objectives

The main objectives of Exam Flow are:

1. To develop a web-based college exam timetable scheduling application.
2. To demonstrate the practical application of Graph Coloring.
3. To implement a Greedy Algorithm for assigning examinations to time slots.
4. To prevent examinations belonging to the same class from being scheduled simultaneously.
5. To provide facilities for managing classes and subjects.
6. To visualize subject relationships and examination conflicts using a conflict graph.
7. To organize examinations into morning and afternoon sessions.
8. To demonstrate the relationship between graph theory, algorithms, and scheduling optimization.
9. To provide a simple interface for generating and reviewing examination timetables.

## 💡 Proposed Solution

Exam Flow converts the examination scheduling problem into a graph-coloring problem.

The system follows these steps:

1. Collect the available classes and subjects.
2. Identify which subjects belong to each class.
3. Create a vertex for each examination subject.
4. Connect two vertices if their subjects share at least one class.
5. Apply the Greedy Coloring Algorithm to assign colors to the vertices.
6. Map each color to an examination time slot.
7. Display the resulting timetable and subject conflicts.

Subjects with the same color can be scheduled in the same time slot because they do not share a class under the system's conflict model.

This approach automates the basic scheduling process and makes conflicts easier to identify.

---

## 🧠 Graph Theory Concepts Used

### 1. Graph

A graph is a mathematical structure consisting of vertices and edges.

It is represented as:

**G = (V, E)**

Where:

* **G** represents the graph.
* **V** represents the set of vertices.
* **E** represents the set of edges connecting vertices.

In Exam Flow, the graph represents examination subjects and their conflicts.

### 2. Vertex

A vertex represents an examination subject.

For example:

* Data Structures
* Database Management Systems
* Operating Systems
* Mathematics

Each subject is represented by a node in the conflict graph.

### 3. Edge

An edge represents a conflict between two subjects.

If two subjects belong to the same class, an edge connects their vertices because students in that class cannot attend both examinations simultaneously.

For example:

If Class A studies both Data Structures and Mathematics, an edge connects these two subjects.

### 4. Adjacent Vertices

Two vertices are adjacent when an edge connects them.

In Exam Flow, adjacent vertices represent subjects that must be assigned different examination time slots.

### 5. Degree of a Vertex

The degree of a vertex is the number of edges connected to it.

A subject with a higher degree conflicts with more subjects. Such subjects may be more difficult to schedule because they have more restrictions.

### 6. Graph Coloring

Graph Coloring assigns colors to vertices so that no two adjacent vertices receive the same color.

In this project, each color represents an examination time slot.

### 7. Chromatic Number

The chromatic number of a graph, denoted by χ(G), is the minimum number of colors needed to color the graph properly.

For examination scheduling, it represents the minimum number of abstract time slots required to schedule all vertices without conflicts.

**Important:** A Greedy Coloring Algorithm produces a valid coloring, but it does not always guarantee the minimum possible number of colors.

---

## 🎨 Graph Coloring in Exam Flow

The system translates graph coloring into examination scheduling as follows:

| Graph Theory          | Exam Scheduling                   |
| --------------------- | --------------------------------- |
| Vertex                | Examination subject               |
| Edge                  | Conflict between subjects         |
| Color                 | Examination time slot             |
| Adjacent vertices     | Subjects that cannot overlap      |
| Number of colors used | Number of assigned time slots     |
| Chromatic number      | Minimum possible number of colors |

### Example

Suppose a class has three subjects:

* Data Structures
* Database Management
* Mathematics

Because all three subjects belong to the same class, they conflict with one another.

The conflict graph is a triangle.

A valid coloring would assign:

* Data Structures → Color 1
* Database Management → Color 2
* Mathematics → Color 3

All three subjects require separate time slots.

The chromatic number of this graph is 3.

However, if two subjects belong to different classes and share no students under the system's class-based conflict model, they may be scheduled in the same time slot.

This allows the scheduler to use examination sessions more efficiently.

## ⚙️ Greedy Algorithm

The Greedy Algorithm is used to assign colors to vertices.

It processes vertices one at a time and assigns each vertex the first available color that has not been assigned to any of its already-colored neighbors.

### Algorithm Steps

1. Construct the conflict graph from the subject and class assignments.
2. Determine the adjacent vertices of every subject.
3. Process subjects in the chosen order.
4. Check which colors are already used by adjacent vertices.
5. Assign the first available color.
6. Continue until all subjects are colored.
7. Convert the assigned colors into examination time slots.

### Pseudocode

```text
GREEDY-COLORING(Graph G)

    Arrange vertices in a chosen order

    FOR each vertex v in G:
        Mark all colors as available

        FOR each already-colored neighbor u of v:
            Mark color[u] as unavailable

        Assign the first available color to v

    RETURN assigned colors
```

### Why use a Greedy Algorithm?

* It is relatively simple to implement.
* It can produce a valid coloring efficiently.
* It is suitable for demonstrating graph-coloring concepts.
* It can handle changes to the set of subjects when the graph and schedule are regenerated.

The quality of the resulting schedule depends on the vertex order and the structure of the conflict graph.

---

## ✨ System Features

### 📚 Class Management

The application supports managing the classes used for examination scheduling.

Class information is used to determine which students are affected by each subject and to identify examination conflicts.

### 📖 Subject Management

Subjects can be associated with the appropriate classes.

The system uses these assignments to construct the conflict graph and determine which examinations require different time slots.

### 🗓️ Automatic Timetable Generation

The scheduler applies the Greedy Coloring Algorithm to assign subjects to time slots.

Examinations that do not conflict can share the same slot, while conflicting subjects receive different slots.

### 🕸️ Interactive Conflict Graph

The conflict graph displays subject relationships visually.

Selecting a subject node can highlight the selected subject and its conflicting neighbors, helping users understand why particular examinations cannot occur simultaneously.

### 🕘 Examination Sessions

The timetable uses two examination sessions per day:

* **Morning:** 9:00 AM – 12:00 PM
* **Afternoon:** 1:00 PM – 4:00 PM

The schedule displays examination days as Day 1, Day 2, Day 3, and so on.

### 🌓 Dark and Light Themes

The interface includes a theme toggle to switch between dark and light appearances.

### 🏫 Room Allocation

Where configured, the application can assign suitable examination rooms based on room capacities and the student requirements associated with scheduled subjects.

Room availability and capacity should be checked before using the timetable operationally.

### ✅ Validation and Conflict Information

The application provides information about subject relationships and scheduling constraints to help users review the generated timetable.

### 📤 Timetable Export

The application provides export options for obtaining a copy of the generated timetable, such as printing or saving to PDF and downloading supported tabular data.

### 💾 Browser-Based Data Storage

The application uses browser-side storage for supported saved data and preferences. This allows data to persist in the same browser when storage is available.

---

## 🔄 System Workflow

The scheduling process can be summarized as:

```text
Start
  |
  v
Load Classes and Subjects
  |
  v
Assign Subjects to Classes
  |
  v
Build the Conflict Graph
  |
  v
Apply Greedy Graph Coloring
  |
  v
Map Colors to Exam Time Slots
  |
  v
Generate the Timetable
  |
  v
Review Conflicts and Assignments
  |
  v
Export or Print the Timetable
  |
  v
End
```

### Explanation

**Step 1 — Input:** The system loads the available classes, subjects, and their assignments.

**Step 2 — Graph Construction:** Each subject becomes a vertex. An edge is created between subjects that belong to at least one common class.

**Step 3 — Coloring:** The Greedy Algorithm assigns colors so that adjacent vertices receive different colors.

**Step 4 — Slot Assignment:** Each color is mapped to an examination time slot.

**Step 5 — Timetable Generation:** The system displays the scheduled examinations grouped by day and session.

**Step 6 — Review:** Users can inspect the timetable, visualize conflicts, and export the result.

---

## 💻 Technology Stack

| Technology            | Purpose                                              |
| --------------------- | ---------------------------------------------------- |
| HTML5                 | Defines the structure of the web application         |
| CSS3                  | Provides layout, styling, and theme appearance       |
| JavaScript            | Implements application behavior and scheduling logic |
| Graph Theory          | Models examination conflicts                         |
| Graph Coloring        | Represents conflict-free time-slot assignments       |
| Greedy Algorithm      | Assigns colors to graph vertices                     |
| Browser Local Storage | Persists supported data and preferences              |
| Git and GitHub        | Source-code version control and project hosting      |
| GitHub Pages          | Publishes the static website online                  |

The application is designed to run in a modern web browser without requiring a separate backend server.

---

## 🏗️ System Architecture

Exam Flow follows a client-side web application architecture.

### Presentation Layer

The HTML and CSS provide the user interface, including class and subject controls, the timetable, theme controls, and graph visualization.

### Application Layer

JavaScript handles user interactions, data management, conflict detection, graph construction, scheduling, validation, and supported export operations.

### Graph Processing Layer

The graph-processing logic represents subjects as vertices and shared-class relationships as edges. The coloring algorithm assigns each subject a time-slot color.

### Storage Layer

Browser Local Storage can retain supported application data between visits on the same browser and device.

### Deployment Layer

GitHub Pages hosts the static application so users can access it through a web browser.

---

## 🧪 Example Scenario

Consider three classes:

* CSE S3 A
* CSE S3 B
* CSE S3 C

Suppose the subjects are assigned as follows:

| Subject             | Assigned classes   |
| ------------------- | ------------------ |
| Data Structures     | CSE S3 A, CSE S3 B |
| Database Management | CSE S3 A           |
| Operating Systems   | CSE S3 B           |
| Mathematics         | CSE S3 C           |

The resulting conflicts include:

* Data Structures conflicts with Database Management because both belong to CSE S3 A.
* Data Structures conflicts with Operating Systems because both belong to CSE S3 B.
* Database Management and Operating Systems do not conflict under the shared-class model.
* Mathematics does not conflict with the other subjects in this example.

One valid assignment is:

| Examination slot  | Subjects                               |
| ----------------- | -------------------------------------- |
| Day 1 — Morning   | Data Structures, Mathematics           |
| Day 1 — Afternoon | Database Management, Operating Systems |

This schedule avoids overlapping examinations within the same class.

The example illustrates how graph coloring allows multiple non-conflicting subjects to be scheduled simultaneously.

---

## 🚀 How to Use the Application

1. Open the Exam Flow website.
2. Review the sample classes and subjects.
3. Add or edit classes when required.
4. Add or edit subjects and associate them with their classes.
5. Generate the examination timetable.
6. Review the day-wise examination slots.
7. Open the conflict graph and select nodes to inspect subject conflicts.
8. Review available validation and room-allocation information.
9. Export or print the timetable if required.

For an accurate schedule, make sure every subject is assigned to the correct class before generating the timetable.

---

## 🛠️ Installation and Setup

### Requirements

* A computer with a modern web browser.
* A copy of the project source code.
* A code editor such as Visual Studio Code or Cursor (optional).

### Run Locally

**Option 1 — Open the HTML file**

1. Download or clone this repository.
2. Extract the downloaded archive if necessary.
3. Locate `index.html`.
4. Open `index.html` in a modern web browser.

**Option 2 — Use a code editor**

1. Open the project folder in Visual Studio Code or Cursor.
2. Locate `index.html`.
3. Open the file in a browser or use a local development extension such as Live Server if appropriate.

No package installation or backend setup is required for a purely static version of the application.

### Clone the Repository

```bash
git clone https://github.com/Afthab556/Exam_TimeTable_Scheduling_System_Using_Graph_Theory.git
```

Navigate to the downloaded project folder and open `index.html`.

---

## 📊 Algorithm and Complexity

Let:

* \(V\) be the number of subject vertices.
* \(E\) be the number of conflict edges.

### Graph Construction

The graph is constructed by checking which subjects share classes.

The exact construction cost depends on the implementation and how subject-to-class assignments are stored.

### Greedy Coloring

With an adjacency-list representation and a suitable implementation, greedy coloring can be implemented in approximately:

$$
O(V+E)
$$

time for a fixed vertex order, when checking the colors of each vertex's neighbors uses an efficient representation and the number of colors is suitably bounded.

If the implementation sorts vertices by degree before coloring, sorting adds a cost of approximately:

$$
O(V\log V)
$$

The actual runtime depends on the data structures and implementation details.

### Optimality

Greedy coloring provides a proper coloring when implemented correctly, but it does not always find the chromatic number.

Finding the minimum number of colors for a general graph is computationally difficult. The Greedy Algorithm is used here as a practical heuristic for generating a valid timetable.

---

## ✅ Advantages

* Automates basic college examination scheduling.
* Demonstrates a practical application of Advanced Graph Theory.
* Reduces manual effort in identifying class-level examination conflicts.
* Makes subject relationships easier to understand through graph visualization.
* Allows non-conflicting subjects to share examination slots.
* Provides a simple web-based interface.
* Supports day-wise scheduling and defined examination sessions.
* Helps students understand the relationship between vertices, edges, colors, and time slots.
* Can be extended with additional scheduling constraints in future versions.

---

## ⚠️ Limitations

The current project focuses on a simplified college examination scheduling problem.

* It models conflicts primarily through shared class assignments.
* It does not automatically account for every possible real-world constraint, such as individual student enrollment across different classes.
* A Greedy Algorithm does not guarantee the globally optimal timetable.
* Room allocation requires suitable room data and does not necessarily solve all room-capacity or simultaneous-usage constraints.
* Browser-based storage is local to the browser and is not a shared database across multiple users.
* The application is a demonstration project and should be validated thoroughly before being used for official examinations.
* Teacher availability, invigilator assignments, accessibility requirements, and other institutional rules may require additional implementation.

---

## 🔮 Future Enhancements

Potential improvements include:

1. **Advanced Optimization:** Compare different vertex-ordering strategies to reduce the number of examination slots.
2. **Student-Level Conflicts:** Identify overlaps based on actual student subject registrations.
3. **Room Scheduling:** Prevent room double-booking and consider seating capacity for every scheduled examination.
4. **Teacher and Invigilator Allocation:** Add availability constraints for staff.
5. **Database Integration:** Store classes, subjects, and timetables in a centralized database.
6. **Authentication:** Introduce administrator and staff accounts.
7. **PDF Reports:** Generate formatted official timetable reports.
8. **Multiple Algorithms:** Compare Greedy Coloring with other graph-coloring heuristics.
9. **Schedule Editing:** Allow manual adjustments followed by automatic conflict validation.
10. **Analytics Dashboard:** Display the number of examinations, time slots, conflicts, and colors used.
11. **Mobile Responsiveness:** Improve usability on phones and tablets.
12. **Automated Testing:** Test the coloring algorithm against a range of conflict graphs.

---

## 🎓 Learning Outcomes

This project demonstrates the practical application of mathematical and computational concepts, including:

* Graph representation using vertices and edges.
* Identification of adjacent vertices.
* Construction of conflict graphs.
* Graph Coloring and the chromatic number.
* Greedy algorithm design and implementation.
* Translating a real-world problem into a graph model.
* Client-side web development using HTML, CSS, and JavaScript.
* Data validation and visualization.
* Version control and project hosting with GitHub.
* Understanding the difference between a valid solution and an optimal solution.

The project provides a practical example of how graph theory can be used to model and solve scheduling problems.

---

## 📁 Project Information

**Project Name:** Exam Flow

**Project Type:** Academic Web Application

**Subject Area:** Advanced Graph Theory

**Problem Domain:** College Examination Timetable Scheduling

**Core Algorithm:** Greedy Graph Coloring

**Technologies:** HTML, CSS, JavaScript

**Hosting:** GitHub Pages

**Developed for:** Academic learning and demonstration

---

## 📜 License

This project is intended for educational and academic purposes.

If you plan to distribute the source code publicly, consider adding an appropriate open-source license, such as the MIT License, after confirming that you have the right to license all included code and assets.

---

## 🙌 Acknowledgement

Exam Flow was developed to demonstrate how graph theory concepts can be applied to practical scheduling problems.

The project connects theoretical concepts from Advanced Graph Theory with an interactive web application, helping make graph coloring and greedy scheduling easier to visualize and understand.

**If you find this project useful for learning, studying graph theory, or understanding examination scheduling, feel free to explore the source code and build upon the concepts.**

---

*Exam Flow — Making examination scheduling easier through Graph Theory.*
