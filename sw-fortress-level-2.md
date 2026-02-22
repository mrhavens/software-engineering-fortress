# Software Engineering Fortress
## Level 2: Agent Skill Taxonomies and Role Implementations

---

# Agent Skill Taxonomies and Role Implementations for Multi-Agent Software Engineering

## Abstract

This paper establishes the detailed skill taxonomies, role implementations, and operational protocols for each agent type within the Software Engineering Fortress framework. Building upon the five-layer architecture established in Level 1, we define the specific capabilities, prompt templates, tool access patterns, error handling strategies, and inter-agent communication mechanisms that enable effective multi-agent software development. Each agent type—Architect, Coder, Tester, DevOps, and Security—possesses a distinct skill taxonomy optimized for its responsibilities, with clear interfaces for collaboration and robust error recovery mechanisms.

## 1. Introduction

The transition from foundational architecture to concrete role implementation demands precise definition of what each agent type can do, how it interacts with other agents, and how it handles the inevitable failures that occur in autonomous systems. Level 1 established the five-layer framework; Level 2 populates that framework with specific, actionable agent capabilities.

The five agent types we implement are:

1. **Architect Agent** - System design, technology selection, pattern application
2. **Coder Agent** - Code generation, refactoring, implementation
3. **Tester Agent** - Test creation, execution, quality validation
4. **DevOps Agent** - Deployment, infrastructure, CI/CD pipelines
5. **Security Agent** - Vulnerability assessment, secure coding, compliance

Each agent operates with defined boundaries, specific tool access, and robust error handling. The following sections detail each role's taxonomy, prompts, tools, error protocols, and communication patterns.

## 2. Skill Taxonomies by Agent Type

### 2.1 Architect Agent

The Architect Agent possesses deep expertise in system design, technology selection, and pattern application. Its skill taxonomy spans:

**Core Skills:**
- **System Design**: Ability to create scalable, maintainable system architectures using established patterns (microservices, event-driven, layered, hexagonal)
- **Technology Selection**: Deep knowledge of programming languages, frameworks, databases, and cloud services—with awareness of trade-offs
- **Pattern Application**: Recognition and application of design patterns (GoF, enterprise integration, cloud-native)
- **Data Modeling**: Entity-relationship design, schema definition, data flow optimization
- **API Design**: RESTful and GraphQL interface specification, contract design

**Advanced Skills:**
- **Performance Architecture**: Capacity planning, caching strategies, load balancing
- **Security Architecture**: Threat modeling, defense-in-depth design, authentication/authorization patterns
- **Observability Design**: Logging, metrics, tracing, alerting strategies
- **Cost Optimization**: Cloud cost modeling, resource right-sizing

**Skill Proficiency Levels:**

| Skill | Level 1 (Foundation) | Level 2 (Advanced) | Level 3 (Expert) |
|-------|----------------------|--------------------|------------------|
| System Design | Single-module design | Multi-service architecture | Enterprise-scale systems |
| Technology Selection | Knows popular options | Understands trade-offs | Pioneers new technology adoption |
| Pattern Application | Recognizes patterns | Applies appropriately | Innovates new patterns |
| Data Modeling | Basic ER design | Complex domain models | Polyglot persistence design |

### 2.2 Coder Agent

The Coder Agent specializes in translating specifications into working code. Its skill taxonomy focuses on implementation:

**Core Skills:**
- **Code Generation**: Writing syntactically correct, idiomatic code in multiple languages
- **Test-Driven Development**: Writing tests before or alongside implementation
- **Refactoring**: Improving code structure without changing behavior
- **Debugging**: Identifying and fixing bugs through systematic analysis
- **Code Review**: Evaluating code quality, identifying issues

**Advanced Skills:**
- **Framework Mastery**: Deep knowledge of specific frameworks (React, Django, Spring, etc.)
- **Library Integration**: Incorporating third-party libraries effectively
- **Performance Optimization**: Algorithmic improvements, query optimization
- **Cross-Language Translation**: Converting between programming paradigms

**Skill Proficiency Levels:**

| Skill | Level 1 (Foundation) | Level 2 (Advanced) | Level 3 (Expert) |
|-------|----------------------|--------------------|------------------|
| Code Generation | Simple functions | Complete modules | Full system implementation |
| TDD | Write basic tests | Test-first development | Behavior-driven specs |
| Refactoring | Rename/extract | Architectural refactoring | Domain-driven remodels |
| Debugging | Print debugging | IDE debugging | Production incident triage |

### 2.3 Tester Agent

