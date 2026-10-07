# Musical Instrument Frequency Analyzer

## 1. Project Overview

The **Musical Instrument Frequency Analyzer** is a beginner-friendly
mathematics project that models a simplified vibrating musical
instrument using a **two-mass spring system**.

The project uses:

-   Matrices
-   Eigenvalues
-   Eigenvectors
-   Natural frequencies
-   Vibration modes
-   Python visualization

The project is designed for a first-year B.Tech student with little or
no programming experience.

------------------------------------------------------------------------

## 2. Problem Statement

A musical instrument produces sound because parts of it vibrate.

Different vibration patterns produce different natural frequencies.

In this project, we simplify a vibrating string/instrument into a small
mass-spring system and use eigenvalues and eigenvectors to find:

-   **Natural frequencies**
-   **Vibration modes**
-   **Principal vibration patterns**

The project is a mathematical model and is not a microphone-based audio
analyzer.

------------------------------------------------------------------------

## 3. Mathematical Idea

The system is represented by:

\[ M`\ddot{x}`{=tex}+Kx=0 \]

where:

-   \(M\) = mass matrix
-   \(K\) = stiffness matrix
-   \(x\) = displacement vector

Assuming harmonic vibration gives:

\[ Kv=`\lambda `{=tex}Mv \]

where:

-   (`\lambda`{=tex}) = eigenvalue
-   \(v\) = eigenvector

The eigenvalue is related to angular frequency by:

\[ `\lambda`{=tex}=`\omega`{=tex}\^2 \]

Therefore:

\[ `\omega`{=tex}=`\sqrt{\lambda}`{=tex} \]

and the ordinary frequency is:

\[ f=`\frac{\sqrt{\lambda}}{2\pi}`{=tex} \]

### Key interpretation

**Eigenvalues → natural frequencies**

**Eigenvectors → vibration modes**

------------------------------------------------------------------------

## 4. Mathematical Model

For two identical masses:

\[ M=
```{=tex}
\begin{bmatrix}
m&0\\
0&m
\end{bmatrix}
```
\]

and:

\[ K=
```{=tex}
\begin{bmatrix}
2k&-k\\
-k&2k
\end{bmatrix}
```
\]

where:

-   \(m\) = mass in kilograms
-   \(k\) = spring stiffness in N/m

The characteristic equation is:

\[ `\det`{=tex}(K-`\lambda `{=tex}M)=0 \]

Solving this gives the eigenvalues.

------------------------------------------------------------------------

## 5. What the Project Does

The notebook performs these steps:

1.  Takes mass and spring stiffness as inputs.
2.  Builds the mass matrix.
3.  Builds the stiffness matrix.
4.  Calculates eigenvalues.
5.  Calculates eigenvectors.
6.  Converts eigenvalues into natural frequencies.
7.  Displays the mathematical calculation.
8.  Draws the vibration modes.
9.  Runs a known test case.
10. Automatically checks the expected result.

------------------------------------------------------------------------

## 6. Software and Tools

The project uses only free tools:

-   **Google Colab**
-   **Python**
-   **NumPy**
-   **Matplotlib**

No:

-   Paid APIs
-   Secret API keys
-   External databases
-   Paid software

are required.

------------------------------------------------------------------------

## 7. How to Run

### Option 1 --- Google Colab

1.  Open Google Colab.
2.  Upload `Musical_Instrument_Frequency_Analyzer.ipynb`.
3.  Run each cell from top to bottom.
4.  When asked for inputs, enter positive values.

Example:

``` text
Mass: 1
Spring stiffness: 100
```

### Option 2 --- Jupyter Notebook

Open the `.ipynb` file in Jupyter Notebook or JupyterLab and run the
cells from top to bottom.

------------------------------------------------------------------------

## 8. Known Test Case

Use:

``` text
Mass = 1 kg
Spring stiffness = 100 N/m
```

Expected eigenvalues:

