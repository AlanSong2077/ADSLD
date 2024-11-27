# **ADSLD: A General Framework for Solving Large-Scale Linear Programming Problems in Multi-Order Fulfillment Scenarios**

Welcome to the **ADSLD** repository! This project introduces a groundbreaking framework for efficiently solving large-scale linear programming problems in multi-order fulfillment scenarios, leveraging **Lagrangian Relaxation**, **duality principles**, and **arbitrary decomposition**.

---

## 📘 **Overview**

This repository provides an implementation of the **Arbitrary Decomposition Supergradient Method Based on Lagrangian Relaxation and Duality (ADSLD)**. With the rapid growth of e-commerce, businesses face unprecedented challenges in processing millions of orders daily while managing fulfillment for diverse products efficiently.

**ADSLD Framework Highlights**:
- Decomposes complex optimization problems into manageable subproblems.
- Efficiently utilizes computational resources through decomposition and duality.
- Scales seamlessly to meet the demands of large-scale operations.
- Generalizes existing methods (e.g., CDSL), enabling enhanced performance.

### **Why Use ADSLD?**
The framework is specifically designed to overcome the limitations of traditional optimization methods in dynamic, large-scale fulfillment scenarios by:
1. Reducing computational complexity.
2. Dynamically adapting to real-world constraints.
3. Supporting batch processing for efficient parallelization.

---

## 🚀 **Algorithm Features**

### **Key Features**
- **Lagrangian Relaxation**  
  Simplifies constraints with Lagrangian multipliers to transform complex optimization into smaller subproblems.  

- **Duality Principles**  
  Leverages dual optimization for improved computational efficiency.  

- **Arbitrary Decomposition**  
  Enables custom decomposition strategies to balance trade-offs between time and space.  

- **Scalable Design**  
  Supports real-world fulfillment scenarios involving millions of variables and constraints.

### **Unique Advantages**
- **Batch Processing**: Processes subproblems in manageable batches, reducing memory overhead.
- **Iterative Refinement**: Improves solution quality through supergradient-based Lagrangian multiplier updates.
- **Versatile Applications**: Applicable across industries requiring large-scale linear programming, such as logistics, supply chain, and e-commerce.

---

## 🔧 **Code Description**

The code implementation is modular, making it easy to adapt or extend. Below are the primary components:

### **1. Random Data Initialization**
Simulates realistic fulfillment scenarios with:
- Randomized cost vectors, constraints, and matrices.
- Flexible configurations for problem scale (number of items, methods, facilities, etc.).

### **2. Lagrangian Relaxation Problem Definition**
Uses the **CPLEX solver** and **Pulp library** for linear programming:
- Models the primary objective function (e.g., minimizing costs).
- Defines constraints (e.g., inventory, order fulfillment).

### **3. Supergradient Optimization**
Iteratively updates Lagrangian multipliers to:
- Handle relaxed constraints.
- Improve solution feasibility and quality.

### **4. Performance Evaluation**
Assesses:
- Convergence behavior.
- Solution quality (objective value).
- Scalability (execution time and resource usage).

---

## 🛠️ **Setup and Usage**

### **1. Prerequisites**
Before running the framework, ensure the following:
- **Python**: Version 3.8 or later.
- **CPLEX Solver**: For high-performance optimization.
- **Pulp Library**: For modeling LP problems.

### **2. Installation**
```bash
# Clone the repository
git clone https://github.com/your-username/adsld-framework.git
cd adsld-framework

# Install dependencies
pip install -r requirements.txt
```

### **3. Running the Code**
Run the main solver:
```bash
python adsld_solver.py --mode original
```
For batch-based optimization:
```bash
python adsld_solver.py --mode batch --batch_size <batch_size>
```

### **4. Example Workflow**
- **Input**: Simulated multi-order data (in JSON/CSV).  
- **Output**: Optimal or near-optimal solutions stored as `.csv`.

---

## 📊 **Theoretical Insights**

### **Optimization Model**
The core problem is modeled as a linear program:
\[
\text{Minimize: } \langle C, X \rangle
\]
Subject to:
1. **Order Constraints**: \( A'X = b' \)  
2. **Inventory Constraints**: \( E'X \leq d \)  
3. **Feasibility**: \( 0 \leq X \leq 1 \)

### **Complexity Analysis**
- **Time Complexity**:  
  \( O(J \cdot |Q| \cdot (|M|)^{3.5} \cdot L) \)  
- **Space Complexity**:  
  \( O(N + |A| + |E| + |b| + |d|) \)  

### **Convergence and Scalability**
1. **Convergence**: Achieved through iterative multiplier updates.  
2. **Scalability**: Designed to handle up to tens of millions of variables efficiently.

---

## 🔬 **Performance Evaluation**

### **Key Metrics**
1. **Optimal Value**: Measures cost efficiency.  
2. **Constraint Satisfaction**: Evaluates adherence to constraints.  
3. **Execution Time**: Assesses computational efficiency.  

### **Empirical Results**
- **Scalability**: Demonstrated efficient handling of large-scale datasets.  
- **Convergence**: Achieves near-optimal solutions within acceptable iterations.  
- **Flexibility**: Adapts to varying problem scales and computational resources.  

---

## 🛡️ **Contributions**

We welcome all contributions! To contribute:
1. **Fork** the repository.
2. **Create a new branch**:
    ```bash
    git checkout -b feature-name
    ```
3. **Commit and push changes**:
    ```bash
    git commit -m "Add feature"
    git push origin feature-name
    ```
4. **Submit a pull request** on GitHub.

---

## ✉️ **Contact**

For questions, feedback, or support:
- **Yinsheng Song**: [yson6207@uni.sydney.edu.au](mailto:yson6207@uni.sydney.edu.au)


### **Tools**
1. IBM CPLEX Optimizer: [Documentation](https://www.ibm.com/docs/en/icos)  
2. Pulp Library: [GitHub](https://github.com/coin-or/pulp)

