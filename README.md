# Automata Finance

Automata Finance is an AI-powered SMB credit intelligence platform for loan underwriting. Small and medium-sized businesses upload financial data, and the platform generates a structured credit risk profile for loan officers with a risk score, cash-flow trends, anomaly flags, red flags, and a plain-English underwriting summary.

The goal is to make SMB credit review faster, more consistent, and easier to audit by replacing manual document review with structured financial analysis and AI-assisted risk assessment.

## Core Workflow

1. An SMB submits company information and uploads financial data, such as transaction CSVs, invoices, bank statements, or cash-flow history.
2. Automata Finance parses and stores the submitted financial data.
3. The AI analysis layer evaluates cash-flow health, detects anomalies, and identifies credit risk signals.
4. The platform generates a credit risk profile with a score, key trends, red flags, and a loan officer summary.
5. Loan officers review pending applications from a dashboard and inspect each risk assessment.
6. Audit logs preserve analysis history and timestamps for traceability.

## Core Features

- SMB onboarding and financial data upload
- Transaction parsing and storage
- AI-powered credit risk analysis
- Risk score generation
- Cash-flow trend visualization
- Red flag and anomaly detection
- Loan officer dashboard
- Application detail pages
- Audit logs for each analysis

## Tech Stack

| Layer | Technology |
| --- | --- |
| Frontend | Next.js App Router |
| Styling | Tailwind CSS |
| Database | AWS Aurora PostgreSQL |
| ORM | Prisma |
| Backend | Next.js API routes |
| AI | Anthropic Claude API |
| Auth | Clerk |
| Charts | Recharts |
| Deployment | Vercel |

## Data Model Direction

The application is designed around a relational lending workflow:

```text
companies -> applications -> transactions -> risk_assessments -> audit_logs
```

This structure supports a realistic credit review process where financial records, AI-generated assessments, and review history are connected and traceable.

## Getting Started

Install dependencies:

```bash
npm install
```

Create a `.env` file with the required environment variables:

```env
DATABASE_URL="postgresql://username:password@your-aurora-endpoint.rds.amazonaws.com:5432/database"
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY="your_clerk_publishable_key"
CLERK_SECRET_KEY="your_clerk_secret_key"
ANTHROPIC_API_KEY="your_anthropic_api_key"
```

Run the development server:

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## Development Scripts

```bash
npm run dev
npm run build
npm run start
npm run lint
```

## Suggested Build Order

1. Set up authentication and base app layout.
2. Define the Prisma schema for companies, applications, transactions, risk assessments, and audit logs.
3. Build the SMB upload form and transaction CSV parser.
4. Add the AI analysis endpoint for risk scoring and summaries.
5. Build the loan officer dashboard and application detail view.
6. Add charts, polish the UI, and deploy to Vercel.

## Project Status

Automata Finance is currently in early development. The initial Next.js project and core dependencies are in place, with the product direction focused on B2B fintech credit underwriting for SMB lending.
