# SEKU ADSAP: Agent-Based Model for Substance Use Dynamics Among Kenyan University Students

## Overview

This repository contains the complete code, data, and documentation for the research paper:

**"A Hybrid Compartmental and Agent-Based Model for Predicting Substance Use Dynamics and Evaluating Intervention Strategies among University Students in Kenya: A Calibration and Simulation Study Using National Survey Data"**

**Author:** Dr. Joel Ngesa, South Eastern Kenya University

**GitHub:** [mathsJoel/seku-adsap-substance-use-model](https://github.com/mathsJoel/seku-adsap-substance-use-model)

**Journal:** Prepared for submission to *Addiction* (Impact Factor: 6.6)

## Abstract

This study develops and validates a hybrid mathematical model to predict substance use dynamics among Kenyan university students using data from the NACADA 2024 national survey (N=15,678). The model estimates the basic reproduction number ($R_0 = 2.38$) and simulates the impact of four policy interventions, projecting that a coordinated "Whole of Society" approach could reduce prevalence by 28.7%.

## Repository Contents

| Directory | Description |
|-----------|-------------|
| `code/` | Python simulation scripts |
| `data/` | Extracted NACADA parameters and simulation results |
| `figures/` | Generated figures (PNG and PDF) |
| `tables/` | Results tables in CSV and LaTeX formats |
| `manuscript/` | LaTeX source for the manuscript |
| `docs/` | Supplementary documentation |

## Requirements

- Python 3.8 or higher
- Required packages: numpy, matplotlib, pandas, seaborn, scipy

Install dependencies:
```bash
pip install -r requirements.txt

Running the Simulations
Quick Run (for testing)
bash
cd code
python simulation.py
Full Reproducible Run
bash
python run_all.py
This will:

Run all simulations (5,000 runs per scenario)

Generate all figures

Generate all tables in CSV and LaTeX formats

Results Summary
Scenario	Relative Reduction	NNT
Mandatory Accommodation	14.2%	25
Enhanced Counselling	8.5%	42
Peer Mentorship	11.3%	31
Combined Approach	28.7%	12
Key Finding
The estimated basic reproduction number $R_0 = 2.38$ (95% CI: 2.14-2.62) confirms that substance use among Kenyan university students is a self-sustaining social epidemic requiring coordinated, multi-pronged interventions.

Citation
If you use this code or data in your research, please cite:

bibtex
@software{Ngesa2026SEKU,
  author = {Ngesa, Joel},
  title = {SEKU ADSAP: Agent-Based Model for Substance Use Dynamics Among Kenyan University Students},
  year = {2026},
  publisher = {GitHub},
  url = {https://github.com/mathsJoel/seku-adsap-substance-use-model}
}
License
This project is licensed under the MIT License - see the LICENSE file for details.

Contact
Dr. Joel Ngesa
Coordinator, ADSAP Unit
Department of Mathematics and Actuarial Science
South Eastern Kenya University
Email: jngesa@seku.ac.ke
GitHub: @mathsJoel

"Transforming Arid Lands to Green: A Metaphor for Transforming Lives from Substance Abuse to Wholesome Living" — SEKU Institutional Motto

text

---

## File 2: requirements.txt (Same)
numpy>=1.21.0
matplotlib>=3.5.0
pandas>=1.3.0
seaborn>=0.11.0
scipy>=1.7.0

text

---

## File 3: LICENSE (Same as before)

```text
MIT License

Copyright (c) 2026 Dr. Joel Ngesa, South Eastern Kenya University

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
File 4: code/run_all.py (Updated with mathsJoel)
python
"""
Master script to run all simulations and generate all outputs
Dr. Joel Ngesa, South Eastern Kenya University
GitHub: mathsJoel
"""

import os
import subprocess
import sys
import glob
import shutil

print("="*70)
print("SEKU ADSAP - RUNNING COMPLETE ANALYSIS")
print("Author: Dr. Joel Ngesa (mathsJoel)")
print("="*70)

# Create directories if they don't exist
os.makedirs('../figures', exist_ok=True)
os.makedirs('../tables/latex_tables', exist_ok=True)
os.makedirs('../data/simulation_results', exist_ok=True)
os.makedirs('../docs', exist_ok=True)

# Step 1: Run simulation
print("\n[1/3] Running simulations...")
subprocess.run([sys.executable, 'simulation.py'])

# Step 2: Generate tables
print("\n[2/3] Generating tables...")
subprocess.run([sys.executable, 'generate_tables.py'])

# Step 3: Move files to appropriate folders
print("\n[3/3] Organizing output files...")

# Move figures
for f in glob.glob('*.png'):
    shutil.move(f, f'../figures/{f}')
for f in glob.glob('*.pdf'):
    shutil.move(f, f'../figures/{f}')

# Move CSV tables
for f in glob.glob('*.csv'):
    shutil.move(f, f'../tables/{f}')

# Move LaTeX table files
for f in glob.glob('*.tex'):
    if 'manuscript' not in f:
        shutil.move(f, f'../tables/latex_tables/{f}')

print("\n" + "="*70)
print("COMPLETE! All outputs organized in:")
print("  - figures/")
print("  - tables/")
print("  - tables/latex_tables/")
print("  - data/")
print("="*70)
print("\nRepository: https://github.com/mathsJoel/seku-adsap-substance-use-model")
File 5: docs/policy_brief.md (Updated with mathsJoel)
markdown
# Policy Brief: Evidence-Based Interventions for Substance Use Among Kenyan University Students

**Author:** Dr. Joel Ngesa, South Eastern Kenya University  
**Contact:** jngesa@seku.ac.ke | GitHub: @mathsJoel  
**Date:** March 2026

## Key Findings

1. **Self-Sustaining Epidemic**: Substance use has a basic reproduction number $R_0 = 2.38$, meaning each current user creates 2.38 new users.

2. **Primary Prevention is Most Effective**:
   - Mandatory Accommodation: 14.2% reduction, NNT=25
   - Peer Mentorship: 11.3% reduction, NNT=31

3. **Combined Approach is Transformative**:
   - 28.7% reduction, NNT=12
   - Would lower national rate from 26.6% to 19.0%

## Recommendations

### 1. Implement Mandatory First-Year Accommodation
- Require first-year students to live in accredited university housing
- Reduces exposure to high-risk environments during critical initiation period

### 2. Scale Up Peer Mentorship Programs
- Pair incoming students with trained senior mentors
- Creates positive peer culture and counter-narratives

### 3. Strengthen Counselling Services
- Increase counsellor-to-student ratio
- Ensure confidentiality to address stigma

### 4. Adopt Coordinated Multi-Sectoral Approach
- Engage universities, Ministry of Education, NACADA, parents, and communities
- Implement interventions as a portfolio, not in isolation

## For More Information

Full methodology, simulation code, and results are available at:
https://github.com/mathsJoel/seku-adsap-substance-use-model

---

*"Transforming Arid Lands to Green" — SEKU Institutional Motto*
File 6: docs/methodology.md (Updated with mathsJoel)
markdown
# Detailed Methodology

**Author:** Dr. Joel Ngesa, South Eastern Kenya University  
**GitHub:** [mathsJoel/seku-adsap-substance-use-model](https://github.com/mathsJoel/seku-adsap-substance-use-model)

## Model 1: SEUR Compartmental Model

### Model Equations

$$
\frac{dS}{dt} = \Pi - \beta S \frac{U}{N} - \mu S
$$
$$
\frac{dE}{dt} = \beta S \frac{U}{N} - (\sigma + \mu)E
$$
$$
\frac{dU}{dt} = \sigma E - (\gamma + \mu)U
$$
$$
\frac{dR}{dt} = \gamma U - \mu R
$$

### Basic Reproduction Number

$$
R_0 = \frac{\beta \sigma}{(\sigma + \mu)(\gamma + \mu)}
$$

### Parameter Estimation

Parameters were estimated via nonlinear least squares fitting to NACADA-reported prevalence by year of study:
- Year 1: 21.6%
- Year 2: 27.6%
- Year 3: 29.8%
- Year 4+: 28.0%

## Model 2: Agent-Based Model

### Agent Attributes

| Attribute | Values | Source |
|-----------|--------|--------|
| Sex | Male (54.2%), Female (45.8%) | NACADA Table 4.1 |
| Year | 1 (26.9%), 2 (24.3%), 3 (23.8%), 4+ (25.0%) | NACADA Table 4.1 |
| Residence | On-campus (25.4%), Off-campus (61.7%), At-home (11.9%) | NACADA Table 4.1 |
| Religiosity | Active (70%), Inactive (30%) | Calibrated from RR=0.71 |
| Trauma History | Yes (30%), No (70%) | Calibrated from OR=2.31 |

### Behavioral Rules

**Rule 1: Initiation (S → E)**
$$
P_{init} = \alpha \cdot \left(\frac{\text{User Friends}}{\text{Total Friends}}\right)^{\beta} \cdot (1 - \rho \cdot \text{Religiosity})
$$

**Rule 2: Progression (E → U)**
$$
P_{prog} = \min(1, \gamma \cdot \text{Stress} + \delta \cdot \text{Trauma})
$$

**Rule 3: Cessation (U → R)**
$$
P_{cess} = \kappa \cdot (1 + \lambda \cdot \text{Counselling})
$$

**Rule 4: Relapse (R → U)**
$$
P_{relapse} = \nu \cdot \frac{\text{User Friends}}{\text{Total Friends}} \cdot (1 - \omega \cdot \text{Religiosity})
$$

## Intervention Scenarios

| Scenario | Description | Parameter Change |
|----------|-------------|------------------|
| A | Mandatory On-Campus Accommodation | First-year students on-campus |
| B | Enhanced Guidance & Counselling | $\lambda$ increased by 40% |
| C | Targeted Peer Mentorship | $\alpha$ reduced by 30% for first-years |
| D | Combined Approach | All changes applied |

## Simulation Parameters

- Number of agents per simulation: 5,000
- Number of simulations per scenario: 1,000
- Time steps: 160 weeks (4 academic years)
- Random seed: 2026 (for reproducibility)

## Reproducibility

All code is available at:
https://github.com/mathsJoel/seku-adsap-substance-use-model
File 7: manuscript/references.bib
bibtex
@report{nacada2024status,
  author = {{National Authority for the Campaign Against Alcohol and Drug Abuse (NACADA)}},
  title = {Status of Drugs and Substance Use among University Students in Kenya, 2024},
  year = {2024},
  address = {Nairobi},
  institution = {NACADA}
}

@article{fromme2008behavioral,
  author = {Fromme, K. and Corbin, W. R. and Kruse, M. I.},
  title = {Behavioral risks during the transition from high school to college},
  journal = {Developmental Psychology},
  volume = {44},
  number = {5},
  pages = {1497-1504},
  year = {2008}
}

@article{degenhardt2016increasing,
  author = {Degenhardt, L. and others},
  title = {The increasing global health priority of substance use in young people},
  journal = {The Lancet Psychiatry},
  volume = {3},
  number = {3},
  pages = {251-264},
  year = {2016}
}

@article{christakis2007spread,
  author = {Christakis, N. A. and Fowler, J. H.},
  title = {The spread of obesity in a large social network over 32 years},
  journal = {New England Journal of Medicine},
  volume = {357},
  number = {4},
  pages = {370-379},
  year = {2007}
}

@article{vanden2002reproduction,
  author = {Van den Driessche, P. and Watmough, J.},
  title = {Reproduction numbers and sub-threshold endemic equilibria for compartmental models of disease transmission},
  journal = {Mathematical Biosciences},
  volume = {180},
  number = {1-2},
  pages = {29-48},
  year = {2002}
}

@article{grimm2006standard,
  author = {Grimm, V. and others},
  title = {A standard protocol for describing individual-based and agent-based models},
  journal = {Ecological Modelling},
  volume = {198},
  number = {1-2},
  pages = {115-126},
  year = {2006}
}

@article{watts1998collective,
  author = {Watts, D. J. and Strogatz, S. H.},
  title = {Collective dynamics of 'small-world' networks},
  journal = {Nature},
  volume = {393},
  number = {6684},
  pages = {440-442},
  year = {1998}
}
