## Verdict

This is a strong independent rediscovery of an existing connected-transportation concept. The advisory version is already deployed in some places, while automatic vehicle control and joint car–signal optimization remain active research and limited demonstration technologies.

The closest names are:

- **Signal Phase and Timing (SPaT)**
- **Green Light Optimal Speed Advisory (GLOSA)**
- **Eco-Approach and Departure (EAD)**
- **Vehicle-to-Infrastructure / Vehicle-to-Everything (V2I/V2X)**
- **Cooperative automated driving**

Your proposal is therefore not novel as a broad concept. It is technically sound, however, provided “eliminate stopping” is narrowed substantially.

## 1. Capture the Idea

The strongest formulation is:

> Traffic signals continuously broadcast their current state and predicted phase changes. Approaching vehicles use that information, together with their distance and traffic conditions, to calculate a safe speed trajectory that minimizes braking, idling, and unnecessary stops.

There are actually three ideas bundled together:

1. **Information:** The signal tells the vehicle when green will begin or end.
2. **Vehicle control:** The vehicle recommends or automatically follows an appropriate speed.
3. **System optimization:** Many vehicles arrive in usable green windows, smoothing the entire traffic stream.

Important ambiguities:

- Is the timing merely displayed to the driver, or does the car control its own speed?
- Does the signal broadcast a fixed schedule, predict an adaptive schedule, or negotiate with vehicles?
- Does “avoid stopping” mean under light traffic, or even during rush-hour congestion?
- Does the system account for queues, pedestrians, cyclists, turning traffic, buses, and emergency vehicles?

Those distinctions determine whether this is a straightforward driver-assistance feature or a much harder citywide coordination system.

## 2. Decomposition

| Component | Type | Assessment |
|---|---|---|
| Signals can transmit their phase and timing | Proposed mechanism | Already established as SPaT |
| A car can calculate whether it will reach the light during green | Logical deduction | Correct |
| The car can slow gradually rather than race to a red light | Proposed mechanism | Correct and already implemented |
| Automatic acceleration and braking can follow that trajectory | Technical proposal | Demonstrated experimentally |
| Fewer stops reduce idling, acceleration losses, and brake use | Prediction | Generally sound |
| Coordinating many cars can smooth traffic | Prediction | Plausible and supported by modeling |
| Cars can usually avoid stopping entirely | Assumption | Conditional on demand, queues, and speed flexibility |
| This can eliminate traffic jams | Speculation | Overstated; intersection capacity still exists |
| The light can always say exactly when it will change | Assumption | False for many adaptive or actuated signals |

The later benefits depend on more than communication. They require accurate timing predictions, sufficient road capacity, controllable vehicles, queue awareness, and widespread compliance.

## 3. Does It Already Exist?

### Direct match: GLOSA and Eco-Approach and Departure

GLOSA uses traffic-signal timing data, vehicle position, and speed to recommend a speed that should reach the intersection during green. That is essentially the idea as described.

