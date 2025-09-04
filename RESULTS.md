# **Element to Function Mapping**

### **Solar Panels & MPPT**

This is the section on the far left of the circuit labeled "Simulated Orbit". The timed 811mA current source represents the combined, ideal power output from the solar panels after being optimized by the Maximum Power Point Tracking (MPPT) controller.

### **Batteries**

This corresponds directly to the component labeled "Satellite's Battery" in the diagram. The model, using two voltage sources and a 100mΩ series resistor, represents the 7.4V battery pack and its internal resistance, as required by the project specifications.

### **Energy Management & Power Busses Control**

These logic-based functions are represented in the circuit by the clocks (CLK) and the MOSFETs. This switching system controls the flow of power—turning the solar source on/off and activating the TT\&C and ADCS loads at specific times—which is the primary role of management and bus control.

### **Satellite (Loads)**

This final block represents all the power-consuming subsystems. In the circuit, these are all the components to the right of the battery: the Payload (LED), the On Board Computer (55Ω resistor), the TT\&C (20Ω resistor), and the ADCS (15Ω resistor). Each is modeled as a timed load, matching the project's requirements.

# **Observations**

Didn't quite understand what the observation (here) is suppoed to capture, but I tried to explain what I understood. -

The simulation illustrates the basic charge and discharge cycle of the power system of the satellite within a 90-minute (90 second simulation time) orbit. Throughout the 60-minute (60 second simulation time) sun phase, the solar array (current source) is operational, providing power to the always on On Board Computer (OBC) and sun only Payload, while also charging the battery, as evidenced by a positive direction of current flow.

In the 30 minute (30 second simulation time) eclipse period, the solar source is disabled, and the battery takes over automatically, now discharging to supply loads like the OBC and burst like intermittent loads like the TT\&C and ADCS. The battery current reverses direction (turns negative) to mark this switch. This sun charging and eclipse discharging cycle, as it manages the different timed loads, assures the EPS is functioning properly by providing a constant power supply for the satellite's subsystems.

(Gemini was used to format this document.)