The Tester Agent ensures software quality through systematic verification:

**Core Skills:**
- **Test Design**: Creating test strategies, selecting appropriate test types
- **Test Automation**: Writing and maintaining automated test suites
- **Boundary Analysis**: Identifying edge cases and failure points
- **Test Data Management**: Creating and managing test fixtures
- **Test Execution**: Running suites, analyzing results, triaging failures

**Advanced Skills:**
- **Property-Based Testing**: Designing invariants and generative tests
- **Performance Testing**: Load, stress, and endurance testing
- **Mutation Testing**: Evaluating test suite effectiveness
- **Visual Regression**: Screenshot and UI change detection

**Skill Proficiency Levels:**

| Skill | Level 1 (Foundation) | Level 2 (Advanced) | Level 3 (Expert) |
|-------|----------------------|--------------------|------------------|
| Test Design | Happy path tests | Edge case coverage | Risk-based strategies |
| Test Automation | Basic selenium/unit | CI pipeline integration | Self-healing test suites |
| Boundary Analysis | Common edges | Domain-specific edges | Novel failure modes |
| Performance Testing | Basic load tests | Complex scenarios | Production simulation |

### 2.4 DevOps Agent

The DevOps Agent handles deployment, infrastructure, and operational concerns:

**Core Skills:**
- **Infrastructure as Code**: Terraform, CloudFormation, Pulumi definitions
- **Container Orchestration**: Docker, Kubernetes, Helm charts
- **CI/CD Pipeline**: GitHub Actions, GitLab CI, Jenkins pipelines
- **Configuration Management**: Environment configs, secrets management
- **Deployment Strategies**: Blue-green, canary, rolling deployments

**Advanced Skills:**
- **Multi-Cloud Infrastructure**: Cross-cloud architecture and deployment
- **Site Reliability Engineering**: SLIs, SLOs, error budgets
- **Infrastructure Security**: Hardening, network policies, secrets rotation
- **Cost Optimization**: Resource scheduling, spot instances, reserved capacity

**Skill Proficiency Levels:**

| Skill | Level 1 (Foundation) | Level 2 (Advanced) | Level 3 (Expert) |
|-------|----------------------|--------------------|------------------|
| IaC | Basic templates | Modular infrastructure | Policy-as-code |
| K8s | Basic deployments | Complex orchestration | Multi-cluster management |
| CI/CD | Simple pipelines | Complex workflows | Self-optimizing pipelines |
| Deployment | Basic rollout | Blue-green/canary | Progressive delivery |

### 2.5 Security Agent

The Security Agent protects the system through vulnerability assessment and secure practices:

**Core Skills:**
- **Vulnerability Detection**: SAST, DAST, dependency scanning
- **Secure Coding**: Knowledge of OWASP Top 10, CWE
- **Threat Modeling**: STRIDE, PASTA, attack tree creation
- **Compliance**: Understanding of SOC2, GDPR, HIPAA requirements
- **Incident Response**: Identifying and containing security events

**Advanced Skills:**
- **Penetration Testing**: Manual exploitation techniques
- **Cryptography**: Encryption, hashing, key management
- **Zero Trust Architecture**: Identity-based access, microsegmentation
- **Security Automation**: Automated scanning, alerting, response

**Skill Proficiency Levels:**

| Skill | Level 1 (Foundation) | Level 2 (Advanced) | Level 3 (Expert) |
|-------|----------------------|--------------------|------------------|
| Vulnerability Detection | Tool-based scanning | Manual analysis | Advanced exploitation |
| Secure Coding | Known patterns | Context-aware security | Novel threat mitigation |
| Threat Modeling | Basic STRIDE | Full PASTA | Custom methodologies |
| Compliance | Awareness | Implementation | Audit preparation |

## 3. Prompt Templates by Role

Each agent type operates using standardized prompt templates that define its inputs, context, and expected outputs.

### 3.1 Architect Agent Prompt Templates

**Template: System Design Request**
```
You are the System Architect Agent for project {project_id}.

## Context
- Project: {project_name}
- Requirements: {requirements_summary}
- Constraints: {constraints_list}
- Existing Architecture: {architecture_overview}

## Task
Design the system architecture for: {feature_description}

## Deliverables
1. Component diagram showing key modules and their interactions
2. API contracts for external interfaces
3. Data model for persistent storage
4. Technology recommendations with trade-offs
5. Non-functional requirements considerations (performance, security, scalability)

## Constraints
- Budget: {budget_constraint}
- Timeline: {timeline_constraint}
- Team expertise: {expertise_level}

Provide a detailed architecture document with rationale for all decisions.
```

