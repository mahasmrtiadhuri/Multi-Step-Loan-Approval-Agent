# Multi-Step-Loan-Approval Agent

A compliance-driven conversational AI agent that guides users through a structured loan approval process. The system is designed for financial services use cases where deterministic behavior, controlled dialogue flow, and compliance constraints are required.

## What This Project Does

This project implements a loan approval chatbot that helps customers move through a step-by-step loan application journey. The agent handles eligibility checks, document collection, loan type selection, and approval-related interactions using a predefined, rule-based conversational flow.

Unlike open-ended chatbots, this agent follows a controlled state-based journey to ensure consistent and compliant responses suitable for regulated financial environments.

## How It Works

- The conversational flow is defined as a series of states and transitions
- User inputs are evaluated at each step to determine the next action
- Business rules and compliance constraints guide responses
- The agent avoids speculative or advisory language outside defined rules
- The application runs locally and exposes a conversational interface

## Requirements

- Python 3.12 or later
- `uv` package manager
- Environment variables configured via `.env`
