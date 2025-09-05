# Rubiks-Cube-Solver

A fully interactive **3x3 Rubik’s Cube solver** built using **Python**, powered by **Kociemba’s Two-Phase Algorithm**, and presented with a user-friendly **Tkinter GUI**. Designed for **AeroHack 2025**, this project emphasizes accuracy, error handling, and a visual experience for cube solving.

---

## 📌 Features

- ✅ **Interactive GUI** with color-coded stickers
- 🔄 Simulates all 18 valid Rubik’s Cube moves (e.g., `U`, `D'`, `F2`)
- 🧩 Supports accurate cube modeling using 3x3 matrix per face
- 🧠 Solves scrambled cubes using **Kociemba’s optimal algorithm**
- ⚠️ Real-time input validation (ensures exactly 9 stickers per color)
- ✅ Detects **already solved cube** and skips solving
- ❌ Provides descriptive error messages for malformed input

---

## 🖼️ GUI Preview

### GUI Interface

<img width="680" height="761" alt="image" src="https://github.com/user-attachments/assets/4391b851-8568-493d-acf7-1dfde4c0bb75" />

### Already Solved Cube

<img width="667" height="762" alt="image" src="https://github.com/user-attachments/assets/86a68a89-24ef-4a5e-911d-da52aa080f86" />

### Scramble Cube with Solution

<img width="679" height="763" alt="image" src="https://github.com/user-attachments/assets/83b666af-cf1b-41e9-94a9-67515e51fa80" />


---

## 🚀 How to Run

### 1. Clone the Repo

```bash
git clone https://github.com/Jiten28/Rubiks-Cube-Solver.git
cd rubiks-cube-solver
````

### 2. Install Requirements

Make sure Python is installed (Python 3.7+), then:

```bash
pip install kociemba
```

### 3. Run the GUI App

```bash
python Rubiks_Cube_Solver.py
```

> 🖱️ Click each cube face to cycle through sticker colors and then click “Solve Cube”.

---

## 🎮 How It Works

### 🧠 Cube Representation

The cube is represented as a Python dictionary:

```python
{
  'U': [['W', 'W', 'W'], ['W', 'W', 'W'], ['W', 'W', 'W']],
  'R': [['R', 'R', 'R'], ['R', 'R', 'R'], ['R', 'R', 'R']],
  ...
}
```

Each face contains a 3x3 matrix of color strings (`W`, `Y`, `G`, `B`, `O`, `R`).

### 🔁 Move Simulation

Each legal cube move is implemented (including prime and double variants). For example:

```python
def move_U(self):
    self.rotate_face('U')
    F, R, B, L = self.state['F'][0][:], self.state['R'][0][:], self.state['B'][0][:], self.state['L'][0][:]
    self.state['R'][0] = F
    self.state['B'][0] = R
    self.state['L'][0] = B
    self.state['F'][0] = L
```
### 🎯 Solving Algorithm

* Uses the [Kociemba library](https://pypi.org/project/kociemba/)
* Converts the cube into a 54-character facelet string
* Uses the center stickers to assign correct face labels

---

## 🧪 Input & Validation

* Every color must appear exactly **9 times**
* The GUI prevents over-input or invalid structure
* If cube is already solved, it will show: `Cube is already solved ✅`

---

## 📂 File Structure

```
rubiks-cube-solver/
│
├── Rubiks_Cube_Solver.py   # Main GUI application
├── README.md              # This file
└── sample_scrambles.txt   # Demo inputs
```

---

## 💡 Sample Scramble

Input this color configuration into the GUI:

```
For face 'U':
  Row 1: Y O Y
  Row 2: W W O
  Row 3: W R Y
For face 'R':
  Row 1: B Y R
  Row 2: G G G
  Row 3: O R R
For face 'F':
  Row 1: R W O
  Row 2: B O R
  Row 3: O Y Y
For face 'D':
  Row 1: B B G
  Row 2: G Y G
  Row 3: G Y B
For face 'L':
  Row 1: R B G
  Row 2: O B O
  Row 3: W Y W
For face 'B':
  Row 1: G G B
  Row 2: W R W
  Row 3: W R O

```

---

## 👨‍💻 Author

**Jiten Kumar**

📧 work.jiten282003@gmail.com

🌐 Portfolio( jitenkumarportfolio.netlify.app )
🌐 LinkedIn ( linkedin.com/in/jiten-kumar-85a03217a )

---

