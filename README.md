# Rain Alert for Hanging Laundry

An independent project to warn when laundry is exposed and relevant rain is detected. The first pilot uses a manual “laundry outside” state and a local alert.

## Status

Initial definition. No rain sensor, placement, or physical prototype has been validated.

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
- [Program coordination in Notion](https://app.notion.com/p/416504754f0881afaaa6e4297e39c813).

## Next decisions

Sensor placement, protection, power, manual control, sustained-rain rule, local signal, and handling of splashes or condensation.