**Template: Architecture Review Request**
```
You are the System Architect Agent conducting a peer review.

## Context
- Project: {project_id}
- Proposed Design: {design_document}
- Review Focus: {review_criteria}

## Task
Review the proposed architecture and identify:
1. Strengths and weaknesses
2. Potential scalability issues
3. Security considerations
4. Technical debt risks
5. Alternative approaches

Provide specific, actionable recommendations with severity ratings.
```

### 3.2 Coder Agent Prompt Templates

**Template: Implementation Request**
```
You are the Coder Agent for project {project_id}.

## Context
- Module: {module_name}
- Specification: {specification_document}
- Existing Code: {codebase_context}
- Test Coverage: {coverage_status}

## Task
Implement the following feature: {feature_description}

## Requirements
- Language: {programming_language}
- Framework: {framework_version}
- Style Guide: {style_guide_reference}
- Test Requirements: {test_requirements}

## Constraints
- Must pass existing tests: {test_list}
- Performance requirements: {performance_constraints}
- Security requirements: {security_constraints}

Generate clean, well-documented code with inline comments explaining complex logic.
```

**Template: Refactoring Request**
```
You are the Coder Agent performing code refactoring.

## Context
- File: {file_path}
- Current Issues: {issues_list}
- Target Pattern: {target_pattern}

## Task
Refactor the following code to improve: {improvement_goals}

## Requirements
- Maintain all existing functionality
- Preserve the public API
- Add no new dependencies without approval
- Ensure test coverage remains 100%

Provide the refactored code with a summary of changes and rationale.
```

### 3.3 Tester Agent Prompt Templates

**Template: Test Generation Request**
```
You are the Tester Agent for project {project_id}.

## Context
- Module Under Test: {module_name}
- Implementation: {implementation_code}
- Test Framework: {test_framework}
- Coverage Target: {coverage_percentage}%

## Task
Generate comprehensive tests for: {feature_description}

## Test Types Required
- Unit tests for all public methods
- Edge case coverage for boundary conditions
- Integration tests for module interactions
- Error handling tests for failure scenarios

## Quality Requirements
- Tests must be independent and idempotent
- Use descriptive test names following {naming_convention}
- Include setup/teardown for test isolation
- Add docstrings explaining test purpose

Generate test code that achieves {coverage_target}% line coverage.
```

**Template: Test Execution and Analysis**
```
You are the Tester Agent executing and analyzing tests.

## Context
- Test Suite: {test_suite_name}
- Execution Environment: {environment_details}
- Previous Results: {historical_results}

## Task
Execute the test suite and analyze results:
1. Run all tests and capture output
2. Identify passing and failing tests
3. For failures, diagnose root cause
4. Provide reproduction steps for each failure
5. Recommend fixes for failing tests

## Output Format
- Summary: Total/Pass/Fail/Skip counts
- Failures: Test name, error message, stack trace, root cause, fix recommendation
- Flaky tests: Tests that sometimes fail
- Coverage: Current coverage metrics

Be thorough—missed bugs are worse than false positives.
```

### 3.4 DevOps Agent Prompt Templates

**Template: Deployment Request**
```
You are the DevOps Agent for project {project_id}.

## Context
- Application: {application_name}
- Version: {version_number}
- Target Environment: {environment_name}
- Previous Version: {previous_version}

## Task
Deploy the application to {environment_name}.

## Infrastructure
- Cloud Provider: {cloud_provider}
- Cluster: {cluster_name}
- Region: {region}

## Deployment Strategy
- Type: {deployment_strategy} (rolling/blue-green/canary)
- Traffic Split: {traffic_percentage}%
- Health Check: {health_check_endpoint}
- Rollback Threshold: {failure_threshold}%

## Requirements
- Ensure zero-downtime deployment
- Run smoke tests post-deployment
- Update monitoring dashboards
- Notify team of deployment status

Provide deployment confirmation with version info and health status.
```

**Template: Infrastructure Provisioning**
```
You are the DevOps Agent provisioning infrastructure.

## Context
- Project: {project_name}
- Environment: {environment_type}
- Requirements: {infrastructure_requirements}

## Task
Create infrastructure as code for: {infrastructure_description}

## Components Required
- Compute: {compute_specifications}
- Database: {database_requirements}
- Network: {network_configuration}
- Security: {security_requirements}

## Standards
- Use {iac_tool} for infrastructure definition
- Follow naming convention: {naming_convention}
- Enable logging: {logging_requirements}
- Enable monitoring: {monitoring_requirements}

Output Terraform/CloudFormation/Pulumi code with appropriate modules.
```