\[ `\lambda`{=tex}\_1=100 \]

\[ `\lambda`{=tex}\_2=300 \]

Expected natural frequencies:

\[ f_1`\approx1.5915`{=tex}`\text{ Hz}`{=tex} \]

\[ f_2`\approx2.7566`{=tex}`\text{ Hz}`{=tex} \]

The notebook includes an automatic test that checks these values.

If the test passes, it displays:

``` text
PASS: known test case matches the expected result.
```

------------------------------------------------------------------------

## 9. Understanding the Visualization

The visualization shows the relative movement of the two masses for each
vibration mode.

### Mode 1

The masses move in a similar direction.

### Mode 2

The masses move in opposite directions.

The exact length of an eigenvector is not important. The important
information is the **relative pattern of movement**.

Changing the mass or spring stiffness changes the calculated
frequencies.

------------------------------------------------------------------------

## 10. Important Python Concepts

### NumPy array

``` python
M = np.array([[m, 0], [0, m]])
```

Creates a matrix.

### Matrix calculation

``` python
A = np.linalg.solve(M, K)
```

Solves the matrix equation needed to obtain the standard eigenvalue
problem.

### Eigenvalues and eigenvectors

``` python
eigenvalues, eigenvectors = np.linalg.eigh(A)
```

Finds the eigenvalues and eigenvectors of the symmetric matrix.

### Frequency calculation

``` python
frequency = np.sqrt(eigenvalues) / (2 * np.pi)
```

Converts eigenvalues into natural frequencies.

### Plotting

``` python
plt.plot(x, y, 'o-')
```

Displays the vibration-mode shape.

------------------------------------------------------------------------

## 11. Project Demonstration Script

You can explain the project like this:

> "Our project models a simplified vibrating musical instrument using a
> two-mass spring system. We represent the physical system using mass
> and stiffness matrices. We then solve the eigenvalue problem. The
> eigenvalues give the natural frequencies, while the eigenvectors give
> the corresponding vibration modes. The visualization allows us to see
> these vibration patterns, and changing the mass or stiffness changes
> the results."

------------------------------------------------------------------------

## 12. Limitations

This is a simplified mathematical model.

It does **not** directly:

-   Record sound from a microphone
-   Identify a real instrument from audio
-   Perform FFT-based audio analysis
-   Reproduce the complete physics of a real musical instrument

A future version could add an audio-frequency analyzer using an FFT and
compare measured frequencies with the mathematical model.

------------------------------------------------------------------------

## 13. Project Flow

``` text
Input Mass + Stiffness
        ↓
Build M and K matrices
        ↓
Solve Eigenvalue Problem
        ↓
Find Eigenvalues
        ↓
Calculate Natural Frequencies
        ↓
Find Eigenvectors
        ↓
Visualize Vibration Modes
        ↓
Validate with Known Test Case
        ↓
Demo and Explain
```

------------------------------------------------------------------------

## 14. AI Completion Route

The recommended workflow is:

**Understand → AI Vibe Code → Validate → Customise → Document → Demo**

### Understand

Learn what matrices, eigenvalues, eigenvectors, and vibration modes
mean.

### AI Vibe Code

Use AI to help generate and explain small pieces of Python code.

### Validate

Run the known test case and check the expected frequencies.

### Customise

Change the mass, stiffness, labels, and visualization.

### Document

Explain the mathematical model, method, results, and limitations.

### Demo

Show the input, calculation, eigenvalues, frequencies, and changing
vibration modes.

------------------------------------------------------------------------

## 15. Final Learning Outcome

After completing this project, you should be able to explain:

1.  What a mass matrix is.
2.  What a stiffness matrix is.
3.  What an eigenvalue means in vibration analysis.
4.  What an eigenvector represents.
5.  How eigenvalues are converted into natural frequencies.
6.  How vibration modes are visualized.
7.  How changing physical parameters changes the mathematical result.
