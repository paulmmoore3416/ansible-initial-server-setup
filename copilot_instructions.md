# Comprehensive GitHub Copilot Instructions for Automation Architects and DevOps Engineers

Below is a comprehensive set of GitHub Copilot instructions tailored for a professional automation architect and a professional DevOps engineer specializing in GitHub. These instructions are designed to maximize Copilot's effectiveness in automating workflows, writing infrastructure-as-code (IaC), scripting deployments, managing CI/CD pipelines, and integrating with GitHub's ecosystem. They emphasize best practices, security, efficiency, and advanced techniques to leverage Copilot as a collaborative AI tool.

The instructions are divided into two sections:
1. **50 Professional Instructions**: Core, practical guidelines for everyday use, focusing on reliability, scalability, and GitHub-specific workflows.
2. **Rare and Powerful Instructions**: Advanced, niche techniques for edge cases, optimization, and high-impact scenarios that go beyond standard usage. These include prompt engineering hacks, integration with external tools, and strategic AI manipulation for complex automation.

Each instruction includes:
- **Context**: When and why to use it.
- **Detailed Steps**: How to apply it with Copilot.
- **Examples**: Sample prompts or code snippets.
- **Best Practices**: Tips to avoid pitfalls and ensure professionalism.
- **GitHub/DevOps Tie-In**: Relevance to automation and DevOps.

---

### 50 Professional Instructions

1. **Initialize IaC Templates**: When starting a new infrastructure project, prompt Copilot to generate boilerplate for Terraform or Ansible playbooks, ensuring modular structure.
   - **Steps**: Describe the cloud provider, resources, and variables; ask Copilot to "Generate a Terraform module for an AWS EC2 instance with security groups."
   - **Example**: "Create an Ansible playbook to install Docker on Ubuntu servers, including error handling."
   - **Best Practices**: Validate generated code against official docs; use version pinning for dependencies.
   - **Tie-In**: Automates server setup in projects like your Ansible initial server setup workspace.

2. **Automate CI/CD Pipelines**: Use Copilot to draft GitHub Actions workflows for build, test, and deploy cycles.
   - **Steps**: Specify triggers (e.g., push to main), jobs, and runners; prompt "Write a GitHub Actions workflow for deploying a Node.js app to Azure."
   - **Example**: Include matrix builds for multiple environments.
   - **Best Practices**: Add security scanning steps; avoid hardcoded secrets.
   - **Tie-In**: Essential for DevOps engineers managing GitHub repositories.

3. **Generate Secure Secrets Management**: Prompt Copilot to create scripts for handling secrets in GitHub Actions or Ansible.
   - **Steps**: Ask for "A bash script to retrieve secrets from GitHub Secrets and inject them into an Ansible vault."
   - **Example**: Use `gh secret list` integration.
   - **Best Practices**: Never expose secrets in prompts; use placeholders.
   - **Tie-In**: Critical for secure automation in DevOps.

4. **Debug Pipeline Failures**: When a GitHub Actions run fails, prompt Copilot to analyze logs and suggest fixes.
   - **Steps**: Paste error logs and ask "Fix this GitHub Actions error: 'npm install failed'."
   - **Example**: Copilot might suggest cache optimizations.
   - **Best Practices**: Cross-reference with GitHub's status page.
   - **Tie-In**: Speeds up DevOps troubleshooting.

5. **Create Issue Templates**: Automate GitHub issue creation with Copilot-generated templates for bug reports or feature requests.
   - **Steps**: Prompt "Generate a YAML issue template for security vulnerabilities in a DevOps repo."
   - **Example**: Include fields for severity and reproduction steps.
   - **Best Practices**: Align with GitHub's community standards.
   - **Tie-In**: Enhances collaboration in automation projects.

