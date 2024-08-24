---
title: "Radar-based position detection"
image:
  path: https://assets.euyuil.com/images/projects/radar-software-running-on-a-computer.jpg
  thumbnail: https://assets.euyuil.com/images/projects/radar-software-running-on-a-computer-400x200.jpg
  caption: "Photo from [Wonderlabs Studio](https://www.wonderlabsstudio.com/)"
tags:
  - wonderlabs-studio
last_modified_at: 2024-08-24T21:17:46+08:00
---

This radar-based position detection system transforms digital art exhibitions by enabling real-time, touchless interaction.

Imagine walking into an exhibition where flowers on a screen move towards you as you approach, or waves ripple across a virtual ocean where you step. These immersive experiences are just the beginning of what radar technology can bring to interactive spaces.

<video width="100%" height="auto" autoplay loop muted>
  <source src="https://assets.euyuil.com/videos/projects/radar-customer-story-demos.mp4" type="video/mp4">
</video>
*Customer projects powered by radar-based position detection, video from [Wonderlabs Studio](https://www.wonderlabsstudio.com/)*

## Why radar?

Radar is ideal for this application because it operates independently of lighting conditions and doesn't require a clear line of sight. This makes it perfect for dynamic environments like exhibitions, where traditional optical systems might struggle. By integrating radar technology, it's ensured that these interactions are smooth, responsive, and unaffected by lighting barriers.

![Radar vs optical detection, conceptual illustration](https://assets.euyuil.com/images/projects/radar-optical-detection-comparison-topdown-grayscale.jpg)
*Radar vs optical detection, conceptual illustration*

### Comparison of radar and optical detection technologies

| Feature | Radar solution | Optical solution |
|---------|----------------|------------------|
| **Lighting dependency** | ✅ **Independent** - Operates effectively without relying on stable lighting conditions. | ❌ **Dependent** - Requires stable and consistent lighting to function accurately. |
| **Processing complexity** | ✅ **Efficient** - Runs fast signal processing algorithms on cost-effective hardware. | ❌ **Complex** - Utilizes advanced machine learning algorithms that require expensive hardware. |
| **Latency** | ✅ **Low** - Delivers quick response times, critical for real-time interaction. | ❌ **High** - Generally experiences slower response times due to intensive processing. |
| **Framerate** | ✅ **High** - Maintains a high framerate, allowing for smooth and accurate detection. | ❌ **Low** - Often operates at a lower framerate, affecting detection smoothness. |
| **Multi-object detection**| ✅ **Efficient** - Capable of detecting multiple objects simultaneously with minimal performance impact. | ❌ **Challenging** - Performance degrades when multiple objects are detected. |

## Use cases

<div class="container-fluid px-0">
  <div class="row">
    <div class="col">
      <img alt="Interactive spaces" src="https://assets.euyuil.com/images/projects/radar-use-interactive-spaces.webp"
        class="float-left me-3 mb-4 d-none d-sm-block" width="256px"/>
      <h3>Interactive spaces</h3>
      <p>✨ <strong>Enhanced visitor interaction</strong>: Use radar to create responsive digital displays that react to gestures and movements in exhibitions, stores, and public spaces.</p>
      <p>👐 <strong>Touchless control and accessibility</strong>: Implement radar-based touchless systems in public areas to improve accessibility and hygiene.</p>
    </div>
  </div>
  <div class="row">
    <div class="col">
      <img alt="Security and safety" src="https://assets.euyuil.com/images/projects/radar-use-security-and-safety.webp"
        class="float-right ms-3 mb-4 d-none d-sm-block" width="256px"/>
      <h3>Security and safety</h3>
      <p>🚨 <strong>Intrusion detection</strong>: Protect buildings with radar-based security systems that detect unauthorized entry.</p>
      <p>🕵️ <strong>Behavior recognition</strong>: Implement radar systems for automated door control and behavior recognition in sensitive areas.</p>
    </div>
  </div>
  <div class="row">
    <div class="col">
      <img alt="Robotics and navigation" src="https://assets.euyuil.com/images/projects/radar-use-robotics-and-navigation.webp"
        class="float-left me-3 mb-4 d-none d-sm-block" width="256px"/>
      <h3>Robotics and navigation</h3>
      <p>🌍 <strong>Environment sensing</strong>: Enable robots to recognize their surroundings for safer and more efficient operation.</p>
      <p>🚗 <strong>Obstacle detection</strong>: Use radar for automatic navigation vehicles (AGV) to detect obstacles and navigate safely.</p>
    </div>
  </div>
</div>

## Technical overview

This solution integrates advanced technologies, including radar input protocols, object detection algorithms, and sophisticated touch input recognition, to detect and interpret human gestures and positions in real-time.

For hardware, the **radar sensor array** is strategically positioned to ensure optimal coverage.

### Software architecture

The software system is constructed with a robust architecture known as the **event pipeline**, designed to seamlessly translate radar events into actionable data, particularly touch input events, through the touch input protocol.

```mermaid
flowchart LR
  A[Radar event<br/>reader]
  B[Cartesian coordinate<br/>translator]
  C[Object detection<br/>module]
  D[Physics module]
  E[Touch event<br/>sender]
  F[Gesture<br/>library]
  G[Customer<br/>application]

  subgraph X[Event pipeline]
    direction TB
    A -->|Raw events| B
    B -->|Detected points| C
    C -->|Object positions| D
    D -->|Physical data| E
  end

  subgraph Y[Downstream system]
    direction TB
    F
  end

  subgraph Z[Downstream system]
    direction TB
    G
  end

  X -->|Touch<br/>events| Y
  Y -->|Gesture<br/>events| Z
```
*Overview of the radar-based detection system architecture and event pipeline*

The event pipeline includes the following components, where each module's output serves as the input for the next:

- 📡 **Radar event reader**: Utilizes radar input protocols to read data and translate it into geometric data.
- 🔄 **Cartesian coordinate translator**: Converts initial geometric data into Cartesian coordinates.
- 🎯 **Object detection module**: Transforms Cartesian points into object position information, reducing noise and clustering similar points.
- ⚙️ **Physics module**: Converts object position information into physical data, including velocity and acceleration.
- 📲 **Touch event sender**: Sends touch information using the touch input protocol, feeding it into the downstream system.

The **gesture library**, developed separately from the radar system, can be integrated as a downstream component to enable intuitive user interactions. This library includes a collection of recognized gestures, enhancing the system's capability to identify key features for gesture recognition.

The radar solution and gesture library empower the customer's application, ensuring it receives high-quality touch events that meet their specific requirements.

### Key features and benefits

- 🎯 **High precision**: Enables accurate detection of gestures and positions, significantly enhancing user interaction.
- ⚡ **Real-time processing**: Provides immediate responses to movements, ensuring a seamless experience.
- 🌍 **Scalability**: Easily adaptable to various environments and applications.

## Customers benefiting from this solution

- [Wonderlabs Studio](https://www.wonderlabsstudio.com/)
