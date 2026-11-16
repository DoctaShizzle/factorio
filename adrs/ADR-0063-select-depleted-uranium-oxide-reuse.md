# ADR-0063: Select Civilian Reuse for Depleted Uranium Oxide

*Status: Accepted*
*Decision date: 2026-11-16*
*Last updated: 2026-11-16*

Related documents: [Intermediate Products](../intermediate-products.md), [Power System](../power-system.md), [Chemical Processes](../chemical-processes.md), [Infrastructure](../infrastructure.md), [Military System](../military-system.md), and [Plan](../plan.md).

## Context

[ADR-0053](ADR-0053-select-depleted-uf6-deconversion.md) selects depleted-UF6 deconversion to uranium oxide and HF. [ADR-0054](ADR-0054-select-depleted-uf6-output-fates.md) assigns later uranium use to the oxide without selecting a consumer. The fission review identified that construction or ammunition demand cannot be assumed to absorb continuous tails production. The user approved civilian reuse, optional military applications, and a separate surplus-handling path.

Depleted oxide is not qualified enriched fuel. It also differs from uranium recovered after reactor discharge, whose return to the fuel front end is selected in [ADR-0066](ADR-0066-select-phase-2-nuclear-recovery-flows.md).

## Decision

1. Use stabilized depleted-uranium-oxide shielding ceramics as the baseline civilian reuse capability in Phase 2. Nuclear-processing buildings and waste casks are intended consumers; exact product names, oxide form, stabilization chemistry, recipes, and construction variants remain open.
2. Keep depleted oxide, recovered spent-fuel uranium oxide, and qualified enriched fuel distinct in product roles and recipe eligibility. Do not turn depleted oxide directly into qualified fuel.
3. Keep suitable ordinary shielding available for first nuclear equipment and waste packaging. Depleted-uranium shielding is an alternative, not a bootstrap prerequisite or a continuing uranium requirement for thorium.
4. Permit optional conventional military uses of depleted uranium as candidates, without selecting a weapon roster, a military recipe, or a core/extension disposition. Ammunition consumption is not required for fission operation.
5. Route surplus depleted oxide without a current consumer through the conditioned nuclear-solid endpoint in [ADR-0067](ADR-0067-engineered-terminal-nuclear-waste-disposal.md). Reuse remains the baseline useful destination; construction demand is not a guaranteed steady-state sink.
6. Do not add a breeder, plutonium/MOX branch, or unlimited tails-re-enrichment loop to erase the surplus. Numerical material and power balances remain deferred.

## Options Considered

1. **Return all depleted oxide directly to fuel production.** Not selected; it confuses material grade with chemical form and does not eliminate enrichment tails.
2. **Make ammunition the required sink.** Not selected; peaceful or low-combat operation would then block fuel production.
3. **Use civilian shielding, retain optional military uses, and provide controlled surplus handling.** Selected; it gives the material a genuine role without assuming unlimited demand.
4. **Add an advanced fuel cycle solely to consume tails.** Not selected; that is a separate reactor/fuel-cycle decision with much broader scope.

## Rationale

The investigated [DUCRETE concept](https://en.wikipedia.org/wiki/Ducrete) provides a precedent for stabilized uranium-oxide aggregate in shielding; it is not presented as standard commercial practice. The game can use this material role while retaining the distinction between reuse and terminal handling.

## Consequences

- Positive: depleted oxide has a concrete civilian use and cannot silently substitute for enriched fuel.
- Negative or trade-offs: shielding demand is finite, and surplus management still has a cost and footprint.
- Follow-up work: validate Phase 2 stabilization/forming and ordinary-shielding alternatives in coverage; define product identities, construction variants, quantities, and gates in their owning phases.

## Affected Design and Related Decisions

- Design documents: [Intermediate Products](../intermediate-products.md) owns product roles; [Chemical Processes](../chemical-processes.md) owns conditioning; [Infrastructure](../infrastructure.md) owns equipment and construction uses; [Power System](../power-system.md) owns fuel-cycle direction; [Military System](../military-system.md) owns optional combat uses.
- Related ADRs: [ADR-0051](ADR-0051-defer-phase-2-uranium-enrichment-target.md), [ADR-0053](ADR-0053-select-depleted-uf6-deconversion.md), [ADR-0054](ADR-0054-select-depleted-uf6-output-fates.md), [ADR-0066](ADR-0066-select-phase-2-nuclear-recovery-flows.md), and [ADR-0067](ADR-0067-engineered-terminal-nuclear-waste-disposal.md).
- Supersedes / superseded by: Resolves ADR-0054's specific oxide-use deferral while retaining its uranium-oxide recovery and HF-reuse decisions.
