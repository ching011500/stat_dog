# 📘 Chapter 3：Some Basic Concepts of Statistics

## ✅ 章節大綱

1. Infinite Population Case（無限母體情況）  
2. Finite Population Case（有限母體情況）  
3. Sampling Distributions（抽樣分配）  
4. Covariance and Correlation（共變異與相關）  
5. Estimation（參數估計）

---

## 🔹 3.1 Infinite Population Case

### 📌 母體平均數（Population Mean）
$$
\mu = E(y) = \sum y \cdot p(y)
$$

### 📌 母體變異數（Population Variance）
$$
\sigma^2 = V(y) = E[(y - \mu)^2] = \sum (y - \mu)^2 \cdot p(y)
$$

### 📌 標準差（Standard Deviation）
$$
\sigma = \sqrt{\sigma^2}
$$

---

### 📌 樣本統計量（Sample Statistics）

- 樣本平均：
  $$
  \bar{y} = \frac{1}{n} \sum_{i=1}^{n} y_i
  $$

- 樣本變異數與標準差：
  $$
  s^2 = \frac{1}{n - 1} \sum_{i=1}^{n} (y_i - \bar{y})^2
  \quad , \quad s = \sqrt{s^2}
  $$

---

### 📌 樣本平均的性質（Properties of Sample Mean）

- 不偏性：
  $$
  E(\bar{y}) = \mu
  $$

- 變異數：
  $$
  Var(\bar{y}) = \frac{\sigma^2}{n}
  $$

- 無偏估計量：
  $$
  \widehat{Var}(\bar{y}) = \frac{s^2}{n}
  $$

---

## 🔹 3.2 Finite Population Case

### 🟦 放回、等機率抽樣（Equal Probability, With Replacement）

#### 📌 抽樣設定

- 每個元素的抽中機率為：
  $$
  \delta_i = \frac{1}{N}
  $$
- 抽樣樣本記為：
  $$
  y_1, y_2, \dots, y_n
  $$

---

#### 📌 抽樣估計量（Estimate）

- 母體總量 $\tau$ 的不偏估計量為：
  $$
  \hat{\tau} = N \cdot \bar{y}
  $$

---

#### 📌 期望值與變異數（Properties）

- **期望值**：
  $$
  E(\hat{\tau}) = E(N \bar{y}) = N \cdot E(\bar{y}) = N \mu = \sum_{i=1}^{N} u_i
  $$

- **變異數（母體變異數已知）**：
  $$
  Var(\hat{\tau}) = V(N \bar{y}) = N^2 \cdot \left( \frac{N - n}{N - 1} \right) \cdot \frac{\sigma^2}{n}
  $$

---

#### 📌 無母體變異數時的估計（Estimation of Variance）

- 使用樣本變異數 $s^2$ 作為替代，估計變異數為：
  $$
  \widehat{Var}(\hat{\tau}) = N^2 \cdot \left( \frac{N - n}{N - 1} \right) \cdot \frac{s^2}{n}
  $$

- 若展開 $s^2$：
  $$
  \widehat{Var}(\hat{\tau}) = N^2 \cdot \left( \frac{N - n}{N - 1} \right) \cdot \frac{1}{n(n - 1)} \sum_{i=1}^{n} (y_i - \bar{y})^2
  $$

---

### 🟨 放回、不等機率抽樣（Unequal Probability, With Replacement）

- 每個 $\delta_i$ 不同，估計量：
  $$
  \hat{\tau} = \frac{1}{n} \sum_{i=1}^{n} \frac{y_i}{\delta_i}
  $$

- 無偏變異數估計式：
  $$
  \widehat{Var}(\hat{\tau}) = \frac{1}{n(n-1)} \sum_{i=1}^{n} \left( \frac{y_i}{\delta_i} - \hat{\tau} \right)^2
  $$

---

### 🟧 不放回、等機率抽樣（Equal Probability, Without Replacement）

#### 📌 抽樣設定

- 母體為 $u_1, u_2, \dots, u_N$
- 抽出 $n$ 個樣本，記為 $y_1, y_2, \dots, y_n$
- 抽樣方式為：**不放回（without replacement）**

