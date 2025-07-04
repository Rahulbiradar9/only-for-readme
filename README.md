# Web3SSH-Ascendant: AI-Powered Dispute Resolution for Web3

# 🤖 AI-Assisted Freelance Escrow dApp

This is a decentralized freelance escrow platform that combines **blockchain smart contracts** with **AI/ML-powered validation** to ensure fair and intelligent handling of freelance payments—especially for software and media-related projects.

---

## 💡 Problem

Traditional smart contracts lack the ability to handle **subjective evaluations**, such as:

- Determining code quality
- Checking if project deliverables are complete
- Evaluating media (designs, videos, audio) for requirement fulfillment

---

## 🛠️ Solution

This platform uses a hybrid approach:

- **Smart Contracts (Solidity + MetaMask)** for fund escrow, milestones, and automated payments
- **Vertex AI (GCP)** for evaluating **GitHub repos** (for software projects)
- **Custom ML Models** for evaluating **media assets** (images, video, audio)
- **AI/ML-generated completion percentage** used to decide payout conditions

---

## ⚙️ Architecture

### Frontend
- Built with React/Next.js
- Integrates with MetaMask
- Displays:
  - Contract status
  - Progress
  - Balances
  - Evaluation results

### Smart Contract (Hardhat / Solidity)
- Holds escrow funds
- Encodes rules:
  - Auto-payment on full/partial completion
  - Cancellation rules
- Main functions:
  - `startContract()`
  - `submitWork()`
  - `evaluateWork()`
  - `releasePayment()`
  - `cancelContractByClient()`
  - `cancelContractByFreelancer()`

### AI Evaluators

#### 📁 Vertex AI (Google Cloud)
- Validates software projects by analyzing GitHub repositories
- Checks:
  - Commit history
  - Task completion
  - Issue tracking
  - Testing and documentation
- Returns `completionPercentage` and `evaluationVerdict`

#### 🎥 ML Model (Media)
- Validates deliverables in:
  - Video
  - Audio
  - Images
- Checks:
  - Requirement match
  - Format and quality
  - Visual/audio consistency
- Outputs `completionPercentage` and `pass/fail` verdict

---

## 🔄 Workflow

### Step-by-step:

1. **Contract Initialization**
   - Client sets budget, scope, milestones, and cancellation rules
   - Full funds are deposited into smart contract

2. **Freelancer Submission**
   - Code submitted via GitHub (software)
   - Media uploaded (audio, image, video)
   - Proof of work submitted via frontend

3. **AI/ML Evaluation**
   - Backend calls Vertex AI or ML model
   - Calculates `completionPercentage` and `evaluationVerdict`
   - Sends results to smart contract via off-chain oracle/backend

4. **Smart Contract Decision**
   - If work is complete → full payment
   - If cancelled midway:
     - **Client cancels** → pays 12–25% fee + partial payment based on work done
     - **Freelancer cancels** → forfeits all payment

---

## 📊 Example Scenarios

| Case                          | Completion % | Result                                                      |
|-------------------------------|--------------|-------------------------------------------------------------|
| Client cancels at 60%         | 60%          | Freelancer gets 60% of payment + 12–25% cancellation fee     |
| Freelancer cancels            | N/A          | Client refunded in full                                     |
| Full completion               | 100%         | Freelancer gets full payment                                |

---

## 🔐 Security & Integration

- Off-chain backend or Chainlink Functions used to fetch AI evaluation securely
- Signed data or on-chain verification prevents manipulation
- Possible IPFS integration for immutable result storage

---

## 🧩 Future Enhancements

- DAO-based dispute resolution for subjective cases
- Milestone-based progressive payments
- Support for more freelancing domains

---

## 🧠 Technologies Used

- `Solidity`, `Hardhat` – Smart contracts
- `React`, `MetaMask` – Frontend interface
- `Vertex AI (GCP)` – Software project validation
- `Custom ML (TensorFlow/PyTorch)` – Media asset evaluation
- `Chainlink Functions / Oracle` – Off-chain to on-chain bridge

---

## 📬 Contact

If you're interested in collaborating or contributing, feel free to open an issue or reach out!

