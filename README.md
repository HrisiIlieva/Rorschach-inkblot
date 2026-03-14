# Mathematical Analysis and Generation of Rorschach Inkblots
This project explores the intersection of geometry, symmetry theory, fractals, and probability within the context of Hermann Rorschach’s tests. It provides a formal mathematical framework to explain how these shapes stimulate human perception and includes a Python-based simulation to generate synthetic inkblots. 
## 🧠 Theoretical Framework
### 1. Geometric & Symmetry Model
Each inkblot is modeled as a subset of the plane $B \subset \mathbb{R}^2$. The project analyzes the axial symmetry created by folding the paper, where 

$$(x,y) \in B \implies (-x,y) \in B$$ 

- Group Theory: The minimal symmetry group is the cyclic group $G \cong C_2$ , consisting of the identity $e$ and reflection $r$, where $r^2=e$ .
- Bilateral Symmetry: All standard 10 cards are approximately bilaterally symmetric, which is a key property of the test.
- Visual Perception: This symmetry triggers the brain to automatically search for bilateral structures, interpreting shapes as animals or faces.
### 2. Fractal Geometry
The contours of real inkblots are not smooth and are best described by their fractal dimension $D$. 
- Complexity Range: Research indicates that inkblots have fractal properties with typical values falling between

$$1.1 < D < 1.3$$

or up to $1.6$
- Calculation: The dimension is determined by 

$$D =\lim_{(\epsilon \to 0)} \frac{\log N(\epsilon)}{\log(1/\epsilon)}$$

where $N(\epsilon)$ is the number of squares of size $\epsilon$ needed to cover the blot.
- Cognitive Impact: This multi-scale structure makes the figure more complex than a line but less than a filled area, stimulating pattern recognition.
### 3. Probabilistic Perception & Topology
- Bayesian Perception: Model the probability $P(s_i \mid B)$ of an observer seeing a specific object $s_i$ based on factors like symmetry, contrast, and experience.
- Visual Attention: Eye-tracking experiments show that gaze fixations are symmetrically distributed around the central axis, with a correlation of $R^2 \approx 0.93$ .
- Topological Invariants: Using the Euler characteristic

$$\chi = k - h$$

the model analyzes the number of connected components $k$ and holes $h$ .
- Information Entropy: Visual complexity is measured via Shannon entropy

$$H = -\sum p_i \log p_i$$

Design aims for moderate entropy to avoid being too obvious or looking like noise.
## 💻 Simulation (Python)
The project implements a Python simulation to generate inkblots through three core mathematical stages: 
1.	Random Field Generation: Simulating initial ink density using a normal distribution

$$f(x,y) \sim \mathcal{N}(0,1)$$

2.	Diffusion Modeling: Applying the diffusion equation

$$\frac{\partial u}{\partial t} = D \nabla^2$$

to simulate the spread of ink across paper.
3.	Fractal Enhancement: Adding fractal noise $F(x,y)$ to create organic, multi-scale boundaries:

$$u_{final} = u_{diffusion} + \alpha \cdot F(x,y)$$

4.	Thresholding & Symmetry: Converting the field into a binary image via a threshold and applying a mirror transformation.
## Requirements
To run the simulations, you will need:
- numpy
- matplotlib
- scipy
## 🔬 Conclusion
The mathematical combination of bilateral symmetry, moderate fractal dimension, and stochastic noise creates an ideal stimulus for pareidolia—the brain's tendency to recognize familiar patterns in random stimuli. 


