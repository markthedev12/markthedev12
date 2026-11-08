# Project directory

Projects are organized by the engineering evidence they provide. Labs and
prototypes are labeled as such; roadmaps describe future work.

| Project | Focus | What to inspect |
| --- | --- | --- |
| [IAM Access Review Bot](https://github.com/markthedev12/iam-access-review-bot) | Python and identity governance | Validated CSV/JSON, rule boundaries, reproducible dates, escaped reports and regression tests |
| [Current](https://github.com/markthedev12/current-budget) | Full-stack application source | Money/date invariants, API validation, versioned saves, D1 schema and identity boundary |
| [CloudAccess Portal](https://github.com/markthedev12/cloud-access-portal) | Early Python API prototype | Validated registration, Argon2 password storage, isolated API tests; approvals/UI/AI remain planned |
| [AWS Configuration Checker](https://github.com/markthedev12/hipaa-aws-checker) | Cloud API inspection | Offline demo, collection-failure behavior, configuration rules and documented coverage gaps |
| [EC2 DevSecOps Lab](https://github.com/markthedev12/aws-ec2-devsecops-lab) | Terraform and Python | EC2 provisioning, paginated management-port checks, IPv6/range tests |
| [RDS PostgreSQL Lab](https://github.com/markthedev12/aws-rds-secure-tier) | Database infrastructure lab | Service-managed master secret, encrypted RDS and read-only inspection; networking limitations documented |
| [Route 53 Failover Lab](https://github.com/markthedev12/aws-route53-dns-failover-terraform) | DNS availability lab | Explicit endpoint inputs, independent primary health target, manual failover verification |
| [S3 Security Lab](https://github.com/markthedev12/aws-secure-s3-lab) | Manual policy lab | Example JSON policies, exact encryption-header semantics and acceptance checks |
| [IAM Security Review Demo](https://github.com/markthedev12/iam-security-tool) | Python learning project | Fictional identity-policy checks, portable report generation and escaping tests |
| [Password Generator](https://github.com/markthedev12/python-password-generator) | Focused Python utility | Secure random sampling, CLI validation, importable function and boundary tests |

Read each repository's setup and limitations before evaluating its results.
Tests establish specific behavior, not complete security or compliance. Cloud
labs may incur costs; their validation checks do not deploy infrastructure.

For the full-stack AI/cloud/security direction, see [the roadmap](ENGINEERING_ROADMAP.md).
