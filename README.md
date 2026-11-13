# Rain Alert for Hanging Laundry

An independent project to warn when laundry is exposed and relevant rain is detected. The first pilot uses a manual “laundry outside” state and a local alert.

## Status

Public design and discovery stage. The repository currently contains specifications and a proposed technology map; it does not yet contain firmware or a working prototype. No rain sensor, placement, or physical test has been validated.

## Initial scope

- Manually switch the “laundry outside” state on or off.
- Detect sustained rain using a rule tested at the real location.
- Alert locally only when laundry is outside and rain is relevant.
- Show an unknown state if measurement fails or becomes stale.
- Consider a central-display alert later.

## Technology map

| Area | Current direction | Status |
| --- | --- | --- |
| Rain sensing | Observe rain near the drying area and distinguish sustained rain from splashes or condensation. | Required capability; sensor and mounting open. |
| Manual control and local alert | A visible “laundry outside” control and an alert that works locally. | Pilot direction; switch, indicator, and alert hardware open. |
| Connectivity | Local Wi-Fi may carry a later alert to the central display. | Candidate; not needed for the first local test. |
| Platform and power | Controller, firmware, protected enclosure, and power source. | Open pending balcony observations. |
| Documentation and localization | Living English specifications; English and Spanish product text. Use Lingui if a JavaScript/TypeScript interface is built. | Language direction agreed; Spec Kit and Lingui not installed. |

## Documents

- [Pilot specification](specs/001-rain-alert/spec.md).
- [Shared method and architecture](docs/method.md).

## Next decisions

Sensor placement, protection, power, manual control, sustained-rain rule, local signal, and handling of splashes or condensation.

## Follow the work

This project is being shared early so its requirements, experiments, and trade-offs can be reviewed as they develop. The pilot specification describes intended behavior, not a validated device. Upcoming measurements and design decisions will be recorded here; GitHub Issues will track bounded next steps. Suggestions and questions are welcome through Issues.

## Safety and privacy

Do not publish Wi-Fi credentials, device tokens, exact home details, or unredacted balcony photos. Test observations should describe exposure and placement without identifying the home.

## License

[MIT](LICENSE) covers the current repository content. Hardware design files, if added later, will have their licensing and manufacturing information reviewed before publication.
