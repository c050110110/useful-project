# Plan Review Rubrics

Apply the common rubric to every plan, then add all domain rubrics that materially match. Treat these as investigative lenses, not a requirement to manufacture a finding for every item.

## Common Core

- **Objective and success**: Is the outcome measurable, and do acceptance criteria prove it rather than merely prove activity occurred?
- **Scope and traceability**: Does every requirement map to an action and verification step? Are exclusions explicit and compatible with the goal?
- **Assumptions and evidence**: Which claims are verified, inferred, or still to verify? Would a false assumption change the approach?
- **Dependencies and sequence**: Are prerequisites, owners, resources, permissions, decision gates, and ordering complete?
- **Interfaces and handoffs**: Are inputs, outputs, responsibilities, state transitions, and ownership at boundaries clear enough to implement?
- **Failure and reversibility**: What can partially fail, leave inconsistent state, become unsafe, or be hard to undo? Are stop, rollback, recovery, and escalation paths proportional to risk?
- **Verification and observability**: Can success, degradation, and failure be observed? Are tests independent of the implementation claim they validate?
- **Proportionality**: Does the plan avoid both missing critical controls and adding unjustified complexity?

## Software, Systems, and Deployment

- Confirm the actual entrypoints, versions, APIs, schemas, permissions, dependencies, and target environments.
- Trace data and control flow across components; check compatibility, concurrency, idempotency, timeouts, retries, partial writes, and cleanup where relevant.
- Check migration and rollback symmetry, preservation of user data, secrets handling, and the effect of interrupted deployment.
- Require acceptance coverage for core behavior, negative paths, integration boundaries, and regression risk; distinguish automated from manual verification.
- Check rollout, health signals, logs, alert thresholds, and a bounded recovery procedure when the change can affect a live system.

## Robotics, Hardware, and Real-Time Control

- Identify the exact device, vendor, model, firmware, coordinate units, reduction ratio, limits, and operating mode; do not transfer settings between brands without evidence.
- Check control-cycle assumptions, scheduling jitter, bus load, synchronization, watchdogs, stale commands, packet loss, error counters, and the consequences of missed deadlines.
- Trace the state machine for startup, mode selection, enable, motion, disable, fault, reset, and restart. Ensure commands are valid for the current state.
- Require conservative position, velocity, torque, acceleration, workspace, thermal, and current limits plus a tested emergency stop independent of the normal command path.
- Cover communication faults, following errors, unexpected disable, sensor disagreement, mechanical obstruction, power loss, and safe recovery without surprise motion.
- Require timestamped logs tied to physical time, device error/status objects, command/feedback samples, cycle diagnostics, and enough context to reconstruct an incident.
- Separate simulation, bench, unloaded, guarded, and production tests. Escalate energy and motion gradually with a human observer and explicit stop criteria.

## Research and Experiments

- Check whether the hypothesis is falsifiable and whether outcomes, variables, controls, confounders, and exclusion rules are defined before data collection.
- Assess sample strategy, power or justification, measurement validity, calibration, missing data, bias, leakage, and data provenance.
- Match the analysis and statistical method to the design; require effect sizes and uncertainty, not only significance where applicable.
- Distinguish exploratory from confirmatory work and prevent post-hoc choices from being presented as preplanned conclusions.
- Require reproducible environment, code, parameters, random seeds, raw-data preservation, analysis traceability, and ethical/privacy approvals where applicable.

## Management and Business

- Check customer or stakeholder outcome, decision rights, accountable owner, contributors, dependencies, budget, capacity, schedule, and milestone exit criteria.
- Distinguish output metrics from outcome metrics; define baseline, target, measurement owner, review cadence, and stop/pivot thresholds.
- Examine incentives, adoption, communication, operational handoffs, legal or contractual constraints, and the cost of delay or reversal.
- Stress-test optimistic assumptions, resource contention, single points of ownership, vendor dependency, and what happens when milestones slip.
- Require a decision log, risk owner, escalation path, and explicit next decision at each major gate.

## Cross-Domain Selection

Combine rubrics when the plan crosses boundaries. Examples:

- An EtherCAT web controller uses Software/Systems plus Robotics/Hardware.
- An experiment using a robot uses Research plus Robotics/Hardware, and Software when analysis or acquisition code is in scope.
- Deploying an AI-assisted business workflow uses Software/Systems plus Management/Business and Research when evaluation validity matters.

State which rubrics were applied in the report. Ignore irrelevant checklist items instead of lowering the verdict for their absence.

