# ADSLD: A General Framework for Solving Large-Scale Linear Programming Problems in Multi-Order Fulfillment Scenarios

Welcome to the **ADSLD** repository! This project introduces a groundbreaking framework for efficiently solving large-scale linear programming problems in multi-order fulfillment scenarios, leveraging **Lagrangian Relaxation**, **duality principles**, and **arbitrary decomposition**.

---

## 📘 **Overview**

This repository provides an implementation of the **Arbitrary Decomposition Supergradient Method Based on Lagrangian Relaxation and Duality (ADSLD)**. The rapid growth of e-commerce has led to unprecedented challenges in handling millions of orders daily and managing fulfillment for a diverse range of products. ADSLD addresses these challenges by:

- Decomposing complex problems into manageable subproblems.
- Balancing computational resource utilization.
- Extending scalability and efficiency.

This framework generalizes existing methods, such as the Completely Decomposed Supergradient Method (CDSLD), to accommodate arbitrary decomposition strategies, enabling enhanced performance and adaptability in various fulfillment scenarios.

---

## 🚀 **Algorithm Features**

- **Lagrangian Relaxation**  
  Converts complex constraints into manageable subproblems using Lagrangian multipliers.  

- **Duality Principles**  
  Applies dual optimization techniques to achieve computational efficiency.

- **Arbitrary Decomposition**  
  Allows flexible decomposition strategies, balancing time and space complexities.

---

## 🔧 **Code Description**

The implementation consists of four key components:

1. **Random Data Initialization**  
   - Simulates a multi-order fulfillment environment.  
   - Handles scenarios with tens of millions of variables.  

2. **Lagrangian Relaxation Problem Definition & Solution**  
   - Configures the **CPLEX solver** and **Pulp** for mathematical modeling.  
   - Supports distributed computing for large-scale problems.  

3. **Lagrangian Multiplier Updates (Supergradient Method)**  
   - Trades space for time to derive approximate solutions.  
   - Refines solutions through multiple iterations.  

4. **Performance Evaluation**  
   - Evaluates scalability and accuracy of solutions.  

---

## 🛠️ **Setup and Usage**

### Prerequisites
- Python 3.8+
- **CPLEX Solver**: A high-performance solver for mathematical optimization.
- **Pulp Library**: For linear programming modeling.

### Installation
```bash
# Clone the repository
git clone https://github.com/your-username/adsld-framework.git

# Install required dependencies
pip install -r requirements.txt
```

### Running the Code
```bash
python adsld_solver.py --data <path_to_input_data>
```

### Input/Output Example
- **Input**: Simulated multi-order data in JSON/CSV format.  
- **Output**: Optimal or approximate solutions for the linear programming problem, stored in `.csv`.

---

## 📊 **Theoretical Insights**

### **Optimization Model**
The ADSL framework models multi-order fulfillment as a linear programming problem:

\[
\text{Minimize: } \langle C, X \rangle
\]
Subject to:
- Equality constraints \( A'X = b' \)
- Inequality constraints \( E'X \leq d \)
- Feasibility \( 0 \leq X \leq 1 \)

### **Complexity Analysis**
- **Time Complexity**: \( O(J \cdot |Q| \cdot (|M|)^{3.5} \cdot L) \), where \( J \) is the number of iterations.
- **Space Complexity**: \( O(N + |A| + |E| + |b| + |d|) \).

### **Key Algorithms**
- **Complete Decomposition Method**: For fully separable problems.
- **Arbitrary Decomposition Method**: Balances time and space complexities dynamically.

---

## 🔬 **Key Results**

1. Proven convergence and efficiency of the ADSL method.
2. Empirical results demonstrate adaptability for problems with varying scales.
3. Flexibility to incorporate distributed computing for scalability.

---

## 📂 **Repository Structure**

```plaintext
├── adsld_solver.py      # Main script for solving the problem
├── data/                # Example input datasets
├── docs/                # Documentation
├── models/              # Predefined LP models
├── requirements.txt     # Required Python packages
└── tests/               # Unit tests for the framework
```

---

## 🛡️ **Contributions**

We welcome contributions to improve and expand the framework. Please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature: `git checkout -b feature-name`.
3. Commit your changes: `git commit -m "Add feature"`.
4. Push to your branch: `git push origin feature-name`.
5. Open a pull request.

---

## ✉️ **Contact**

For inquiries or support, please contact:  
- Yinsheng Song: [yson6207@uni.sydney.edu.au](mailto:yson6207@uni.sydney.edu.au)  
- Qibang Liu: [qliu348@wisc.edu](mailto:qliu348@wisc.edu)  
- Xuewen Luo: [xluo0033@student.monash.edu](mailto:xluo0033@student.monash.edu)  

---

## 📚 **References**

1. Dantzig, G. B. "Maximization of a Linear Function of Variables Subject to Linear Inequalities" (1951).  
2. Nesterov, Y. "Primal-Dual Subgradient Methods for Convex Problems" (2009).  
3. Bertsekas, D. P. "Incremental Subgradient Methods for Large-Scale Optimization" (2015).  

For more details, please refer to the [documentation](docs/).