6. **Write Unit Tests for Automation Scripts**: Prompt Copilot to add tests to Ansible roles or Terraform modules.
   - **Steps**: Ask "Add pytest tests for this Ansible module that installs Nginx."
   - **Example**: Include mocks for external APIs.
   - **Best Practices**: Aim for 80% coverage; integrate with CI.
   - **Tie-In**: Ensures reliability in DevOps automation.

7. **Optimize Resource Usage in IaC**: Use Copilot to refactor Terraform for cost efficiency.
   - **Steps**: Provide existing code and prompt "Optimize this Terraform config for AWS to reduce costs."
   - **Example**: Suggest spot instances or auto-scaling.
   - **Best Practices**: Benchmark changes in staging.
   - **Tie-In**: Key for automation architects managing cloud infra.

8. **Automate Dependency Updates**: Prompt Copilot to create Dependabot or Renovate configs for GitHub repos.
   - **Steps**: Ask "Generate a Dependabot config for updating Ansible collections weekly."
   - **Example**: Include PR limits and labels.
   - **Best Practices**: Test updates in CI before merging.
   - **Tie-In**: Maintains security in DevOps toolchains.

9. **Generate Monitoring Dashboards**: For DevOps, prompt Copilot to create Grafana or Prometheus configs.
   - **Steps**: Specify metrics and ask "Create a Prometheus scrape config for monitoring Ansible-deployed services."
   - **Example**: Include alerts for high CPU usage.
   - **Best Practices**: Use standard exporters.
   - **Tie-In**: Integrates with GitHub Actions for deployment.

10. **Handle GitHub API Interactions**: Prompt Copilot to write scripts using the GitHub CLI or REST API.
    - **Steps**: Ask "Script to create a PR via GitHub CLI after a successful deploy."
    - **Example**: Use `gh pr create --title "Deploy complete"`.
    - **Best Practices**: Authenticate securely.
    - **Tie-In**: Automates repo management in DevOps.

11. **Refactor Legacy Automation Code**: When modernizing scripts, prompt Copilot to update Ansible 2.x to 3.x syntax.
    - **Steps**: Provide old code and ask "Migrate this Ansible playbook to use FQCNs."
    - **Example**: Change `uri` to `ansible.builtin.uri`.
    - **Best Practices**: Test migrations incrementally.
    - **Tie-In**: Essential for automation architects.

12. **Create Pull Request Templates**: Automate PR descriptions with Copilot.
    - **Steps**: Prompt "Generate a PR template for infrastructure changes."
    - **Example**: Include checklists for security reviews.
    - **Best Practices**: Enforce via branch protection rules.
    - **Tie-In**: Improves code quality in GitHub workflows.

13. **Automate Rollbacks**: Prompt Copilot to add rollback logic to deployment scripts.
    - **Steps**: Ask "Add a rollback function to this Terraform apply script."
    - **Example**: Use `terraform destroy` with conditions.
    - **Best Practices**: Include manual approval gates.
    - **Tie-In**: Critical for DevOps reliability.

14. **Generate Documentation**: For automation projects, prompt Copilot to create READMEs or wikis.
    - **Steps**: Ask "Write a README for this Ansible role that sets up a web server."
    - **Example**: Include usage examples and variables.
    - **Best Practices**: Keep it concise and up-to-date.
    - **Tie-In**: Enhances GitHub repo usability.

15. **Integrate with GitHub Packages**: Prompt Copilot to publish artifacts.
    - **Steps**: Ask "Create a GitHub Actions job to publish a Docker image to GitHub Packages."
    - **Example**: Use `docker build` and `gh pr create`.
    - **Best Practices**: Secure access tokens.
    - **Tie-In**: Streamlines DevOps pipelines.

16. **Handle Multi-Environment Deployments**: Use Copilot for environment-specific configs.
    - **Steps**: Prompt "Generate Ansible inventory for dev, staging, and prod environments."
    - **Example**: Use variables for scaling.
    - **Best Practices**: Avoid hardcoding env differences.
    - **Tie-In**: Scales automation for DevOps.