---

#### 📌 包含機率（Inclusion Probability）

- 定義 $\pi_i = P($第 $i$ 個元素 $u_i$ 被抽中$)$
- 記得 $\delta_i$ 是在一次抽樣中 $u_i$ 被抽中的機率，但現在抽樣是多次進行，因此用平均機率 $\pi_i / n$ 替代

- 經由組合計數可得：
  $$
  \pi_i = \frac{1}{\binom{N}{n}} \cdot \binom{N-1}{n-1} = \frac{n}{N}
  $$

---

#### 📌 抽樣估計量（Estimator）

- 使用不偏估計量為：
  $$
  \hat{\tau} = \sum_{i=1}^{n} \frac{y_i}{\pi_i}
  $$

- 由於 $\pi_i = \dfrac{n}{N}$，因此：
  $$
  \hat{\tau} = \sum_{i=1}^{n} \frac{y_i}{\pi_i} = \sum_{i=1}^{n} \frac{y_i \cdot N}{n}
  $$

---

### 🟥 不放回、不等機率抽樣（Unequal Probability, Without Replacement）

- 使用 $\pi_i$ 為單位抽中機率，估計量：
  $$
  \hat{\tau} = \sum_{i=1}^{n} \frac{y_i}{\pi_i}
  $$

- 變異數：需計算 $\pi_{ij}$  

---

### 📋 抽樣方式與估計量對照表


| 抽樣方式             | 抽樣估計量 $\hat{\tau}$                          | 變異數估計 $\widehat{Var}(\hat{\tau})$ |
|----------------------|--------------------------------------------------|-----------------------------------------|
| A. 放回，等機率       | $N \cdot \bar{y}$                                | $N^2 \cdot \left( \dfrac{N - n}{N - 1} \right) \cdot \dfrac{s^2}{n}$ |
| B. 放回，不等機率     | $\dfrac{1}{n} \sum \dfrac{y_i}{\delta_i}$        | $\dfrac{1}{n(n - 1)} \sum \left( \dfrac{y_i}{\delta_i} - \hat{\tau} \right)^2$ |
| C. 不放回，等機率     | $\sum \dfrac{y_i}{n/N}$                          | $N^2 \cdot \left( \dfrac{N - n}{N - 1} \right) \cdot \dfrac{s^2}{n}$ |
| D. 不放回，不等機率   | $\sum \dfrac{y_i}{\pi_i}$                        | 無封閉式公式，實務中常用 bootstrap 估計 |

## 🔹 3.3 Sampling Distributions（抽樣分配）

- 抽樣分配：樣本統計量的機率分配
- 樣本平均的抽樣分配：
  $$
  E(\bar{y}) = \mu, \quad Var(\bar{y}) = \frac{\sigma^2}{n}
  $$

---

## 🔹 3.4 Covariance and Correlation（共變異與相關）

- **共變異數**：
  $$
  Cov(y_1, y_2) = E[(y_1 - \mu_1)(y_2 - \mu_2)]
  $$

- **相關係數**：
  $$
  \rho = \frac{Cov(y_1, y_2)}{\sigma_1 \cdot \sigma_2}, \quad -1 \leq \rho \leq 1
  $$

---

## 🔹 3.5 Estimation（估計）

- 母體參數：$\theta$，估計量：$\hat{\theta}$

### ✅ 性質

1. **不偏性**：
   $$
   E(\hat{\theta}) = \theta
   $$

2. **最小變異性**：
   $$
   Var(\hat{\theta}) \text{ 越小越好}
   $$

---

### 📦 信賴區間估計（Confidence Interval）

- 當估計量為常態分配，設估計誤差界限為 $B$，有：
  $$
  P(|\hat{\theta} - \theta| < B) = 1 - \alpha
  $$

- 其中：
  $$
  B = z_{\alpha/2} \cdot \sigma_{\hat{\theta}}
  $$

- 信賴區間：
  $$
  P[\hat{\theta} - B < \theta < \hat{\theta} + B] = 1 - \alpha
  $$

---