### 3.5 Security Agent Prompt Templates

**Template: Security Review Request**
```
You are the Security Agent for project {project_id}.

## Context
- Code Under Review: {code_location}
- Language: {programming_language}
- Previous Issues: {historical_issues}

## Task
Perform a security review of: {review_scope}

## OWASP Focus Areas
- Injection flaws
- Authentication failures
- Sensitive data exposure
- XML external entities
- Broken access control
- Security misconfiguration
- Cross-site scripting (XSS)
- Insecure deserialization
- Using vulnerable components
- Insufficient logging

## Deliverables
1. List of vulnerabilities found (with severity: Critical/High/Medium/Low)
2. Proof of concept for each critical finding
3. Recommended remediation for each issue
4. False positives (if any identified)

Use static analysis tools and manual review techniques.
```

**Template: Vulnerability Assessment**
```
You are the Security Agent conducting vulnerability assessment.

## Context
- Application: {application_name}
- Environment: {environment}
- Assessment Type: {assessment_type}

## Task
Scan for vulnerabilities in: {scan_target}

## Tools to Use
- SAST: {sast_tool}
- DAST: {dast_tool}
- Dependency: {dependency_scanner}
- Secret Detection: {secret_scanner}

## Severity Thresholds
- Critical: Immediate remediation required
- High: Fix within sprint
- Medium: Fix within month
- Low: Address when time permits

Generate a vulnerability report with CVE references and CVSS scores where applicable.
```

## 4. Tool Access Specifications

Each agent type has specific tool access optimized for its role:

### 4.1 Tool Access Matrix

| Tool Category | Architect | Coder | Tester | DevOps | Security |
|---------------|:---------:|:-----:|:------:|:------:|:--------:|
| **Code Operations** | | | | | |
| Read/Write Files | ✓ | ✓ | ✓ | ✓ | ✓ |
| Code Execution | | ✓ | ✓ | | |
| Git Operations | ✓ | ✓ | ✓ | ✓ | ✓ |
| **Testing** | | | | | |
| Unit Test Runner | | ✓ | ✓ | | |
| Integration Test Runner | | | ✓ | | |
| Coverage Analysis | | | ✓ | | |
| Mutation Testing | | | ✓ | | |
| **Infrastructure** | | | | | |
| Cloud APIs | | | | ✓ | |
| Container Registry | | | | ✓ | |
| Kubernetes | | | | ✓ | |
| IaC Tools | | | | ✓ | |
| **Security** | | | | | |
| SAST Scanners | | | | | ✓ |
| DAST Scanners | | | | | ✓ |
| Dependency Scanners | | | | | ✓ |
| Secret Detection | | | | | ✓ |
| **Communication** | | | | | |
| Message Other Agents | ✓ | ✓ | ✓ | ✓ | ✓ |
| Broadcast to Channel | ✓ | ✓ | ✓ | ✓ | ✓ |
| Request Human Input | ✓ | ✓ | ✓ | ✓ | ✓ |

### 4.2 Detailed Tool Specifications

**Coder Agent Tools:**
```python
# File Operations
tools.register('read_file', path: str) -> str
tools.register('write_file', path: str, content: str) -> bool
tools.register('edit_file', path: str, old: str, new: str) -> bool

# Code Execution
tools.register('run_command', cmd: str, cwd: str, timeout: int) -> CommandResult
tools.register('run_tests', test_path: str, coverage: bool) -> TestResult

# Git Operations
tools.register('git_branch', name: str) -> bool
tools.register('git_commit', message: str, files: List[str]) -> str
tools.register('git_push', remote: str, branch: str) -> bool
```

**Tester Agent Tools:**
```python
# Test Execution
tools.register('run_test_suite', path: str, parallel: bool) -> TestResult
tools.register('run_coverage', path: str) -> CoverageReport
tools.register('run_mutation_test', path: str) -> MutationResult

# Test Data
tools.register('generate_fixture', schema: dict) -> FixtureData
tools.register('load_test_data', source: str, query: str) -> TestData
```

**DevOps Agent Tools:**
```python
# Infrastructure
tools.register('terraform_apply', plan_file: str) -> ApplyResult
tools.register('kubectl_apply', manifest: str) -> K8sResult
tools.register('docker_build', tag: str, path: str) -> ImageDigest

# Deployment
tools.register('deploy_k8s', manifest: K8sManifest) -> DeploymentStatus
tools.register('scale_service', name: str, replicas: int) -> bool
tools.register('rollback_deployment', name: str) -> bool
```

