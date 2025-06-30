# Self-Organizing Map for Zoo-Animal Clustering

## 1. Introduction
   This project applies a Kohonen Self-Organizing Map (SOM) to a zoo-animal dataset of 98 species, each described by sixteen binary traits and a rescaled leg-count feature. By training a two-dimensional lattice with exponentially decaying learning-rate and neighborhood functions, the SOM uncovers topology-preserving clusters that correspond to meaningful biological categories (mammals, birds, aquatic species, etc.) .

## 2. Project Structure
The implementation is organized into the following stages:

* **Library Imports:** Load Pandas, NumPy, Matplotlib and scikit-learn for data handling, analysis and visualization.
* **Data Loading & Exploratory Analysis:** Ingest the CSV dataset; compute descriptive statistics; generate histograms and a correlation heatmap to inspect feature distributions and relationships .
* **Data Preprocessing:** Apply Min–Max normalization to all binary attributes and the leg-count feature (originally {0,2,4,5,6,8}), ensuring uniform scale for Euclidean-distance learning .
* **SOM Implementation & Hyperparameter Tuning:** Define weight initialization, Best-Matching Unit selection, and Gaussian neighborhood function. Sweep key hyperparameters—map size (15×15), initial learning rate (α₀ = 0.2), initial neighborhood radius (σ₀ = 12) and training length (300 000 epochs)—to identify the optimal configuration .
* **Training & Monitoring:** Train the SOM over the specified epochs, logging quantization error and topographic error at regular intervals to evaluate convergence and topological fidelity .
* **Post-Training Analysis:** Cluster the 225 neuron weight vectors via K-Means (k = 20) to delineate coherent regions. Visualize the resulting cluster map, U-Matrix, activation frequency heatmap and per-cluster sample assignments for both training and held-out specimens .

## 3. How to Run the Project

* **Environment:** Python 3.8+ in a Jupyter Notebook or Google Colab.
* **Dependencies:** `pandas`, `numpy`, `matplotlib`, `scikit-learn`.
* **Execution:**

  1. Clone the repository and install dependencies via `pip install -r requirements.txt` or just download the Notebook `SelfOrganizingMap.ipynb`.
  2. Upload the datasets `zoo_animals_train.csv` and `zoo_animals_test.csv`.
  3. Launch `SelfOrganizingMap.ipynb` and run all cells sequentially.

Feel free to change the hyperparameters in order to find the best SOM!

## 4. Test Specimen Assignment (Extension)
   To project new animal records onto the trained SOM, you can add more on the `data/zoo_animals_test.csv`.

## 5. Dataset Availability

* **Train Set:** Provided as `data/zoo_animals_train.csv` (98 specimens × 17 features).
* **Test Set:** Included in `data/zoo_animals_test.csv` (3 specimens) for out-of-sample validation.

Feel free to include this description in your GitHub README to succinctly convey the goals, structure and usage of your SOM project!
