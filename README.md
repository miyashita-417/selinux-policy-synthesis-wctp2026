# Automated Synthesis of Least-Privilege SELinux Policies via SMT-Based Optimization

This repository contains the verification code and supplementary materials for the paper presented at WCTP 2026.

In this research, we propose a method to automatically synthesize SELinux policies with least privilege using the Z3 solver by converting functional requirements indicating operational intent into logical constraints.

## Repository Structure

- `src/target/mydaemon.c`: Virtual daemon process used for verification.
- `src/tool/solver.py`: Automatic policy synthesis tool using an SMT solver.
- `documents/constraints.md`: Detailed definitions of functional requirements and logical constraints omitted from the paper due to space limitations.

## Requirements

- Python 3.x
- z3-solver