**Security Agent Tools:**
```python
# Scanning
tools.register('run_sast', language: str, path: str) -> FindingList
tools.register('run_dast', target: str, config: ScanConfig) -> FindingList
tools.register('scan_dependencies', lock_file: str) -> VulnList

# Analysis
tools.register('analyze_owasp', code: str) -> OWASPReport
tools.register('check_secrets', path: str) -> SecretList
```

## 5. Error Handling Protocols

Each agent implements role-specific error handling with clear escalation paths.

### 5.1 Architect Agent Error Handling

**Error Categories:**
- **Specification Ambiguity**: Requirements unclear or contradictory
- **Design Conflicts**: Multiple valid approaches with trade-offs
- **Technical Constraints**: Limitations prevent ideal solution
- **Resource Limits**: Budget/timeline incompatible with scope

**Error Handling Protocol:**
```
1. DETECT: Identify the error condition and categorize
2. ASSESS: Determine if resolution is within scope
3. ATTEMPT: Try resolution using alternative approaches
4. ESCALATE: If unresolved after 2 attempts, escalate to governance

Architect-specific recovery:
- Ambiguity → Request clarification from Stakeholder Proxy
- Conflict → Present trade-off analysis to governance
- Constraint → Propose scope adjustment with rationale
- Resource → Recommend phased implementation
```

**Retry Logic:**
```python
async def handle_design_error(error: DesignError) -> Resolution:
    attempts = 0
    max_attempts = 2
    
    while attempts < max_attempts:
        try:
            solution = await attempt_resolution(error, attempts)
            if await validate_solution(solution):
                return solution
        except ResolutionFailed:
            attempts += 1
            continue
    
    return await escalate_to_governance(error)
```

### 5.2 Coder Agent Error Handling

**Error Categories:**
- **Syntax Errors**: Code doesn't parse
- **Type Errors**: Type checking failures
- **Test Failures**: Implementation doesn't meet tests
- **Lint Errors**: Style/quality violations
- **Dependency Issues**: Missing or incompatible libraries

**Error Handling Protocol:**
```
1. DETECT: Compiler/interpreter/test runner reports error
2. ANALYZE: Read error message, identify root cause
3. FIX: Apply correction based on error type
4. VERIFY: Run tests to confirm fix
5. COMMIT: Save working solution

Coder-specific recovery:
- Syntax → Auto-fix if possible, otherwise manual correction
- Type → Review type signatures, add annotations
- Test Failure → Understand expected behavior, fix implementation
- Lint → Auto-format and review warnings
- Dependency → Find compatible version or alternative
```

**Retry Logic:**
```python
async def implement_with_retry(spec: FeatureSpec) -> Implementation:
    max_attempts = 3
    
    for attempt in range(max_attempts):
        try:
            code = await generate_implementation(spec)
            await run_tests(code)
            await run_linter(code)
            return code
        except TestFailure as e:
            await analyze_failure(e)
            await fix_implementation(e)
        except LintError as e:
            await auto_format(e)
    
    if attempt_exhausted:
        await request_peer_review()
```

### 5.3 Tester Agent Error Handling

**Error Categories:**
- **Test Infrastructure**: Environment issues preventing test execution
- **Flaky Tests**: Non-deterministic test behavior
- **False Positives**: Tests failing incorrectly
- **Coverage Gaps**: Insufficient test coverage

**Error Handling Protocol:**
```
1. ISOLATE: Determine if failure is test or code issue
2. INVESTIGATE: Run tests multiple times to confirm flakiness
3. FIX: Address the appropriate source of failure
4. DOCUMENT: Record findings for future reference

Tester-specific recovery:
- Infrastructure → Request DevOps support, log issue
- Flaky Test → Add retry logic, investigate race conditions
- False Positive → Adjust test or report as won't fix
- Coverage Gap → Generate additional test cases
```

### 5.4 DevOps Agent Error Handling

**Error Categories:**
- **Deployment Failure**: Application fails to start or becomes unhealthy
- **Infrastructure Failure**: Resource provisioning or configuration errors
- **Rollback Required**: Post-deployment issues requiring revert
- **Permission Denied**: IAM/authorization failures

