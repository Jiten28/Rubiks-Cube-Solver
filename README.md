# Rubiks-Cube-Solver

A fully interactive **3x3 Rubik’s Cube solver** built using **Python**, powered by **Kociemba’s Two-Phase Algorithm**, and presented with a user-friendly **Tkinter GUI**. Designed for **AeroHack 2025**, this project emphasizes accuracy, error handling, and a visual experience for cube solving.



## 📌 Features

- ✅ **Interactive GUI** with color-coded stickers
- 🔄 Simulates all 18 valid Rubik’s Cube moves (e.g., `U`, `D'`, `F2`)
- 🧩 Supports accurate cube modeling using 3x3 matrix per face
- 🧠 Solves scrambled cubes using **Kociemba’s optimal algorithm**
- ⚠️ Real-time input validation (ensures exactly 9 stickers per color)
- ✅ Detects **already solved cube** and skips solving
- ❌ Provides descriptive error messages for malformed input


## 🖼️ GUI Preview

<img src="https://your-screenshot-link-1" alt="Rubik GUI" width="600"/>
<br>
<img src="https://your-screenshot-link-2" alt="Solution Example" width="600"/>

---

## 🚀 How to Run

### 1. Clone the Repo

```bash
git clone https://github.com/your-username/rubiks-cube-solver.git
cd rubiks-cube-solver
````

### 2. Install Requirements

Make sure Python is installed (Python 3.7+), then:

```bash
pip install kociemba
```

### 3. Run the GUI App

```bash
python RubiksCube_Solver.py
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


