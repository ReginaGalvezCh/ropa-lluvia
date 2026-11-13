# Specification 001: Rain Alert for Hanging Laundry

**Status:** proposal for validation. No location, sensor, or physical prototype has been validated.

## Purpose and use scenario

Give the person time to bring in laundry hanging on a narrow balcony when rain could reach it. The person indicates that laundry was left outside and may move away from the balcony. This pilot does not measure whether the laundry is dry.

## First pilot scope

- The person manually turns the “laundry outside” state on or off. Its current value must be visible near the drying area and easy to change when hanging or removing laundry.
- The module observes rain at a nearby point representative of the laundry's exposure.
- If “laundry outside” is active and sustained rain is detected, it gives a local signal.
- If “laundry outside” is inactive, it does not give a bring-in-laundry alert.
- If measurement fails or becomes stale, it reports “rain state unknown” rather than treating the state as dry.
- It does not continuously repeat the same alert. How to silence and reset it will be decided after observing use.

The central display and message transport are outside this pilot. A future integration should convey source, type, severity, observation time, and validity through a shared contract that has not yet been agreed.

## Placement and protection: decide before choosing hardware

Compare at least two possible mounting points near the drying area. For each, record a photo or sketch covering:

1. Distance and height relative to the laundry; whether water reaches it when water reaches the laundry; and whether it sits under a different roof or edge.
2. Exposure to wind-driven rain, dripping from above, watering, splashes, and condensation.
3. Walking space on the balcony, mounting stability, and access to the “laundry outside” control.
4. A path that keeps water away from electronics, the need to expose the rain-sensing area, and maintenance access.
5. Whether the local signal can be perceived from inside the apartment and where power might be placed.

Do not choose a board, sensor, final enclosure, or power arrangement until these points and initial observations at the location have been reviewed. No powered component will be exposed to water during initial exploration.

## “Laundry outside” mode

Manual activation is the starting reference. Laundry presence will not be inferred from moisture or rain. Before implementation, decide whether the control is a position switch or a button with an indicator; in either case, the person must be able to recognize the active state. After a restart, the state must not become ambiguous or silently switch to “no laundry”: test whether it is retained or requires confirmation.

Usage risks include forgetting to activate the mode when hanging laundry or leaving it active after removing laundry. Record both errors in user tests. Consider automatic detection only if it demonstrates a useful improvement.

## Alert rule and false alarms

“Sustained rain” means a rain-compatible reading over an interval that still needs calibration on the balcony. A single drop or brief splash is not enough by itself. Observe separately rain that reaches the laundry, rain that reaches only the sensor, dripping from a surface, splashing, condensation, and sensor drying. Set duration, intensity, and reset conditions from those observations rather than inventing thresholds before measuring.

The local signal remains the pilot outcome even without a network. If messages are added later, a reading without a valid timestamp or outside its validity period must not be displayed as current rain.

## First validation plan

Observe the location without powered electronics first. Record date, time, placement, weather, actual laundry presence, and which areas became wet. Controlled application of water may check sensor behavior, but it must be recorded as a simulation rather than real rain.

| Scenario | Expected result |
| --- | --- |
| Sustained water at a point representative of laundry exposure; mode active | One recognizable local signal; record time to alert. |
| Same condition; mode inactive | No bring-in-laundry alert. |
| Isolated brief splash | Does not automatically become a sustained-rain alert. |
| Condensation or dripping from above | Record whether they trigger an alert and whether they pose a real risk to the laundry. |
| Water reaches the laundry but not the sensing point | Identify a placement failure; do not claim the chosen point works. |
| Measurement interrupted or stale | Show unknown, distinct from dry. |
| Restart while laundry is outside | Manual state remains understandable and verifiable; record whether confirmation is needed. |
| Alert active while rain continues | Do not repeat continuously; document how it is silenced and reset. |

For each trial, record configuration, observed result, response time, photos or video when useful, and any false alert or missed alert. Numerical criteria for response time and false-alert rate will be agreed after the first observation, before accepting the pilot.

## Criteria for moving to hardware design

- A candidate placement is backed by observations of sensor and laundry exposure.
- The manual state and local signal are clear in the use setting.
- The main sources of false alerts and missed alerts at the location are known.
- There is a way to distinguish current readings, stale readings, and failure.
- Measurable acceptance criteria for the prototype have been defined.

## Out of scope for now

Weather forecasting, claiming that laundry is dry, automatic laundry detection, component purchasing, and central-display integration.