**Error Handling Protocol:**
```
1. MONITOR: Detect failure through health checks or alerts
2. DIAGNOSE: Analyze logs, metrics, events for root cause
3. ATTEMPT FIX: Apply appropriate remediation
4. VERIFY: Confirm health after remediation
5. ROLLBACK: If unrecoverable, revert to previous version

DevOps-specific recovery:
- Deployment Failure → Check logs, fix application issue
- Infrastructure → Apply corrective IaC, recreate resources
- Rollback → Execute rollback procedure, notify team
- Permission → Request elevated access, fix IAM policies
```

**Critical Error Response:**
```python
async def handle_deployment_failure(event: DeploymentEvent) -> Response:
    if event.is_critical():
        await execute_rollback(event)
        await notify_oncall(event)
        await_create_incident(event)
    
    logs = await fetch_logs(event.pods)
    metrics = await fetch_metrics(event.service)
    
    diagnosis = await diagnose(logs, metrics)
    
    if diagnosis.can_fix():
        await apply_fix(diagnosis)
    else:
        await escalate_to_engineering(diagnosis)
```

### 5.5 Security Agent Error Handling

**Error Categories:**
- **Vulnerability Found**: Security flaw detected in code/dependencies
- **Scan Failure**: Security tool error or timeout
- **False Positive**: Tool incorrectly flags safe code
- **Compliance Violation**: Missing required security controls

**Error Handling Protocol:**
```
1. VALIDATE: Confirm vulnerability is real, not false positive
2. ASSESS: Determine severity and exploitability
3. REMEDIATE: Apply fix or implement mitigation
4. VERIFY: Confirm vulnerability is resolved
5. DOCUMENT: Record for compliance and learning

Security-specific recovery:
- Vulnerability → Prioritize by severity, assign to Coder
- Scan Failure → Retry with increased timeout, check credentials
- False Positive → Add to allowlist with justification
- Compliance → Implement missing control or document exception
```

## 6. Inter-Agent Communication Patterns

Agents communicate through standardized patterns optimized for different scenarios.

### 6.1 Message Format

All inter-agent communication uses this standardized format:

```json
{
  "message_id": "uuid-v4",
  "timestamp": "ISO-8601",
  "from": {
    "agent_id": "architect-001",
    "agent_type": "Architect",
    "role": "System Design"
  },
  "to": {
    "agent_id": "coder-001",
    "agent_type": "Coder",
    "role": "Implementation"
  },
  "type": "REQUEST|RESPONSE|NOTIFICATION|ACK",
  "action": "IMPLEMENT|FIX|REVIEW|DEPLOY|SCAN",
  "priority": "HIGH|NORMAL|LOW",
  "payload": {
    "task": "Implement user authentication module",
    "context": {...},
    "constraints": {...},
    "deliverables": [...]
  },
  "reply_to": null,
  "correlation_id": null
}
```

### 6.2 Communication Patterns

**Request-Response (Synchronous)**
```
Agent A → REQUEST → Agent B → RESPONSE → Agent A

Use when: Agent needs immediate result before continuing
Example: Architect requests design review from peer Architect
Timeout: 60 seconds
```

**Fire-and-Forget (Asynchronous)**
```
Agent A → NOTIFICATION → Agent B

Use when: Informing without requiring response
Example: DevOps notifies team of deployment completion
Acknowledgment: Optional ACK within 30 seconds
```

**Broadcast**
```
Agent A → BROADCAST → [Agent B, Agent C, Agent D]

Use when: Announcements affecting multiple agents
Example: Security broadcasts critical vulnerability alert
Delivery: All recipients must ACK within 60 seconds
```

**Chain (Sequential Handoff)**
```
Agent A → REQUEST → Agent B → REQUEST → Agent C → RESPONSE → Agent B → RESPONSE → Agent A

Use when: Tasks requiring sequential specialization
Example: Architect → Coder → Tester → Coder (fix) → Tester (verify) → Complete
```

**Parallel (Concurrent Execution)**
```
Agent A → REQUEST → [Agent B, Agent C, Agent D]
                ↓         ↓         ↓
Agent A ← RESPONSE ← [Agent B, Agent C, Agent D]

Use when: Multiple independent tasks
Example: Security scans multiple services in parallel
Aggregation: Wait for all responses or use majority/consensus
```

### 6.3 Conversation Flows

**Implementation Flow:**
```
Architect: Creates specification
    ↓
    Creates implementation REQUEST to Coder
    ↓
Coder: Implements feature
    ↓
    Creates test REQUEST to Tester
    ↓
Tester: Verifies implementation
    ↓
    Returns results to Coder
    ↓
Coder: If failures, fixes and resubmits
    ↓
    If success, creates commit NOTIFICATION
```

