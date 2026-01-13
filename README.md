# Étude des Machines Synchrones Triphasées

<div align="center">

[![Status](https://img.shields.io/badge/Status-Completed-success)](https://github.com)
[![Version](https://img.shields.io/badge/Version-1.0.0-blue)](https://github.com)
[![License](https://img.shields.io/badge/License-Academic-green)](https://github.com)

**Mini Projet ME3 - Sujet 04 | École Nationale Polytechnique (ENP)**

</div>

---

## Project Description

### Electrical Engineering Problem

The analysis of three-phase synchronous machines requires complex calculations involving multiple electrical parameters and vector diagrams. Traditional methods involve:

- **Manual calculations** of excitation current (J) based on machine characteristics
- **Graphical construction** of vector diagrams (Potier, Behn-Eschenburg, Blondel, KAPP methods)
- **Interpolation** from experimental test data (open-circuit, short-circuit, slip tests)
- **Complex relationships** between voltage, current, reactances, and electromotive forces

These calculations are time-consuming, error-prone, and difficult to visualize, making it challenging for students and engineers to understand the relationships between different electrical parameters.

### Why a Web Platform?

A web-based solution provides several advantages:

1. **Accessibility**: No installation required, works on any device with a modern browser
2. **Visualization**: Interactive animations show step-by-step construction of vector diagrams
3. **Real-time Calculation**: Instant results with automatic validation
4. **Educational Value**: Step-by-step animations help understand complex electrical concepts
5. **Cross-platform**: Works on Windows, macOS, Linux, and mobile devices
6. **No Software Dependencies**: Pure web technologies eliminate compatibility issues

This web application automates the analysis process, provides visual feedback, and serves as both a calculation tool and an educational platform for understanding synchronous machine behavior.

---

## Objectives

### Primary Objectives

1. **Automate Complex Calculations**: Implement algorithms for calculating excitation current and electrical parameters using standard methods (Potier, Behn-Eschenburg, Blondel, KAPP)

2. **Visualize Vector Diagrams**: Create interactive, animated visualizations that show the step-by-step construction of phasor diagrams

3. **Support Multiple Machine Types**: Handle both smooth-pole (cylindrical rotor) and salient-pole synchronous machines with their respective analysis methods

4. **Provide Educational Value**: Enable users to understand the relationships between electrical parameters through interactive visualizations

5. **Ensure Accuracy**: Implement validation and error-checking to ensure reliable results

### Secondary Objectives

- Create a user-friendly interface for data input and result visualization
- Support both single-phase and three-phase configurations (star/delta connections)
- Implement responsive design for various screen sizes
- Provide detailed calculation steps for transparency and learning

---

## System Overview

### Electrical System Components

The application models the following electrical system components:

1. **Synchronous Machine**: Three-phase machine with either smooth or salient poles
2. **Stator Windings**: Three-phase windings with configurable connections (star/delta)
3. **Rotor Excitation**: Field winding with adjustable excitation current (J)
4. **Load Characteristics**: Inductive, capacitive, or resistive loads with power factor
5. **Test Data**: Experimental measurements from open-circuit, short-circuit, and slip tests

### Website-Physical System Interaction

```
┌─────────────────────────────────────────────────────────┐
│                    Physical System                      │
│  ┌──────────────┐      ┌──────────────┐               │
│  │  Synchronous │      │  Test        │               │
│  │  Machine     │◄─────┤  Equipment   │               │
│  └──────────────┘      └──────────────┘               │
│         │                                              │
│         │ Experimental Data                            │
│         ▼                                              │
└─────────────────────────────────────────────────────────┘
                    │
                    │ User Input
                    ▼
┌─────────────────────────────────────────────────────────┐
│                  Web Application                        │
│  ┌──────────────┐      ┌──────────────┐               │
│  │  Data Input  │─────►│  Calculation │               │
│  │  Interface   │      │  Engine      │               │
│  └──────────────┘      └──────────────┘               │
│         │                      │                        │
│         │                      │                        │
│         ▼                      ▼                        │
│  ┌──────────────┐      ┌──────────────┐               │
│  │  Validation  │      │  Visualization│              │
│  │  & Error     │      │  & Animation  │              │
│  │  Handling    │      │  Engine       │              │
│  └──────────────┘      └──────────────┘               │
│         │                      │                        │
│         └──────────┬───────────┘                        │
│                   │                                     │
│                   ▼                                     │
│         ┌──────────────────┐                          │
│         │  Results Display │                          │
│         └──────────────────┘                          │
└─────────────────────────────────────────────────────────┘
                    │
                    │ Calculated Parameters
                    ▼
┌─────────────────────────────────────────────────────────┐
│              Electrical Parameters                       │
│  • Excitation Current (J)                                │
│  • Internal EMF (E)                                      │
│  • Load Angle (δ)                                        │
│  • Reactances (Xs, Xt, Xl, λ)                           │
│  • Power Factor                                          │
└─────────────────────────────────────────────────────────┘
```

### Data Flow

1. **Input**: User enters machine parameters and experimental test data through web forms
2. **Validation**: System validates data consistency and completeness
3. **Calculation**: JavaScript algorithms process the data using electrical engineering formulas
4. **Visualization**: Canvas API renders vector diagrams with step-by-step animations
5. **Output**: Results displayed with detailed calculation steps

---

## Technologies Used

### Electrical Engineering Tools/Software

| Tool/Software | Purpose | Usage |
|---------------|---------|-------|
| **Standard Methods** | Analysis algorithms | Potier, Behn-Eschenburg, Blondel, KAPP methods |
| **Vector Diagram Theory** | Phasor representation | Complex number calculations for vector diagrams |
| **Interpolation Algorithms** | Data processing | Linear interpolation from experimental test curves |
| **Electrical Formulas** | Parameter calculation | Reactance, EMF, excitation current calculations |

### Web Technologies

#### Frontend

| Technology | Version | Purpose |
|------------|---------|---------|
| **HTML5** | 5.0 | Semantic structure, forms, canvas elements |
| **CSS3** | 3.0 | Styling, animations, responsive layouts (Grid, Flexbox) |
| **JavaScript** | ES6+ | Business logic, calculations, state management |
| **Canvas API** | HTML5 | Vector diagram rendering and animations |

#### External Resources

| Resource | Version | Purpose |
|----------|---------|---------|
| **Google Fonts** | Latest | Typography (Playfair Display, IBM Plex Sans) |
| **Font Awesome** | 6.4.0 | Icon library for UI elements |

#### Backend/Database

- **None**: This is a client-side only application
- **No server required**: All calculations performed in the browser
- **No database**: Data stored in JavaScript variables during session

---

## Features

### Core Features

1. **Dual Machine Type Support**
   - Smooth-pole machines (cylindrical rotor)
   - Salient-pole machines (distinct poles)

2. **Multiple Analysis Methods**
   - **Potier Method** (smooth poles): Accounts for armature reaction and saturation
   - **Behn-Eschenburg Method** (smooth poles): Single reactance approach
   - **Blondel Method** (salient poles): Two-reactance method with λ and τ
   - **KAPP Method** (salient poles): Direct and quadrature axis analysis

3. **Interactive Data Input**
   - Form-based parameter entry with real-time validation
   - Support for single-phase and three-phase configurations
   - Star (Y) and Delta (Δ) connection options
   - Dynamic table management for test data points

4. **Animated Visualizations**
   - Step-by-step construction of vector diagrams
   - Interactive controls (play, pause, restart)
   - Progress indicators and step descriptions
   - Toggle visibility of individual vectors

5. **Automatic Calculations**
   - Excitation current (J) calculation
   - Internal EMF (E) determination
   - Load angle (δ) calculation
   - Reactance parameter extraction
   - Detailed calculation steps displayed

6. **Data Validation**
   - Input range checking
   - Consistency verification
   - Error messages with guidance
   - Prevention of invalid calculations

### Advanced Features

- **Responsive Design**: Adapts to desktop, tablet, and mobile screens
- **Calculation History**: View detailed steps of all calculations
- **Export Capability**: Results can be copied for documentation
- **Multi-language Support**: French interface (extensible to other languages)

---

## Website Architecture

### Architecture Diagram

```
┌─────────────────────────────────────────────────────────────┐
│                    User Interface Layer                     │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐    │
│  │   Home Page  │  │ Selection    │  │ Input Forms  │    │
│  │   (Landing)  │  │ Page         │  │ & Tables     │    │
│  └──────────────┘  └──────────────┘  └──────────────┘    │
└─────────────────────────────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────┐
│                    Presentation Layer                       │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐    │
│  │   CSS Styles │  │  Animations  │  │  Responsive  │    │
│  │   & Layouts  │  │  & Effects   │  │  Design      │    │
│  └──────────────┘  └──────────────┘  └──────────────┘    │
└─────────────────────────────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────┐
│                    Application Logic Layer                  │
│  ┌──────────────────────────────────────────────────────┐  │
│  │           jsPoleLisse.js                            │  │
│  │  • computePotier()                                   │  │
│  │  • computeBehnEschenburg()                           │  │
│  │  • drawPotierDiagramCorrect()                        │  │
│  │  • drawBehnDiagram()                                 │  │
│  │  • calculerCourantExcitationJLisse()                 │  │
│  └──────────────────────────────────────────────────────┘  │
│  ┌──────────────────────────────────────────────────────┐  │
│  │           jsPoleSaillant.js                         │  │
│  │  • calculerAlphaLambdaSaillant()                     │  │
│  │  • calculerXtXlSaillant()                           │  │
│  │  • tracerDiagrammeBlondelSaillant()                  │  │
│  │  • tracerDiagrammeKAPPSaillant()                    │  │
│  │  • calculerCourantExcitationJSaillant()             │  │
│  └──────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────┐
│                    Rendering Layer                          │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐    │
│  │  Canvas API  │  │  Vector      │  │  Animation    │    │
│  │  Rendering   │  │  Drawing     │  │  Controller   │    │
│  └──────────────┘  └──────────────┘  └──────────────┘    │
└─────────────────────────────────────────────────────────────┘
```

### Component Description

**User Interface Layer**: HTML5 structure with semantic elements, forms, and navigation

**Presentation Layer**: CSS3 for styling, animations, and responsive layouts

**Application Logic Layer**: 
- Modular JavaScript architecture
- Separate modules for each machine type
- Calculation functions for each analysis method
- Validation and error handling

**Rendering Layer**: Canvas API for vector diagram visualization with animation support

---

## Installation & Setup

### Prerequisites

- Modern web browser (Chrome 90+, Firefox 88+, Edge 90+, Safari 14+)
- JavaScript enabled
- Internet connection (only for initial font/icon loading)

### Installation Steps

1. **Download the Project**
   ```bash
   # Clone or download the repository
   git clone [repository-url]
   cd "Mini Projet ME3_ Sujet 04"
   ```

2. **Open the Application**
   
   **Option 1: Direct Opening**
   - Navigate to the project folder
   - Double-click `style.html`
   - The application opens in your default browser

   **Option 2: Local Server (Recommended)**
   ```bash
   # Using Python 3
   python -m http.server 8000
   
   # Using Node.js (if http-server is installed)
   npx http-server -p 8000
   
   # Access at http://localhost:8000/style.html
   ```

3. **Verify Installation**
   - Application loads without errors
   - All pages are accessible
   - Forms are functional
   - No console errors

### File Structure

```
Mini Projet ME3_ Sujet 04/
│
├── style.html                 # Main HTML file (entry point)
├── style (1).css             # Complete CSS stylesheet
├── jsPoleLisse.js            # Smooth-pole machine module
├── jsPoleSaillant.js         # Salient-pole machine module
├── Logo-ENP.png              # Institution logo
└── README_ME3_Sujet04.md     # Project documentation
```

---

## Usage Instructions

### Quick Start

1. Open `style.html` in a web browser
2. Click **"Commencer l'étude"** (Start Study)
3. Select machine type: **Pôle Lisse** (Smooth Pole) or **Pôle Saillant** (Salient Pole)
4. Fill in the required parameters
5. Generate the diagram
6. View results and calculate excitation current

### Detailed Workflow

#### Step 1: Machine Selection
- Choose between smooth-pole or salient-pole machine
- Each type has different analysis methods available

#### Step 2: Machine Parameters
Enter the following information:

**Basic Machine Parameters**
- Machine type: Single-phase or Three-phase
- Connection: Star (Y) or Delta (Δ) for three-phase
- Stator resistance Rs (Ω) or calculate from Req
- Frequency (Hz)
- Number of pole pairs

**Operating Conditions**
- Terminal voltage V (V)
- Armature current I (A)
- Power factor cos(φ)
- Load type: Inductive, Capacitive, or Resistive
- Operating mode: Generator or Motor

#### Step 3: Test Data Input

**Open-Circuit Test Data** (E = f(J))
- Minimum 4 points required for Potier method
- Enter pairs of values: Excitation current J (A) and Open-circuit voltage E (V)
- Data should be sorted by increasing J values

**Short-Circuit Test Data** (Icc = f(J))
- Minimum 1 point required
- Enter pairs: Excitation current J (A) and Short-circuit current Icc (A)

**Additional Tests**
- **Dewatté Test** (for Potier method): Vd, Id, Jd, cos(φ)
- **Slip Test** (for salient poles): Imax, Imin at rated voltage

#### Step 4: Generate Diagram
- Click the button for desired analysis method
- Watch the animated construction
- Review calculated parameters

#### Step 5: Calculate Excitation Current
- Click **"Calculer le courant d'excitation J"**
- Review detailed calculation steps
- Note the final excitation current value

---

## Results & Expected Outcomes

### Calculated Parameters

The application provides the following calculated outputs:

#### For Smooth-Pole Machines

**Behn-Eschenburg Method:**
- Internal EMF (E) in volts
- Load angle (δ) in degrees
- Synchronous reactance (Xs) in ohms
- Excitation current (J) in amperes
- Voltage regulation percentage

**Potier Method:**
- Potier coefficient (α)
- Potier reactance (λ) in ohms
- Reaction EMF (Er) in volts
- Excitation current (J) in amperes
- Phase angle (φ) in degrees

#### For Salient-Pole Machines

**Blondel Method:**
- Transverse EMF component (Etr) in volts
- Longitudinal EMF component (Elr) in volts
- Total EMF (E) in volts
- Angle ψ between current and EMF in degrees
- Excitation current (J) in amperes

**KAPP Method:**
- Direct-axis reactance (Xl) in ohms
- Quadrature-axis reactance (Xt) in ohms
- Load angle (δ) in degrees
- Direct current component (Id) in amperes
- Quadrature current component (Iq) in amperes
- Active power (P) in watts
- Reactive power (Q) in VAR
- Excitation current (J) in amperes

### Expected Accuracy

- **Calculation Precision**: Results accurate to 2-4 decimal places depending on parameter
- **Interpolation Accuracy**: Linear interpolation provides good accuracy for typical test data
- **Validation**: All inputs validated before calculation to prevent errors

### Use Cases

1. **Educational**: Students learning synchronous machine analysis
2. **Design**: Engineers calculating excitation requirements
3. **Verification**: Cross-checking manual calculations
4. **Research**: Analyzing different machine configurations

---

## Authors

### Development Team

| Name | Role | Email | Contributions |
|------|------|-------|---------------|
| **Loubna FERIKH** | Lead Developer | loubna.ferikh@g.enp.edu.dz | Frontend development, smooth-pole module implementation |
| **Chahrazed MERIDED** | Lead Developer | chahrazed.merided@g.enp.edu.dz | Frontend development, salient-pole module implementation |


### Project Information

- **Institution**: École Nationale Polytechnique (ENP)
- **Course**: Mini Projet ME3
- **Subject**: Sujet 04 - Étude des machines synchrones triphasées
- **Academic Year**: 2024-2025

---

## License

### Academic License

This project is developed for academic purposes as part of the Mini Projet ME3 course at École Nationale Polytechnique (ENP).

**Copyright © 2024-2025 - Mini Projet ME3 Sujet 04 Team**

### Usage Rights

- **Academic Use**: Free to use for educational and research purposes
- **Modification**: Allowed for academic projects with proper attribution
- **Distribution**: Permitted for educational purposes
- **Commercial Use**: Not permitted without explicit authorization

### Attribution

When using this project, please include:
- Reference to the original project
- Credit to École Nationale Polytechnique (ENP)
- Link to this repository (if applicable)

### Disclaimer

This software is provided "as is" without warranty of any kind. The authors and institution are not responsible for any errors or consequences resulting from the use of this application.

---

## Acknowledgments

- **École Nationale Polytechnique (ENP)** for providing the academic framework
- **Course Instructors** for guidance and technical support
- **Open Source Community** for the excellent web technologies used

---

<div align="center">

**Projet réalisé dans le cadre du Mini Projet ME3 - Sujet 04**  
**École Nationale Polytechnique (ENP)**  
**Année académique 2024-2025**



</div>
