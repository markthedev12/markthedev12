# Engineering roadmap

This is planned work, not a list of shipped capabilities.

## 1. Reliable Python tools

Start with IAM Access Review Bot: escape imported HTML, test rule boundaries,
validate CSV/JSON, and model explicit system/group pairs. Keep rule evaluation
separate from file loading and report rendering. Accept a review date for
repeatable historical reviews. Then add structured JSON output.

Completion: a fresh checkout runs the demo and tests without AWS credentials;
invalid inputs produce actionable errors; documentation states limitations.

Next, separate AWS collection from security checks. API failures must produce
UNKNOWN rather than fabricated passes or failures. Test denied, empty,
paginated, and multi-region results with SDK stubs before expanding audit claims.

## 2. Complete one full-stack access workflow

CloudAccess Portal currently contains an early FastAPI backend.

1. Choose managed identity or maintained password hashing; replace the SHA-256 helper before handling real accounts.
2. Define request, approval, expiry, and audit-event models with database migrations.
3. Enforce requester/reviewer roles, ownership, and no self-approval in the API.
4. Build Next.js requester and reviewer screens with loading, empty, and error states.
5. Test unauthorized object access, conflicting decisions, and invalid transitions.

Use a modular FastAPI application and PostgreSQL. Transactions and database
constraints protect state across concurrent requests. Keep policy rules outside
HTTP handlers so they can be tested independently. Introduce a worker for
background tasks; defer microservices until a demonstrated need exists.

Completion: one documented, browser-verified request-to-decision journey with
fictional seed data and API integration tests.

## 3. Add a bounded AI review assistant

The assistant summarizes requests and explains policy evidence. It cannot approve
requests, grant access, execute tools, or change policies. Use minimized fictional
data in public demos, a provider interface, and a deterministic local fake.

Validate structured output and policy source references. Maintain an evaluation
set for unsupported recommendations, missing evidence, prompt injection,
malformed output, timeouts, and provider failures. Set token/cost budgets and
provide a non-AI fallback. Deterministic policy rules remain authoritative.

Completion: measured evaluation results and documented failure behavior, not just
a successful prompt demonstration.

## 4. Reproducible cloud demo

Proposed deployment: containerized FastAPI on ECS Fargate, private RDS, Secrets
Manager, scoped IAM, Terraform, and GitHub Actions with OIDC. Compare frontend
hosting options and costs before deployment. Start locally.

Completion: passing tests/builds, TLS, structured logs, alarms, deployment and
teardown instructions, rollback, and a restore exercise. Never use employer or
patient data in demos. A deployment remains a separately reviewed action.

## 5. Evidence and learning

Each milestone needs a small PR, meaningful tests, architecture decisions, and a
runnable example. Before merging, explain its data flow, trust boundary,
invariant, failure case, and closest alternative. Change a test fixture, predict
the result, then verify it. AI-assisted work still requires understanding and
ownership.

Keep earlier labs as learning history. Feature projects when implementation,
tests, and documentation support their claims. Educational security findings do
not establish regulatory compliance.