**Security Review Flow:**
```
Coder: Submits code for review
    ↓
    Creates review REQUEST to Security
    ↓
Security: Scans code, performs manual review
    ↓
    If issues found, creates fix REQUEST to Coder
    ↓
    Coder fixes issues
    ↓
    Security re-reviews
    ↓
    If clean, creates approval NOTIFICATION
```

**Deployment Flow:**
```
Coder: Code merged to main
    ↓
    Creates deploy REQUEST to DevOps
    ↓
DevOps: Provisions infrastructure (if needed)
    ↓
    Builds and deploys
    ↓
    Creates verify REQUEST to Tester
    ↓
Tester: Runs smoke tests
    ↓
    Returns results to DevOps
    ↓
    DevOps: If failure, rolls back
    ↓
    If success, creates completion NOTIFICATION
```

### 6.4 Conflict Resolution

When agents disagree or produce conflicting outputs:

**Level 1: Self-Resolution**
```
1. Both agents document their reasoning
2. Each attempts to understand the other's perspective
3. Attempt to reach consensus
```

**Level 2: Peer Mediation**
```
1. Request third agent of same type to review
2. Present both positions with evidence
3. Accept majority decision
```

**Level 3: Governance Escalation**
```
1. Present conflict to Governance layer
2. Include all context and evidence
3. Accept governance decision
```

**Level 4: Human Review**
```
1. Governance determines human input needed
2. Create summary for human reviewer
3. Present options and recommendations
4. Accept human decision
```

## 7. Code Examples

### 7.1 Agent Communication Implementation

```python
from dataclasses import dataclass
from typing import Optional, Any
from enum import Enum
import asyncio

class MessageType(Enum):
    REQUEST = "REQUEST"
    RESPONSE = "RESPONSE"
    NOTIFICATION = "NOTIFICATION"
    ACK = "ACK"

class AgentMessage:
    def __init__(
        self,
        from_agent: str,
        to_agent: str,
        message_type: MessageType,
        action: str,
        payload: dict,
        priority: str = "NORMAL"
    ):
        self.from_agent = from_agent
        self.to_agent = to_agent
        self.message_type = message_type
        self.action = action
        self.payload = payload
        self.priority = priority
        self.correlation_id = None

class AgentCommunication:
    def __init__(self, agent_id: str):
        self.agent_id = agent_id
        self.message_queue = asyncio.Queue()
        self.pending_requests = {}
    
    async def send_request(
        self,
        to_agent: str,
        action: str,
        payload: dict,
        timeout: int = 60
    ) -> AgentMessage:
        msg = AgentMessage(
            from_agent=self.agent_id,
            to_agent=to_agent,
            message_type=MessageType.REQUEST,
            action=action,
            payload=payload
        )
        
        future = asyncio.Future()
        self.pending_requests[msg.correlation_id] = future
        
        await self.message_queue.put(msg)
        
        try:
            return await asyncio.wait_for(future, timeout=timeout)
        except asyncio.TimeoutError:
            self.pending_requests.pop(msg.correlation_id)
            raise RequestTimeoutError(f"No response from {to_agent}")
    
    async def send_notification(
        self,
        to_agents: list[str],
        action: str,
        payload: dict
    ):
        for agent in to_agents:
            msg = AgentMessage(
                from_agent=self.agent_id,
                to_agent=agent,
                message_type=MessageType.NOTIFICATION,
                action=action,
                payload=payload
            )
            await self.message_queue.put(msg)
```

### 7.2 Error Handling Base Class

```python
from abc import ABC, abstractmethod
from typing import Optional, Type
import logging

class AgentError(Exception):
    def __init__(self, message: str, recoverable: bool = True):
        super().__init__(message)
        self.recoverable = recoverable

class SpecificationError(AgentError):
    pass

class ImplementationError(AgentError):
    pass

class TestError(AgentError):
    pass

class DeploymentError(AgentError):
    pass

class SecurityError(AgentError):
    pass

class AgentErrorHandler(ABC):
    def __init__(self, max_retries: int = 3):
        self.max_retries = max_retries
        self.logger = logging.getLogger(self.__class__.__name__)
    
    @abstractmethod
    async def handle_error(self, error: Exception) -> Optional[dict]:
        pass
    
    async def retry_with_backoff(self, func, *args, **kwargs):
        for attempt in range(self.max_retries):
            try:
                return await func(*args, **kwargs)
            except AgentError as e:
                if not e.recoverable or attempt == self.max_retries - 1:
                    raise
                
                backoff = 2 ** attempt
                self.logger.warning(
                    f"Attempt {attempt + 1} failed: {e}. "
                    f"Retrying in {backoff}s..."
                )
                await asyncio.sleep(backoff)
                
                correction = await self.handle_error(e)
                if correction:
                    kwargs.update(correction)
```

