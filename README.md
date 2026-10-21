# Loan Journey Orchestration

### A state-based conversation workflow built with Parlant.

A Python demonstration of a multi-step loan inquiry: collect applicant details, call eligibility tools, request document information, and route the conversation to the next state or a human handoff.

## Implemented flow

1. Identify the loan type.
2. Collect credit score, annual income, and requested amount.
3. Evaluate a simple eligibility rule.
4. Request document names and run simulated validation.
5. Continue the journey or direct the user to a human specialist.

## Tool boundaries

| Tool | Current implementation |
|---|---|
| `check_eligibility` | Fixed credit-score, income, and amount thresholds |
| `process_documents` | Checks filenames and a simulated invalid-data marker |
| `get_current_rates` | Returns fixed example rates |
| `get_loan_types` | Returns a static list |

The tools do not contact lenders, validate document contents, retrieve live market rates, or make actual credit decisions. Framework guidelines describe intended conversational behavior; they do not establish regulatory compliance or a production safety guarantee.

## Repository guide

`loan_approval.py` contains the tools, domain glossary, journey state transitions, agent guidelines, and asynchronous server entry point.

| Function | Responsibility |
|---|---|
| `add_domain_glossary` | Configure terms and support terminology |
| `create_loan_journey` | Define transitions and tool states |
| `main` | Start the local Parlant server and configure the agent |

## Local setup

The application imports `parlant.sdk` and `python-dotenv`. Create a Python environment and install compatible versions of those packages, then configure the model provider required by your Parlant installation.

```bash
git clone https://github.com/mahasmrtiadhuri/Multi-Step-Loan-Approval-Agent.git
cd Multi-Step-Loan-Approval-Agent
python -m venv .venv
source .venv/bin/activate
python -m pip install parlant python-dotenv
python loan_approval.py
```

Dependency versions are not locked in the current repository; SDK compatibility and provider setup need to be verified for the installed version. Use synthetic applicant data.

## Next engineering work

Extract pure business rules for unit testing; add journey-transition evaluation cases; lock a verified SDK version; replace simulated tools with explicit adapters; and distinguish preliminary eligibility from final human decisions throughout the conversation.