17. **Automate Security Scans**: Prompt Copilot to integrate tools like Trivy or Snyk.
    - **Steps**: Ask "Add a security scan step to this GitHub Actions workflow."
    - **Example**: Fail builds on vulnerabilities.
    - **Best Practices**: Configure severity thresholds.
    - **Tie-In**: Ensures compliance in DevOps.

18. **Create Custom GitHub Actions**: For reusable automation, prompt Copilot to write composite actions.
    - **Steps**: Ask "Build a custom action for deploying to Kubernetes."
    - **Example**: Include inputs for cluster name.
    - **Best Practices**: Test in a separate repo.
    - **Tie-In**: Extends GitHub's automation capabilities.

19. **Optimize Ansible Playbooks**: Prompt Copilot to improve performance.
    - **Steps**: Provide playbook and ask "Optimize this Ansible role for parallel execution."
    - **Example**: Use `async` and `poll`.
    - **Best Practices**: Profile with Ansible timing.
    - **Tie-In**: Speeds up server setups.

20. **Generate Terraform Modules**: For reusable infra, prompt Copilot to modularize code.
    - **Steps**: Ask "Convert this Terraform config into a reusable module."
    - **Example**: Add variables and outputs.
    - **Best Practices**: Follow Terraform registry standards.
    - **Tie-In**: Promotes IaC best practices.

21. **Automate GitHub Issues from Logs**: Prompt Copilot to parse logs and create issues.
    - **Steps**: Ask "Script to create a GitHub issue from error logs using the API."
    - **Example**: Extract stack traces.
    - **Best Practices**: Use issue labels for triage.
    - **Tie-In**: Enhances DevOps monitoring.

22. **Handle Branch Protection Rules**: Prompt Copilot to suggest rules for repos.
    - **Steps**: Ask "Recommend branch protection rules for a DevOps repo."
    - **Example**: Require reviews and status checks.
    - **Best Practices**: Balance security with agility.
    - **Tie-In**: Secures GitHub workflows.

23. **Create Incident Response Playbooks**: For DevOps, prompt Copilot to draft runbooks.
    - **Steps**: Ask "Write an Ansible playbook for incident response: isolate a compromised server."
    - **Example**: Include notification steps.
    - **Best Practices**: Test in drills.
    - **Tie-In**: Prepares for outages.

24. **Automate Code Reviews**: Prompt Copilot to suggest review comments.
    - **Steps**: Paste code and ask "Review this Terraform for security issues."
    - **Example**: Flag exposed ports.
    - **Best Practices**: Use as a supplement to human reviews.
    - **Tie-In**: Improves GitHub PR quality.

25. **Generate Helm Charts**: For Kubernetes deployments, prompt Copilot to create charts.
    - **Steps**: Ask "Generate a Helm chart for deploying an app with Ingress."
    - **Example**: Include values.yaml.
    - **Best Practices**: Validate with `helm lint`.
    - **Tie-In**: Automates container orchestration.

26. **Handle API Rate Limits**: Prompt Copilot to add retry logic for GitHub API calls.
    - **Steps**: Ask "Add exponential backoff to this GitHub CLI script."
    - **Example**: Use `sleep` commands.
    - **Best Practices**: Monitor usage.
    - **Tie-In**: Ensures reliable automation.

27. **Create Notification Systems**: Prompt Copilot to integrate Slack or email alerts.
    - **Steps**: Ask "Add Slack notifications to this GitHub Actions workflow."
    - **Example**: On deploy success/failure.
    - **Best Practices**: Secure webhooks.
    - **Tie-In**: Keeps DevOps teams informed.

28. **Automate Database Migrations**: For DevOps, prompt Copilot to write Flyway or Liquibase scripts.
    - **Steps**: Ask "Generate a Flyway migration for adding a table."
    - **Example**: Include rollback scripts.
    - **Best Practices**: Test in staging.
    - **Tie-In**: Manages data in automation.

