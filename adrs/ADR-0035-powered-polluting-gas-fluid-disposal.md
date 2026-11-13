# ADR-0035: Permit Powered, Pollution-Producing Disposal of Gases and Fluids

*Status: Accepted*
*Decision date: 2026-11-13*
*Last updated: 2026-11-13*

Related documents: [Mod Overview](../mod-overview.md), [Minerals and Refining](../minerals-and-refining.md), [Chemical Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), and [Plan](../plan.md).

## Context

The current balanceability rules reject required voiding and instead require a consumer, recovery path, buffer, or production control for each output. This can leave unwanted process gases and fluids with no practical sink; the selected Phase 2 quartz-reduction route produces carbon monoxide. The user decided that any gas or fluid may be released, but every release must consume power and produce pollution.

Angel's provides a relevant precedent: its Petrochem Flare Stack disposes of excess chemicals with a pollution cost, while Angel's Refining provides a Clarifier for unwanted water. Its implementation separates chemical and water disposal categories ([Flare Stack description](https://github.com/Arch666Angel/mods/blob/57a8ea551c99169e1a5173e2f4e1fbb742766249/angelspetrochem/locale/en/petrochem.cfg), [Clarifier description](https://github.com/Arch666Angel/mods/blob/57a8ea551c99169e1a5173e2f4e1fbb742766249/angelsrefining/locale/en/water-treatment.cfg), and [disposal-category helper](https://github.com/Arch666Angel/mods/blob/57a8ea551c99169e1a5173e2f4e1fbb742766249/angelsrefining/prototypes/angels-functions.lua)); these are inspiration, not a feature specification.

## Decision

Use separate disposal facility families: a Gas Flare Stack for gas streams and a Liquid Effluent Clarifier for liquid streams. Either facility may process any stream of its type, including otherwise useful products, through an explicit player-directed disposal operation. Every disposal operation must consume electrical power and generate pollution. Production recipes must not silently delete a gas or fluid output.

This changes the balanceability rule for gas and fluid streams only. Solid coproducts still need a useful consumer, recovery path, bounded buffer, or production control. The Gas Flare Stack must be available no later than the Phase 2 silicon-reduction route that produces carbon monoxide.

The facility split and roles are selected; exact recipes, power draw, pollution output, throughput, construction materials, and research/construction gates remain open.

## Options Considered

1. **Keep the no-disposal rule for all streams.** Not selected; it leaves unwanted gas and fluid outputs without a direct handling path.
2. **Allow gas and fluid disposal without a cost.** Not selected; it makes disposal a free bypass of route balancing and pollution tradeoffs.
3. **Use separate powered, pollution-producing gas and liquid disposal facilities.** Accepted; the Gas Flare Stack and Liquid Effluent Clarifier provide dedicated, legible outlets while preserving a meaningful operating cost.
4. **Use one combined disposal facility for all gas and liquid streams.** Not selected; separate facilities better communicate distinct handling roles.

## Rationale

Separate facilities make gas release and liquid treatment legible as distinct operations. Power demand and pollution make disposal an explicit engineering tradeoff rather than a silent recipe behavior, while leaving useful recovery routes available where they are worthwhile.

## Consequences

- Positive: CO and other unwanted gas or fluid coproducts can be removed without inventing a mandatory consumer for each one.
- Negative or trade-offs: Disposal competes for electrical capacity and increases pollution; an unpowered disposal route cannot clear a blocked stream.
- Follow-up work: Define the facilities' recipes, power draw, pollution emissions, throughput, construction materials, and progression gates.

## Affected Design and Related Decisions

- Design documents: [Mod Overview](../mod-overview.md), [Minerals and Refining](../minerals-and-refining.md), [Chemical Processes](../chemical-processes.md), [Intermediate Products](../intermediate-products.md), [Infrastructure](../infrastructure.md), [Documentation Map](../documentation-map.md), and [Plan](../plan.md).
- Related ADRs: [ADR-0033](ADR-0033-phase-2-submerged-arc-silicon-reduction.md), which selects the silicon-reduction route that produces CO.
- Supersedes / superseded by: Supersedes the former no-required-voiding constraint for gas and fluid streams in the current-state documents. No prior ADR recorded that constraint; solid coproduct handling is unchanged.
