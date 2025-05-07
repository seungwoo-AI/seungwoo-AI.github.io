# Summary.md

## 📘 Overview
This summary provides a structured conceptual outline of LSTM (Long Short-Term Memory) based on core mechanisms, roles of internal components, and sequence modeling principles. It omits critical exploration and focuses on clarity and organization.

---

## 1. LSTM Architecture
- LSTM is a type of recurrent neural network designed to model sequences and long-term dependencies.
- It introduces a memory cell \( c_t \) and gating mechanisms to control information flow.

---

## 2. Core Components

### 2.1 Inputs
- \( x_t \): Input vector at time step \( t \)
- \( h_{t-1} \): Previous hidden state
- \( c_{t-1} \): Previous cell state
- \( z_t = [h_{t-1}; x_t] \): Concatenated input

### 2.2 Gates
- **Forget gate:** \( f_t = \sigma(W_f z_t + b_f) \)
- **Input gate:** \( i_t = \sigma(W_i z_t + b_i) \)
- **Candidate memory:** \( \tilde{c}_t = \tanh(W_c z_t + b_c) \)
- **Cell state update:** \( c_t = f_t \odot c_{t-1} + i_t \odot \tilde{c}_t \)
- **Output gate:** \( o_t = \sigma(W_o z_t + b_o) \)
- **Hidden state (output):** \( h_t = o_t \odot \tanh(c_t) \)

---

## 3. Weight Parameters
- Each gate has its own weight matrix: \( W_f, W_i, W_c, W_o \)
- Bias terms: \( b_f, b_i, b_c, b_o \)
- Parameters are trained via backpropagation through time (BPTT)

---

## 4. Initialization
- \( h_0 \) and \( c_0 \) are typically initialized to zero vectors.
- Weight matrices are initialized using standard methods (e.g., Xavier, He)

---

## 5. Output Usage Patterns

### 5.1 Final hidden state \( h_T \)
- Used for classification, regression, or sequence-level summarization.

### 5.2 All hidden states \( \{h_1, ..., h_T\} \)
- Used for sequence labeling or attention-based mechanisms.

### 5.3 Attention over hidden states
- \( h_t \) values are combined via attention to create a context vector.

---

## 6. Head Architectures
- **Classification:** Linear → Softmax
- **Regression:** Linear
- **Matching:** Cosine similarity or dot product

---

## 7. Terminology
- **Cell:** All computations for one time step (gates + updates)
- **Unit:** One dimension of \( h_t \)
- **Layer:** Sequence of cells applied across all time steps
- **Unrolling:** Visualization and modeling of temporal computation across steps

---

## 8. Key Properties
- Designed to handle long-range dependencies
- Mitigates gradient vanishing via additive memory updates
- Sequential by nature: cannot be parallelized across time steps

---
