# Verification strategy

Verification is a first-class project deliverable, not a final phase.

## Evidence ladder

### 1. Directed simulation

Test reset behavior, every instruction, every stall condition, FIFO boundaries, and pin direction changes. Keep small waveform-based regression cases for timing-sensitive behavior.

### 2. Protocol conformance

Run protocol firmware against independent software models and reusable bus agents. Cover normal traffic and errors such as malformed frames, clock stretching, arbitration loss, FIFO starvation, and reset during traffic.

### 3. Differential co-simulation

Maintain a cycle-accurate architectural model. Given the same firmware and pin inputs, compare architectural state and pin outputs against RTL every cycle or at every retired instruction.

### 4. Constrained-random testing and coverage

Generate legal and intentionally illegal instruction streams, randomized host traffic, and randomized pin timing. Define functional coverage from the specification instead of relying only on line coverage.

### 5. Formal verification

Candidate property groups:

- instruction timing and progress under documented assumptions;
- FIFO overflow/underflow behavior;
- shift-counter bounds;
- decoder completeness;
- reset convergence;
- open-drain safety and output-enable behavior;
- ownership rules when engines can address the same pin;
- equivalence between selected model transitions and RTL transitions.

State the bounds and assumptions for every proof. A bounded proof must not be described as an unbounded guarantee.

### 6. Mutation testing

Introduce controlled RTL or model faults and report which tests or properties detect them. Track surviving mutants to identify gaps. If AI is used to propose tests or assertions, only tool-checked results count as evidence.

### 7. Implementation-level validation

Run gate-level simulation, static timing analysis, design-rule checks, and the full Tiny Tapeout flow. Later, execute the same protocol firmware on an FPGA and, if fabricated, on silicon.

## Result format

Every reported result should include:

- code commit;
- tool and version;
- command or script;
- target configuration and clock;
- pass/fail criteria;
- output artifact or log;
- known exclusions.
