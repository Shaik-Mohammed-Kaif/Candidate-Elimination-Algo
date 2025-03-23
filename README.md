#  **Candidate Elimination Algorithm - Full Explanation, Formula & Code**

## 🔹 **Introduction**
The **Candidate Elimination Algorithm** is a **Supervised Learning** algorithm used in **Concept Learning**.  
It finds the **most specific hypothesis (S)** and the **most general hypothesis (G)** by iterating over training examples.

---

##  **Formula for Candidate Elimination Algorithm**

###  **Step 1: Initialization**
- **Specific Hypothesis (S)** = First **positive** training example  
- **General Hypothesis (G)** = Set of most **general hypotheses**  


### ✅ **Step 2: Process Each Training Example (X, Y)**
For each training example **(X, Y)**:
1. **If Y = "Yes" (Positive Example)**
 - Generalize **S**: Update attributes that mismatch with `'?'`
 - Remove inconsistent hypotheses from **G**  

2. **If Y = "No" (Negative Example)**
 - Specialize **G**: Replace '?' with **S’s** values for mismatched attributes  
 - Ensure **G** does not cover the negative example  

###  **Step 3: Remove Redundant Hypotheses**
- Eliminate hypotheses in **G** that are **too general** or **inconsistent**  

---

##  **Example Calculation**
### **Dataset (sample.csv)**
| Outlook | Temperature | Humidity | Wind  | Play Tennis |
|---------|------------|----------|-------|-------------|
| Sunny   | Hot        | High     | Weak  | No          |
| Sunny   | Hot        | High     | Strong| No          |
| Overcast| Hot        | High     | Weak  | Yes         |
| Rainy   | Mild       | High     | Weak  | Yes         |
| Rainy   | Cool       | Normal   | Weak  | Yes         |
| Rainy   | Cool       | Normal   | Strong| No          |
| Overcast| Cool       | Normal   | Strong| Yes         |
| Sunny   | Mild       | High     | Weak  | No          |

---

##  **Step-by-Step Execution**
### **Step 1: Initialization**
- **Specific Hypothesis (S) = First Positive Example**

- **General Hypothesis (G) = Most General Hypothesis**


### **Step 2: Processing Each Example**
| Example | Outlook | Temp | Humidity | Wind  | Play Tennis | Action |
|---------|--------|------|----------|-------|-------------|---------|
| 1       | Sunny  | Hot  | High     | Weak  | No          | Specialize G |
| 2       | Sunny  | Hot  | High     | Strong| No          | Specialize G |
| 3       | Overcast | Hot | High | Weak | Yes | No Change (First +ve Example) |
| 4       | Rainy  | Mild | High | Weak | Yes | Generalize S |
| 5       | Rainy  | Cool | Normal | Weak | Yes | Generalize S |
| 6       | Rainy  | Cool | Normal | Strong | No | Specialize G |
| 7       | Overcast | Cool | Normal | Strong | Yes | Generalize S |
| 8       | Sunny  | Mild | High | Weak | No | Specialize G |

---

##  **Final Hypotheses**
### 🔹 **Final Specific Hypothesis (S)**

### 🔹 **Final General Hypothesis (G)**