Audi already offers a traffic-light information service in some cities: the vehicle receives data from the traffic-control system, provides a suitable approach speed, and displays a countdown when stopping is unavoidable. [Audi’s description of Traffic Light Information](https://www.audi.com/en/audi-technology-lexicon-7180/user-operation-displays-and-infotainment-16948)

The U.S. Department of Transportation calls the broader application **Eco-Approach and Departure**, using SPaT communication to create energy-efficient vehicle trajectories. [USDOT EAD study summary](https://www.itskrs.its.dot.gov/2023-b01748)

### Close relative: automated speed control

Your automatic-control version goes beyond most consumer implementations, which generally advise the driver. But it has already been tested.

FHWA’s partially automated **GlidePath** research vehicle controlled its approach to an intelligent intersection and reported a 22% fuel-saving benefit in its test setting. That is a proof of concept, not evidence that every city would obtain 22%. [FHWA Saxton Laboratory](https://www.fhwa.dot.gov/publications/research/operations/17031/index.cfm)

FHWA’s CARMA research goes further by coordinating automated vehicle trajectories with optimized signals—the infrastructure and vehicles jointly decide how traffic should move. [FHWA cooperative signal optimization report](https://www.fhwa.dot.gov/publications/research/operations/22052/22052.pdf)

### Older relative: the “green wave”

Even without vehicle communication, cities have long coordinated consecutive signals so that a platoon traveling at approximately the intended speed encounters successive green lights. Your proposal personalizes that principle for each vehicle and allows it to react dynamically. [FHWA Traffic Signal Timing Manual](https://ops.fhwa.dot.gov/publications/fhwahop08024/chapter6.htm)

**Novelty result: Direct Match.** Almost every major component has an established precedent.

## 4. Would It Actually Work?

Yes, within limits.

A basic implementation would work like this:

1. The signal broadcasts its present phase and predicted timing.
2. The car determines its lane, intended movement, distance, and current speed.
3. It estimates the queue ahead and downstream congestion.
4. It calculates a legal, comfortable speed range that reaches an available green window.
5. It recommends that speed or applies gentle automatic control.
6. If no feasible trajectory exists, it brakes normally and stops.

The physical reasoning is valid. Smooth deceleration wastes less energy than maintaining speed until the last moment, braking heavily, idling, and accelerating again.

USDOT summaries report simulation results of up to 15% lower fuel consumption and 85% lower waiting time at equipped intersections, although these are scenario-dependent upper results, not universal expectations. [USDOT V2X briefing](https://www.itskrs.its.dot.gov/sites/default/files/2025-01/executive-briefing/Executive%20Briefing%202024_Vehicle-to-Everything%20%28V2X%29%20Technology_FINAL508_0_0_0.pdf)

### What limits it

**Signal timing is not always exactly predictable.** Many lights are actuated: green duration changes according to vehicle detections, pedestrian calls, transit priority, and other demands. FHWA describes green intervals that vary from cycle to cycle. A vehicle may receive a predicted interval rather than one guaranteed change time. [FHWA actuated signal control](https://ops.fhwa.dot.gov/trafficanalysistools/tat_vol4/app_f.htm)

**A green light does not guarantee a clear path.** A queue may extend backward from the intersection, or downstream traffic may block the exit. Signal timing alone is insufficient; the vehicle needs queue and downstream-occupancy estimates.

**Independent optimization can become systemically bad.** The speed best for one car may interfere with vehicles behind it. A scalable system must allocate feasible green windows across groups of vehicles, not tell every vehicle independently to chase the same final second of green.

**Mixed traffic reduces control.** An automated car cannot follow its optimal trajectory if a human-driven car is immediately ahead. Slowing unusually early may also frustrate or destabilize following traffic.

**Pedestrians and conflicting approaches still need right-of-way.** The system cannot optimize only for equipped cars. Signals exist largely because incompatible movements cannot safely occupy an intersection simultaneously.

**Communication cannot override safety.** The car must still detect red lights, stopped traffic, pedestrians, and emergency situations locally. A corrupted, stale, spoofed, or incorrect timing message cannot be treated as permission to enter.

## 5. What Is Actually Interesting?

The broad idea is known, but one distinction remains important:

> Merely broadcasting the countdown is much less powerful than jointly coordinating the signal, the approaching vehicles, queues, and pedestrian demand.

A one-way system helps individual drivers coast. A two-way system could:

- Assign different vehicles different green windows.
- Extend or shorten phases within safe constraints.
- Form moving platoons before they reach the intersection.
- Give buses and emergency vehicles controlled priority.
- Prevent vehicles from accelerating toward a green they cannot actually enter.
- Optimize an entire corridor rather than one intersection.

That is the serious research version. It resembles ongoing cooperative-automation work, but the practical algorithms, deployment strategy, mixed-traffic behavior, and institutional coordination are not “solved.”

## 6. Try to Kill It

The strongest objection is **intersection capacity**.

Suppose two heavily traveled roads cross. Only compatible movements can use the intersection simultaneously. If vehicles arrive faster than their allocated green phases can process them, a queue must form somewhere.

Changing vehicle speeds can turn a stationary queue into a slowly moving queue, but it cannot make the excess demand disappear. The waiting may occur 300 meters before the intersection instead of at the stop line.

FHWA describes a finite saturation flow rate once vehicles are moving through a green phase. Communication can reduce start-up losses and improve arrival timing, but it does not remove that capacity ceiling. [FHWA signal operation fundamentals](https://ops.fhwa.dot.gov/publications/fhwahop08024/chapter3.htm)

**Does the idea survive?** Yes—but as a method for reducing stops, energy consumption, and some delay, not as a general cure for congestion.

## 7. Try to Rescue It

The smallest defensible modification is:

> Traffic signals broadcast continuously updated phase-time ranges, while connected cars combine those ranges with queue estimates and local sensors to recommend or automatically follow safe, energy-efficient approach trajectories. The goal is to reduce unnecessary stops under low-to-moderate demand, not guarantee nonstop travel.

The strongest first deployments would be:

- Coordinated suburban arterials
- Late-night or off-peak corridors
- Bus and truck fleets
- Controlled campuses, ports, or industrial parks
- Corridors with reliable central signal data
- Electric vehicles, where smoother acceleration can improve range

The message should be treated as planning information—not an intersection reservation or proof that the road is clear.

## 8. Best Next Test

Build a five-intersection corridor in the open-source [SUMO traffic simulator](https://eclipse.dev/sumo/). It supports individual vehicles, pedestrians, traffic-light control, automated vehicles, communications, and emissions estimates.

Compare:

1. Normal coordinated signals
2. Timing displayed to drivers
3. Automatic eco-approach control
4. Joint vehicle-and-signal optimization

Test each at:

- 0%, 20%, 50%, and 100% connected-vehicle adoption
- Light, moderate, and oversaturated traffic
- Fixed and actuated signals
- With and without pedestrian calls
- With realistic queues and communication errors

Measure total travel time, stops, throughput, fuel or electricity, hard braking, and queue length.

The decisive falsification test is this: **Does total network delay improve, or does the system merely replace stopped queues with slow-moving queues farther upstream?**

## Final Reality Check

**The Idea:**  
Traffic signals tell approaching cars when their phases will change, allowing the cars to adjust speed automatically and arrive during green.

**Closest Existing Concept:**  
GLOSA, SPaT-based Eco-Approach and Departure, and cooperative automated driving.

**What’s Already Known:**  
Signal timing can be transmitted to vehicles; cars can calculate green-compatible speeds; smoother approaches can reduce stops, energy consumption, emissions, and braking.

**What’s Actually Interesting:**  
Coordinating vehicle trajectories, signal timing, queues, and nonvehicle road users across an entire corridor—not merely showing drivers a countdown.

**What Breaks:**  
Signals have finite capacity. During heavy demand, some traffic must be delayed, and adaptive signals cannot always promise an exact change time.

**The Rescue:**  
Aim to minimize unnecessary stops using rolling timing predictions and queue awareness, while retaining normal safety controls and accepting that stops remain unavoidable under congestion.

**Best Next Test:**  
A SUMO corridor simulation across different traffic levels, equipment penetration rates, pedestrian demand, and timing uncertainty.

**Classification:** **REDISCOVERED**  
Secondary: **KNOWN**, **INTERESTING**, and partially **FLAWED** in its strongest “eliminate stops and jams” form.

**Potential: High as a transportation technology; low as a novel invention.**  
The central concept is already real and technically credible. Its benefits are meaningful, but deployment, mixed traffic, safety, timing uncertainty, and intersection capacity prevent it from delivering universal nonstop travel.