29. **Optimize GitHub Actions Runners**: Prompt Copilot to choose self-hosted vs. GitHub-hosted.
    - **Steps**: Ask "Recommend runner setup for high-throughput CI."
    - **Example**: Use larger instances.
    - **Best Practices**: Monitor costs.
    - **Tie-In**: Scales DevOps pipelines.

30. **Generate Compliance Reports**: Prompt Copilot to create scripts for auditing.
    - **Steps**: Ask "Script to generate a compliance report from GitHub repo data."
    - **Example**: Check for licenses.
    - **Best Practices**: Automate weekly runs.
    - **Tie-In**: Meets regulatory needs.

31. **Handle Multi-Cloud Deployments**: Prompt Copilot for hybrid configs.
    - **Steps**: Ask "Create a Terraform config for AWS and Azure resources."
    - **Example**: Use providers.
    - **Best Practices**: Manage state carefully.
    - **Tie-In**: Expands automation scope.

32. **Automate Backup Strategies**: Prompt Copilot to add backups to scripts.
    - **Steps**: Ask "Add backup logic to this Ansible playbook."
    - **Example**: Use rsync.
    - **Best Practices**: Encrypt backups.
    - **Tie-In**: Ensures data safety in DevOps.

33. **Create Custom Linters**: For code quality, prompt Copilot to write ESLint rules for IaC.
    - **Steps**: Ask "Generate a custom ESLint rule for Terraform syntax."
    - **Example**: Flag deprecated resources.
    - **Best Practices**: Integrate into CI.
    - **Tie-In**: Maintains standards.

34. **Handle Feature Flags**: Prompt Copilot to implement toggles in automation.
    - **Steps**: Ask "Add feature flags to this Ansible role."
    - **Example**: Use variables.
    - **Best Practices**: Test flag states.
    - **Tie-In**: Enables safe rollouts.

35. **Generate API Gateways**: For microservices, prompt Copilot to configure Kong or NGINX.
    - **Steps**: Ask "Create an NGINX config for API routing."
    - **Example**: Include rate limiting.
    - **Best Practices**: Secure endpoints.
    - **Tie-In**: Builds scalable architectures.

36. **Automate Log Aggregation**: Prompt Copilot to set up ELK stacks.
    - **Steps**: Ask "Generate a Docker Compose for ELK stack."
    - **Example**: Include Filebeat.
    - **Best Practices**: Configure retention.
    - **Tie-In**: Enhances DevOps observability.

37. **Create Disaster Recovery Plans**: Prompt Copilot to draft DR scripts.
    - **Steps**: Ask "Write a Terraform plan for multi-region failover."
    - **Example**: Use Route 53.
    - **Best Practices**: Test regularly.
    - **Tie-In**: Prepares for failures.

38. **Optimize Container Images**: Prompt Copilot to slim Dockerfiles.
    - **Steps**: Ask "Optimize this Dockerfile for a smaller image size."
    - **Example**: Use multi-stage builds.
    - **Best Practices**: Scan for vulnerabilities.
    - **Tie-In**: Improves deployment efficiency.

39. **Handle GitOps Workflows**: Prompt Copilot to integrate with Flux or ArgoCD.
    - **Steps**: Ask "Create a GitOps config for deploying via ArgoCD."
    - **Example**: Include sync policies.
    - **Best Practices**: Use immutable repos.
    - **Tie-In**: Automates Kubernetes management.

40. **Generate Cost Reports**: For cloud, prompt Copilot to analyze usage.
    - **Steps**: Ask "Script to generate AWS cost reports from Terraform state."
    - **Example**: Use AWS CLI.
    - **Best Practices**: Automate monthly.
    - **Tie-In**: Manages budgets in DevOps.

41. **Automate User Onboarding**: Prompt Copilot to create scripts for team setup.
    - **Steps**: Ask "Generate a script to onboard devs to a GitHub org."
    - **Example**: Add to teams and repos.
    - **Best Practices**: Use SSO.
    - **Tie-In**: Scales DevOps teams.

