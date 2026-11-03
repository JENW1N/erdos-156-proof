# Erdős 156 — Small maximal integer Sidon sets

This repository contains the manuscript and reproducible Lean proof for the eventual O(N^(1/3)) upper bound on the size of an inclusion-maximal Sidon subset of {1,...,N}.

The authors are **Will Howe (@h0w4rd), Grant Huffman (@ghuffy), Jensen Kohlmeyer (@JENW1N), and Liam Kruer (@lkruer)**. The submitting author confirms joint contributions to the mathematics and formalization. The manuscript describes substantial OpenAI Codex assistance.

- [Manuscript](paper/proof.pdf), November 2, 2026, Theorem 1.1 and Sections 2–9.
- [Lean project and build instructions](lean/README.md).
- [Verification report](lean/verification/report.md).
- [Original problem](https://www.erdosproblems.com/156).
- [Prize entry JSP-000154](https://github.com/TheJustinSunPrize/awards/blob/main/problems/catalog-0101-0200.md#JSP-000154).
- [Submission record](submission.md).

## Reproduce the proof

Use Lean 4.35.0-rc2 as specified by `lean/lean-toolchain`. From `lean/`, run the following commands with the pinned dependency manifest.

```sh
lake exe cache get
lake build +Main
lake env lean Erdos156.lean
lake env lean Audit.lean
lake env lean AuditAll.lean
lake env leanchecker --verbose Statement Erdos156 Main
```

The main declaration is `Erdos156.solved`. All 178 public theorem declarations passed their axiom audit with only the standard Lean foundations `propext`, `Classical.choice`, and `Quot.sound`. Source checking and kernel replay from trusted imports passed.

## Publication provenance

The authors first published these verified files at [lkruer/conjectures, commit bb0951eb0c8155f10fddb74fa66162f4b5cb0668](https://github.com/lkruer/conjectures/tree/bb0951eb0c8155f10fddb74fa66162f4b5cb0668/problems/erdos-156). Jensen Kohlmeyer requested this dedicated coauthor-owned repository for submission through JENW1N. The supplied manuscript, original source files, and audited Lean project retain their recorded content hashes. All four authors retain their credits.
