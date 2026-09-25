## Projects

### CASCADE 

I worked on CASCADE, a port disruption dashboard that helps operators respond when a ship arrives late. It identifies containers at risk of missing their next ship, forecasts storage needs, and compares recovery plans with estimated costs.

**My integration work connected AISStream and Mapbox to the dashboard.** AISStream supplies live AIS (Automatic Identification System) vessel positions through the FastAPI backend. Mapbox provides the interactive map where operators can see ship movements and understand where a disruption is happening. This connects the recovery analysis to a view of the real shipping network.

CASCADE also uses specialist AI agents to explain options, while a Python calculation engine checks constraints and produces consistent estimates. Operators review and approve a plan before the system creates simulated work orders.

**Technologies:** Python, FastAPI, React, TypeScript
**Project:** [View CASCADE on GitHub](https://github.com/edward3423/hackathon_psa2026)


### AI-Generated Image Detection 

I worked on an AIGC (AI-generated content) detector that distinguishes real photographs from AI-generated images. The challenge was making detection work after images are shared online, where compression, cropping, resizing, blur, and noise can remove clues the model relies on.

The project uses a SigLIP Vision Transformer, an image model with about 93 million parameters. I worked on a training pipeline that shows the model both a clean image and an altered version of it, then tests whether it can classify both correctly. We compared this approach with standard training instead of assuming the more complex approach would perform better. We also kept evaluation images separate from training images and tested images made by generators the model had not trained on.

The selected model scored **0.9624 ROC-AUC** on a 4,500-image validation set. ROC-AUC measures how well a model ranks AI-generated images above real ones across different decision thresholds; 1.0 is perfect. We also measured performance under different image alterations and examined cases where genuine photos were incorrectly flagged. The project includes batch image scoring and an interactive demo that shows a calibrated confidence score. That score helps with review, but does not prove where an image came from.

**Technologies:** Python, PyTorch, SigLIP, Vision Transformers, Gradio  