42. **Create Chaos Engineering Tests**: Prompt Copilot to simulate failures.
    - **Steps**: Ask "Write a Chaos Monkey script for Kubernetes."
    - **Example**: Kill pods randomly.
    - **Best Practices**: Run in staging.
    - **Tie-In**: Builds resilience.

43. **Handle API Versioning**: Prompt Copilot to manage versions in IaC.
    - **Steps**: Ask "Add versioning to this Terraform provider config."
    - **Example**: Pin versions.
    - **Best Practices**: Update gradually.
    - **Tie-In**: Ensures compatibility.

44. **Generate Performance Benchmarks**: Prompt Copilot to create load tests.
    - **Steps**: Ask "Script a JMeter test for this API."
    - **Example**: Include assertions.
    - **Best Practices**: Integrate with CI.
    - **Tie-In**: Validates automation.

45. **Automate Certificate Management**: Prompt Copilot for Let's Encrypt setups.
    - **Steps**: Ask "Create an Ansible role for SSL cert renewal."
    - **Example**: Use certbot.
    - **Best Practices**: Monitor expirations.
    - **Tie-In**: Secures deployments.

46. **Create Service Meshes**: Prompt Copilot to configure Istio.
    - **Steps**: Ask "Generate Istio configs for traffic splitting."
    - **Example**: Include VirtualServices.
    - **Best Practices**: Test canary deployments.
    - **Tie-In**: Manages microservices.

47. **Handle Data Pipelines**: Prompt Copilot for ETL scripts.
    - **Steps**: Ask "Write a Python script for data ingestion using Airflow."
    - **Example**: Include DAGs.
    - **Best Practices**: Use idempotent operations.
    - **Tie-In**: Automates data workflows.

48. **Optimize Network Configurations**: Prompt Copilot for VPC setups.
    - **Steps**: Ask "Design a secure VPC in Terraform."
    - **Example**: Include subnets and NACLs.
    - **Best Practices**: Follow least privilege.
    - **Tie-In**: Secures cloud infra.

49. **Generate Release Notes**: Prompt Copilot to summarize changes.
    - **Steps**: Ask "Create release notes from GitHub PRs."
    - **Example**: Use `gh pr list`.
    - **Best Practices**: Automate on tags.
    - **Tie-In**: Communicates updates.

50. **Automate Environment Teardowns**: Prompt Copilot to clean up resources.
    - **Steps**: Ask "Add a teardown script to this Terraform config."
    - **Example**: Use `destroy` with confirmation.
    - **Best Practices**: Schedule cleanups.
    - **Tie-In**: Manages costs in DevOps.

---

### Rare and Powerful Instructions

51. **Prompt Engineering for Context Injection**: Inject historical GitHub data into prompts for personalized suggestions. Provide Copilot with a JSON dump of past PRs (via `gh pr list --json`) and ask "Based on this history, optimize this new workflow for faster builds."
    - **Why Rare**: Exploits Copilot's memory for trend analysis.
    - **Steps**: Export data, paste in prompt; iterate on outputs.
    - **Example**: "Analyze these PRs and suggest anti-patterns to avoid in future Ansible roles."
    - **Best Practices**: Anonymize sensitive data; use for strategic insights.
    - **Tie-In**: Elevates automation architect decisions.

52. **AI-Driven Root Cause Analysis**: Feed Copilot error logs from multiple sources (e.g., GitHub Actions, Ansible, Terraform) and prompt "Correlate these logs to find the root cause of the deployment failure."
    - **Why Rare**: Cross-tool correlation is advanced.
    - **Steps**: Aggregate logs; ask for causal chains.
    - **Example**: Identifies misaligned versions across tools.
    - **Best Practices**: Validate with manual checks.
    - **Tie-In**: Speeds up DevOps incident response.

