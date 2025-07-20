# GalaxyUAS Website Development Roadmap

This roadmap outlines a plan for integrating interactive 3D content into **GalaxyUAS**'s website (<https://galaxyuas.com>). Using **three.js** alongside **Onshape** CAD models, we can showcase our capabilities, the *constellation concept*, and the *AIRSHIP^2* initiative in a dynamic way.

## Overview
The goal is to bring existing Onshape designs to the web, enabling visitors to explore our drone technology, constellation operations, and the AIRSHIP^2 program directly in the browser. Assets will be exported to `glTF` and displayed through three.js to provide smooth, interactive models. A modern build pipeline ensures assets remain optimized as we iterate on new content.

## Onshape Export Integration
Automate the flow from Onshape CAD to the web:
1. Use a webhook or scheduled check to detect updates in Onshape documents.
2. Trigger a Node.js script that calls Onshape's `/export` endpoint to fetch the latest assembly as `glTF`.
3. Compress the output with DRACO/Basis and push to an `assets/models` directory.
4. Commit the exported files so each deployment includes the newest CAD revisions.

## 1. Goals
- Embed interactive 3D models derived from Onshape designs.
- Illustrate the constellation concept with animated scenes.
- Highlight the AIRSHIP^2 initiative using visualizations.
- Provide an engaging user experience while keeping the site performant.

## 2. Tools & Technologies
- **three.js** – JavaScript library for creating and displaying animated 3D graphics.
- **Onshape** – CAD modeling platform; export models to `glTF` or `OBJ` for web use.
- **WebGL/WebGPU** – Renderers supported by three.js.
- **TypeScript or ES6** – For structured JavaScript development.
- **Bundler** – e.g., `webpack` or `Vite` for building optimized assets.

## 3. Phase 1 – Setup
1. Create a dedicated repository or branch for the website enhancements.
2. Integrate a modern build pipeline (webpack or Vite) with three.js as a dependency.
3. Choose a framework (React, Next.js, or plain TypeScript) for new 3D pages.
4. Establish a basic page with a canvas for 3D rendering and a placeholder model.
5. Load a sample Onshape model exported as `glTF` to verify the pipeline.
6. Store Onshape API tokens securely (e.g., environment variables) for automated exports.

## 4. Phase 2 – Asset Pipeline
1. Define a standard export workflow from Onshape:
   - Export assemblies directly as `glTF`, or as STEP files converted to `glTF` using `gltf-pipeline`.
   - Organize 3D assets in a version-controlled folder (e.g., `/assets/models`).
2. Automate model optimization if necessary (using tools like `gltf-pipeline`).
   - Apply DRACO and Basis compression to reduce file sizes.
3. Document the asset pipeline so team members can add or update models easily.
4. Validate each exported model in a test scene to confirm orientation and textures.

## 5. Phase 3 – Website 3D Integration
1. Build reusable viewer components using three.js to display models on pages.
2. Implement camera controls (orbit/first-person) for user interaction.
3. Add UI elements for switching between different models or scenes.
4. Ensure responsive design so the 3D content scales across devices.
5. Optimize for performance: lazy load large assets, use compressed textures, and limit polygon counts.

## 6. Phase 4 – Constellation Concept
1. Create a dedicated scene demonstrating the constellation concept:
   - Use multiple 3D assets (drones, satellites, support craft) arranged in orbital patterns.
   - Animate formations to show fleet coordination and mission roles.
2. Allow user interaction to explore individual elements or highlight formations.
3. Include orbital trails and labels to convey altitude, velocity, and mission roles.
4. Add textual overlays or tooltips describing capabilities and benefits.

## 7. Phase 5 – AIRSHIP^2 Initiative
1. Design a 3D model or scene that represents the AIRSHIP^2 concept in action.
2. Animate launch, flight, and landing sequences to illustrate the full workflow.
3. Provide informational hotspots where users can click to learn more about each stage and technical highlights.
4. Tie the scene events to scripted sequences such as preflight checks or payload installation.

## 8. Phase 6 – Additional Enhancements
1. Integrate analytics to measure user engagement with 3D content.
2. Add progressive loading indicators so users know when a model is ready.
3. Consider implementing AR (Augmented Reality) views using WebXR to showcase assets in real-world scale.
4. Maintain accessibility: offer alt text, keyboard navigation, and fallback imagery for users unable to load WebGL content.

## 9. Phase 7 – Deployment & Maintenance
1. Deploy updates to a staging environment before pushing to production.
2. Monitor performance metrics to ensure smooth rendering across devices.
3. Schedule regular asset reviews to incorporate new Onshape models and retire outdated content.
4. Automate model exports using Onshape webhooks so deployments always include the latest revisions.
5. Add automated tests that load models and verify the viewer functions across updates.

## 10. Sample Timeline (Adjust as needed)
| Month | Milestone |
|-------|-----------|
| 1     | Set up build pipeline and load first Onshape model |
| 2     | Implement reusable 3D viewer components |
| 3     | Launch constellation concept demo |
| 4     | Add AIRSHIP^2 interactive scene |
| 5     | Optimize performance and gather feedback |
| 6     | Deploy final version and iterate on new content |

## 11. Summary
By leveraging three.js and Onshape exports, the GalaxyUAS website can present its 3D assets and initiatives in a compelling manner. This roadmap provides a phased approach that covers setup, asset management, interactive showcases, and ongoing improvements. Following these steps will help communicate GalaxyUAS's capabilities with engaging, dynamic visuals.

_End of roadmap._