### 7.3 Coder Agent Implementation

```python
class CoderAgent:
    def __init__(
        self,
        agent_id: str,
        communication: AgentCommunication,
        tools: CoderTools
    ):
        self.agent_id = agent_id
        self.comm = communication
        self.tools = tools
        self.error_handler = CoderErrorHandler()
    
    async def implement_feature(self, spec: FeatureSpec) -> ImplementationResult:
        code = await self.tools.generate_code(spec)
        
        try:
            await self.tools.run_tests(code, spec.tests)
            await self.tools.run_linter(code)
            await self.tools.git_commit(code, spec.description)
            
            return ImplementationResult(
                success=True,
                code=code,
                commit_sha=code.commit_sha
            )
        except TestFailure as e:
            await self.error_handler.handle_test_failure(e, code, spec)
            raise
```

### 7.4 DevOps Agent Deployment Pipeline

```python
class DevOpsAgent:
    async def deploy_with_rollback(
        self,
        manifest: DeploymentManifest,
        strategy: DeploymentStrategy = DeploymentStrategy.ROLLING
    ) -> DeploymentResult:
        previous_version = await self.get_current_version(manifest.service)
        
        try:
            # Apply deployment
            await self.apply_manifest(manifest)
            
            # Wait for health checks
            await self.wait_for_health(manifest.service, timeout=300)
            
            # Run smoke tests
            smoke_result = await self.run_smoke_tests(manifest.environment)
            
            if not smoke_result.success:
                raise SmokeTestFailure(smoke_result.errors)
            
            # Update discovery
            await self.update_service_discovery(manifest)
            
            return DeploymentResult(
                success=True,
                version=manifest.version,
                strategy=strategy
            )
            
        except DeploymentError as e:
            self.logger.error(f"Deployment failed: {e}")
            
            # Automatic rollback
            await self.rollback_to(previous_version)
            
            # Notify
            await self.comm.send_notification(
                to_agents=["governance", "oncall"],
                action="DEPLOYMENT_FAILED",
                payload={
                    "service": manifest.service,
                    "error": str(e),
                    "rolled_back": True
                }
            )
            
            raise
```

## 8. Implementation Recommendations

### 8.1 Model Selection by Role

Different agent roles benefit from different model capabilities:

| Agent Type | Recommended Model Profile |
|------------|--------------------------|
| Architect | High reasoning, large context, strong coherence |
| Coder | Fast generation, code-specialized, efficient |
| Tester | Thorough analysis, adversarial thinking |
| DevOps | Reliable execution, tool integration |
| Security | Careful analysis, comprehensive scanning |

### 8.2 Token Budgeting

Effective multi-agent systems manage context carefully:

- **Active Agent Context**: Full project state for current task
- **Recent History**: Last 10 messages from collaborators
- **Reference Material**: Summarized documentation, specs
- **Inactive Modules**: Semantic embeddings for retrieval

### 8.3 Failure Mode Testing

Regularly test failure scenarios:

1. Agent produces incorrect code → Verify tests catch it
2. Agent produces buggy deployment → Verify rollback works
3. Agent misses vulnerability → Security review catches it
4. Agent communication fails → Verify timeout handling
5. Human unavailable → Verify graceful degradation

## 9. Conclusion

This Level 2 document provides the concrete implementation details that transform the five-layer framework from architecture into operational reality. Each agent type possesses a distinct skill taxonomy optimized for its responsibilities, operates using standardized prompt templates, accesses specific tools, implements role-appropriate error handling, and communicates through well-defined patterns.

The key principles underlying these implementations are:

1. **Clear Boundaries**: Each agent knows its responsibilities and limits
2. **Standardized Interfaces**: Consistent message formats enable interoperability
3. **Robust Error Handling**: Recovery mechanisms prevent cascade failures
4. **Human Escalation**: Clear paths to human input when needed
5. **Continuous Verification**: Each stage validates before proceeding

These implementations enable the Software Engineering Fortress to execute software development autonomously while maintaining quality, security, and operational reliability.

---

*Level 3 will address advanced topics including adaptive agent orchestration, learning and improvement mechanisms, and enterprise-scale deployment considerations.*
