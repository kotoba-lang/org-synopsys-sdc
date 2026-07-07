# kotoba-lang/org-synopsys-sdc

Zero-dep portable `.cljc` implementation of a simplified subset of SDC
(Synopsys Design Constraints), the TCL-based de facto industry-standard
format for timing/design constraints consumed by STA and synthesis
tools. Part of the kotoba-lang EDA standards-substrate reverse-domain
naming initiative (ADR-2607072500, `com-junkawasaki/root`). Vendor-
prefixed (`org-<vendor>-<spec>`) rather than standards-body-prefixed,
since SDC is a Synopsys-originated de facto standard, not a formally
ratified spec — same naming variant as other vendor-format repos in
this family (e.g. `org-synopsys-liberty`).

| Namespace | Purpose |
|---|---|
| `sdc.clock` | create_clock model + duty-cycle computation |
| `sdc.io-delay` | set_input_delay/set_output_delay model + effective-delay resolution |
| `sdc.path-exception` | set_false_path/set_multicycle_path model + path-coverage check |
| `sdc.parser` | simplified TCL-style tokenizer/parser for the above commands |

## Status

New — simplified subset covering 5 of the most common SDC commands
(create_clock, set_input_delay, set_output_delay, set_false_path,
set_multicycle_path). Not implemented: clock groups, generated clocks,
case analysis, derate, most other SDC commands (SDC has 100+). 14 tests
/ 69 assertions, 0 failures.

## Develop

```bash
clojure -M:test
```
