# 3D Architecture Studio & Spatial Workstation CDN

[![Architecture: Spatial WebGL](https://img.shields.io/badge/Architecture-Spatial_WebGL_Workstation-0A0D14?style=for-the-badge&logo=webgl&logoColor=white)](https://github.com/naishal988)
[![Security: Zero--Trust](https://img.shields.io/badge/Security-Zero--Trust_Architectures-0A0D14?style=for-the-badge&logo=auth0&logoColor=white)](https://github.com/naishal988)
[![Runtime: Three.js / R3F](https://img.shields.io/badge/Runtime-Three.js_%2F_React_Three_Fiber-0A0D14?style=for-the-badge&logo=three.js&logoColor=white)](https://github.com/naishal988)
[![Animation: GSAP Core](https://img.shields.io/badge/Animation-GSAP_3.12-0A0D14?style=for-the-badge&logo=greensock&logoColor=white)](https://github.com/naishal988)
[![Edge: CDN Distribution](https://img.shields.io/badge/Edge-Media_CDN_%26_HLS_Streaming-0A0D14?style=for-the-badge&logo=cloudflare&logoColor=white)](https://github.com/naishal988)

---

## Executive Overview

**Architect:** Naishal Nadiya (`naishal988`)  
**Role:** System Architect & Cybersecurity Researcher  
**Core Disciplines:** High-Performance WebGL Environments, Zero-Trust Infrastructure, Cryptographic Protocol Engineering, Edge Computing  
**Public Repository:** `3d-portfolio-cdn`  
**Production Runtime:** [Live Spatial Workstation](https://naishal988.naishalpnadiya988.workers.dev/)

The **3D Architecture Studio** represents a foundational paradigm shift in technical portfolio presentation and executive developer spaces. Traditional portfolio sites rely on flat document structures or static grid layouts. This platform replaces the traditional terminal and flat portfolio with a fully spatial, hardware-integrated WebGL environment engineered for high-concurrency systems architecture, zero-trust security research, and tactile creative computing.

This repository serves as the public-facing **Content Delivery Network (CDN) and streaming distribution layer** for high-bitrate video, spatial textures, HLS assets, and media channels powering the in-engine hardware displays.

---

## Architectural Philosophy: Spatial Computing for Systems Engineering

Modern systems engineering is multifaceted, encompassing asynchronous event loops, distributed state machines, cryptographic verification, and physical hardware interfaces. Flat two-dimensional web applications fail to convey the tactile density and spatial harmony required to inspect enterprise systems.

### 1. Spatial Immersion as a Living Workspace
The 3D studio delivers a photorealistic, physically grounded architect office and outdoor penthouse terrace. Rather than scrolling through passive resume bullets, visitors interact within an authoritative physical volume:
- Inspect physical compute infrastructure, including rack-mounted hot-swap NVMe storage arrays with independent asynchronous diagnostic LEDs.
- Navigate architectural spaces from a first-person perspective with true kinematic walking, collision avoidance, and vertical gravity physics.
- Seamlessly transition from spatial mobility to dedicated workstation focus by engaging physical hardware.

### 2. Physical Hardware Integration & Micro-Frontend Iframe Bridging
The centerpiece of the studio is a custom-engineered 27-inch 5K Retina Workstation Display. The screen plane (`1.62m x 0.94m`, aspect ratio `1.7234`) hosts an edge-to-edge interactive micro-frontend web application via Three.js CSS3D matrix transformations:
- **Sub-Millimeter Screen Fitting:** Calibrated transform matrices stretch the interactive viewport to the exact inner bezels of the physical hardware casing, leaving zero black gap or artifact bleed.
- **Decoupled Persistence:** Display power state and rendering pipelines remain decoupled from player kinematic state. Visitors can boot the display, sit down to interact with live software, and stand up to walk across the studio while the terminal application continues running persistently in world space.

### 3. Diurnal Trajectory & Environmental Realism
The workspace incorporates a live temporal engine (`useLiveTime`) that synchronizes real-world solar positioning with in-engine ambient, directional, and celestial lighting. The horizon panorama displays a procedural skyline of 24 grounded skyscrapers, rooftop aviation safety beacons, and deep atmospheric distance fog.

---

## Interactive Controls & Mechanical Systems

The workstation bridges high-performance WebGL rendering with intuitive desktop gaming controls, providing responsive spatial mobility:

| Input Modality | Action Context | Mechanical Behavior |
| :--- | :--- | :--- |
| `[W] [A] [S] [D]` | Free-Roam Spatial Locomotion | Direct kinematic velocity with zero sliding drift; bounded by physical room walls, furniture colliders, and terrace railings. |
| `[SPACEBAR]` | Vertical Jump & Fall Physics | Single-cycle jump velocity clamped to gravitational acceleration (`g = 14.0 m/s^2`) with floor snap detection. |
| `[MOUSE]` | Pointer Lock Reticle (Yaw / Pitch) | Hardware-accelerated camera look with polar pitch boundaries (`-60 deg` to `+60 deg`) to preserve ergonomic perspective. |
| `[F]` | Contextual Mechanical Interaction | Seating at the ergonomic chair, toggling the 3-gang rocker switchboard, pulling the architect lamp chain, or sliding the balcony door. |
| `[O]` | Display Power Bus Toggle | Hardware power toggle cycling terminal system state between offline sleep and live interactive execution. |
| `[ESC]` | Cursor Decoupling | Releases pointer lock to facilitate interaction with embedded terminal iframes and desktop controls. |

---

## Performance Engineering & WebGL Optimization Matrix

To maintain a consistent, uncompromised **60 FPS / 120 FPS refresh rate** across mobile workstations, ultra-wide monitors, and high-DPI displays, the rendering pipeline adheres to strict memory and draw-call hygiene:

```
+-----------------------------------------------------------------------------------------+
|                                3D STUDIO WebGL PIPELINE                                 |
+-----------------------------------------------------------------------------------------+
       |
       +---> [ Canvas DPR Clamping: dpr={[1, 2]} ]
       |        |--> Prevents fillrate bottlenecks on 3x/4x Retina panels
       |
       +---> [ Zero-Allocation useFrame Loop ]
       |        |--> Scratch Vector Pools: _dir, _right, _up, _newPos, _away2
       |        |--> Deduplicated Raycast State: Dispatches updates only on target delta
       |        |--> Cached Collider References: Eliminates recursive scene graph traversal
       |
       +---> [ Rationalized Shadow Generation ]
       |        |--> Major Geometry Only: Bed, Desk, Chair, Lamp, AC Chassis
       |        |--> Insignificant Props Disabled: Railings, Foliage, Books, Cables, Keys
       |        |--> Depth Maps Optimized: Directional & SpotLight at [1024, 1024]
       |
       +---> [ Transmission & Framebuffer Elimination ]
       |        |--> Replaced multi-pass transmission buffers with high-performance PBR glass
       |
       +---> [ Light Consolidation & Instancing ]
                |--> Consolidated 11 point lights down to 3 balanced ambient fill pools
                |--> 60% Mechanical Keyboard rendered via single-draw-call InstancedMesh
```

---

## The Media CDN Architecture: Central Media Distribution Layer

This repository (`3d-portfolio-cdn`) acts as the high-throughput edge delivery network for the 3D portfolio ecosystem. Because high-fidelity spatial computing requires rapid delivery of video streams, audio buffers, and texture maps without bloating application bundles, all heavy binary media is decoupled from the main application codebase.

### Edge Distribution Capabilities
- **Geographic Edge Caching:** Assets are delivered via globally distributed edge nodes to ensure sub-50ms Time to First Byte (TTFB).
- **HLS / MPEG-DASH Adaptive Bitrate:** Video feeds are segmented into multi-bitrate streams (`1080p60`, `720p60`, `480p30`) to support variable bandwidth environments without stuttering.
- **Hardware Acceleration Headers:** Media responses carry optimized caching headers (`Cache-Control: public, max-age=31536000, immutable`), byte-range support, and permissive CORS policies for seamless WebGL texture binding.

---

## Upcoming Milestone: The In-Game Interactive TV Module (December 2026)

Slated for release in **December 2026**, the next major architectural expansion introduces a wall-mounted **Interactive TV & Broadcast Module** inside the studio.

```
+-----------------------------------------------------------------------------------------+
|                           IN-ENGINE TELEVISION BROADCAST BUS                            |
+-----------------------------------------------------------------------------------------+
                                             |
            +--------------------------------+-------------------------------+
            |                                |                               |
            v                                v                               v
   [ Channel 01: ARCH ]            [ Channel 02: SEC ]             [ Channel 03: LAB ]
  Systems Architecture            Zero-Trust Security             Creative WebGL &
  & Distributed Engines           Research & Exploit PoCs         Shader Engineering
```

### Technical Blueprint of the TV Module
1. **Dynamic Video Textures (`THREE.VideoTexture`):** Direct hardware-accelerated video decoding mapped directly to high-reflectance OLED glass geometry.
2. **CDN Channel Multiplexing:** Visitors will be able to cycle channels using physical in-game remote controls or wall switches, with live video feeds streamed directly from `3d-portfolio-cdn`.
3. **Dedicated Broadcast Lineup:**
   - **Channel 01 (Systems Architecture):** End-to-end architectural walkthroughs, distributed backend pipelines, and low-latency database clustering designs.
   - **Channel 02 (Cybersecurity & Zero-Trust):** Penetration testing case studies, binary analysis breakdowns, authorization protocols, and zero-trust perimeter implementations.
   - **Channel 03 (Creative Computing & Shaders):** Deep-dives into WebGL fragment shaders, raymarching techniques, and procedural environment generation.

---

## Technical Stack & Infrastructure Specifications

The 3D Architecture Studio and CDN layer leverage an enterprise-grade technical stack designed for reliability, rendering accuracy, and zero latency:

### 3D Runtime & Graphics Engine
- **Core Engine:** [Three.js](https://threejs.org/) (r168)
- **Component Layer:** [React Three Fiber](https://r3f.docs.pmnd.rs/) (v8.18) & [@react-three/drei](https://github.com/pmndrs/drei) (v9.122)
- **Procedural Geometry:** Three-stdlib `RoundedBoxGeometry`, high-precision PBR `MeshPhysicalMaterial`, parametric spline generation
- **Kinematic Controllers:** PointerLockControls with custom boundary friction collision resolvers

### Animation & Physics
- **Interpolation Engine:** [GreenSock Animation Platform (GSAP 3.12)](https://greensock.com/)
- **Micro-Interactions:** Elastic spring pull-chain tension mechanics, damped horizontal sliding door physics (`THREE.MathUtils.damp`)
- **Fluid Layout Transitions:** Framer Motion & Framer Motion 3D

### Application Core & Tooling
- **Build System:** [Vite 5](https://vitejs.dev/) with high-performance Rollup code splitting
- **Styling Architecture:** [Tailwind CSS 3.4](https://tailwindcss.com/) & PostCSS
- **Smooth Viewport Scrolling:** [Lenis Smooth Scroll](https://lenis.darkroom.engineering/)

### Edge Infrastructure & Hosting
- **Edge Runtime:** Cloudflare Workers & Cloudflare Pages
- **Asset CDN:** Public GitHub CDN Distribution (`3d-portfolio-cdn`) & global CDN caches
- **Audio Pipeline:** Web Audio API with spatial distance attenuation and stereo panning

---

## Security & Architectural Standards

As a Cybersecurity Researcher and System Architect, security and resource integrity are foundational across all deployments:
- **Strict Content Security Policy (CSP):** Isolated iframe execution context with explicit `allow` directives (`accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture`).
- **Sandboxed Execution:** Prevention of frame-busting, unauthorized DOM traversal, or cross-origin access between the parent Three.js canvas and child terminal micro-frontends.
- **Resource Attribution & Immutability:** Hash-verified script injection, zero external unvetted dependencies, and immutable CDN version tags.

---

## Author & Executive Contact

**Naishal Nadiya**  
*System Architect & Cybersecurity Researcher*

- **Live Workstation:** [naishal988.naishalpnadiya988.workers.dev](https://naishal988.naishalpnadiya988.workers.dev/)
- **GitHub:** [@naishal988](https://github.com/naishal988)
- **LinkedIn:** [linkedin.com/in/naishal988](https://www.linkedin.com/in/naishal988/)
- **Primary Focus:** Distributed Systems Architecture, Zero-Trust Infrastructure, Cryptographic Protocol Research, High-Performance WebGL Environments

---

*(c) 2026 Naishal Nadiya. All rights reserved. The source code of the 3D Architecture Studio remains proprietary and confidential. This repository serves exclusively as the public media CDN and technical specification layer.*