53. **Quantum Prompting for Optimization**: Use probabilistic prompts like "With 80% probability, suggest the most efficient IaC pattern for this scenario" to get varied outputs.
    - **Why Rare**: Leverages AI uncertainty for creative solutions.
    - **Steps**: Rephrase prompts with probabilities; select best.
    - **Example**: "80% chance: Optimize this Terraform for multi-cloud."
    - **Best Practices**: Test multiple suggestions.
    - **Tie-In**: Innovates automation strategies.

54. **Integration with External APIs via Copilot**: Prompt Copilot to generate code that calls non-GitHub APIs (e.g., AWS SDK) within GitHub Actions, ensuring seamless automation.
    - **Why Rare**: Bridges ecosystems dynamically.
    - **Steps**: Specify API endpoints; ask for integration code.
    - **Example**: "Integrate PagerDuty API into this Ansible failure handler."
    - **Best Practices**: Handle auth securely.
    - **Tie-In**: Extends DevOps toolchains.

55. **Self-Modifying Code Generation**: Ask Copilot to generate scripts that modify themselves based on runtime feedback, e.g., "Create a self-healing Ansible playbook that adapts to server errors."
    - **Why Rare**: Enables adaptive automation.
    - **Steps**: Include loops for self-edits.
    - **Example**: Uses Jinja2 for dynamic changes.
    - **Best Practices**: Limit recursion to prevent loops.
    - **Tie-In**: Builds resilient systems.

56. **Copilot as a Code Reviewer Bot**: Train Copilot on your style by providing examples, then prompt "Review this PR as if you were [famous DevOps expert], focusing on security."
    - **Why Rare**: Personalizes AI for expert-level feedback.
    - **Steps**: Feed style guides; role-play prompts.
    - **Example**: "As Kelsey Hightower, critique this Kubernetes YAML."
    - **Best Practices**: Combine with human reviews.
    - **Tie-In**: Enhances GitHub PR quality.

57. **Predictive Failure Modeling**: Use Copilot to simulate failures by prompting "Predict and mitigate potential failures in this CI/CD pipeline based on historical data."
    - **Why Rare**: Proactive risk assessment.
    - **Steps**: Provide metrics; ask for scenarios.
    - **Example**: Suggests chaos tests.
    - **Best Practices**: Back with data.
    - **Tie-In**: Strengthens DevOps reliability.

58. **Multi-Language Code Translation**: Prompt Copilot to translate between languages, e.g., "Convert this Bash script to PowerShell for Windows automation."
    - **Why Rare**: Handles polyglot environments.
    - **Steps**: Specify source/target; ensure fidelity.
    - **Example**: Translates Ansible to Terraform.
    - **Best Practices**: Test translations.
    - **Tie-In**: Supports diverse DevOps stacks.

59. **AI-Generated Documentation with Diagrams**: Ask Copilot to create Mermaid diagrams within code comments, e.g., "Generate a flowchart for this GitHub Actions workflow."
    - **Why Rare**: Visualizes complex automation.
    - **Steps**: Prompt for diagram syntax.
    - **Example**: Embeds in READMEs.
    - **Best Practices**: Render in GitHub.
    - **Tie-In**: Improves GitHub repo clarity.

60. **Ethical Hacking Simulations**: Prompt Copilot to generate penetration testing scripts for your infra, e.g., "Create a script to test for SQL injection in this Ansible-deployed app."
    - **Why Rare**: Offensive security in automation.
    - **Steps**: Focus on safe simulations.
    - **Example**: Uses tools like sqlmap.
    - **Best Practices**: Never run on prod; ethical only.
    - **Tie-In**: Bolsters DevOps security.

These instructions form a robust toolkit for leveraging GitHub Copilot in high-stakes automation and DevOps roles. Start with the professional set for daily use, then incorporate rare ones for advanced scenarios. Always iterate on Copilot's outputs, as AI can hallucinate—validate everything. If you need examples tailored to your Ansible workspace, let me know!