# Social Network Analysis of Netflix Collaborations 🎬

*Analyzing Collaboration Patterns Between Directors & Actors Across Movie Genres*  
*A Master's Course Project in Social Network Analysis (SNA)*  

---

## 📌 Overview  
This project explores collaboration networks in the U.S. film industry using Netflix data. By applying **Social Network Analysis (SNA)**, we uncover how directors and actors collaborate within and across genres, identify key influencers, and track how these networks evolve over time. Key questions answered:  
- **Homophily**: Do creators prefer working within the same genre?  
- **Centrality**: Who are the most influential directors/actors in each genre?  
- **Dynamics**: How do collaborations change over time?  
- **Communities**: Do genres form distinct collaboration clusters?  

---

## 📂 Dataset  
- **Source**: [Netflix Movies and TV Shows (Kaggle)](https://www.kaggle.com/datasets/shivamb/netflix-shows)  
- **Scope**: Focused on **2,684 U.S.-produced movies** (filtered from the original dataset).  
- **Key Metadata**:  
  - Directors, actors, genres, release year.  
  - Genres analyzed: *Drama, Comedy, Documentary, Horror, Children & Family, Action & Adventure*.  

---

## 🛠️ Methodology  

### 1. **Graph Construction**  
- **Nodes**: Directors (`_d` suffix) and Actors (`_a` suffix).  
- **Edges**: Created if two individuals collaborated on the same movie.  
- **Genre-Specific Networks**: Separate graphs built for each genre.  

### 2. **Key Metrics**  
| Metric | Definition | Relevance |  
|--------|------------|-----------|  
| **Degree Centrality** | Number of connections a node has. | Identifies highly collaborative individuals. |  
| **Betweenness Centrality** | How often a node acts as a bridge between others. | Highlights "connectors" in the network. |  
| **Closeness Centrality** | Average distance from a node to all others. | Measures how quickly someone can reach others. |  
| **Clustering Coefficient** | Likelihood that two collaborators of a node are also connected. | Indicates tight-knit groups (e.g., frequent repeat collaborations). |  
| **Preferential Attachment** | Probability of new connections forming with highly connected nodes ("rich get richer"). | Explains growth patterns in networks. |  

### 3. **Temporal Analysis**  
- **Cumulative Networks**: Built yearly from 1990–2021 to track evolution.  
- Metrics tracked over time: *Average degree, distance, clustering, preferential attachment*.  

### 4. **Community Detection**  
- **Algorithms**: Multi-level and Leiden (resolution-based).  
- **Modularity**: Measures how well a network is divided into communities.  

---

## 🔍 Key Findings  

### 1. **Genre-Specific Networks**  
- **Horror Films**: Tight-knit communities (high clustering). Directors act as central hubs.  
- **Documentaries**: Fewer connections per person but many small clusters.  
- **Comedies**: Actors have the highest closeness centrality (well-connected within the genre).  

### 2. **Central Figures**  
- **Directors**: *Martin Scorsese* (Drama), *Scott Stewart* (Horror).  
- **Actors**: *Samuel L. Jackson* (Action), *James Franco* (Drama).  

### 3. **Temporal Trends**  
- **Actors in Dramas/Comedies**: Exponential growth in collaborations post-2000.  
- **Documentaries**: Surge in director involvement (2015–2020).  
- **Shrinking Distances**: Actors became more interconnected over time.  

### 4. **Communities Reflect Genres**  
- *Comedy* and *Children & Family* actors form distinct clusters.  
- Mixed-genre communities (e.g., *Drama + Action*) also exist due to multi-genre collaborations.  

---

## 💻 Code & Reproducibility  

### Dependencies  
- Python 3.8+  
- Libraries: `pandas`, `networkx`, `matplotlib`, `seaborn`.  

### How to Run  
1. **Data Preparation**:  
   ```python  
   df = pd.read_csv('https://raw.githubusercontent.com/aphdinh/socialnetwork/main/netflix_titles.csv')  
   # Filter U.S. movies and preprocess (see notebook for details)  

## Build Graphs:
```python  
G = create_graph_from_df(usa)  # Custom function to generate collaboration networks  
```

## Analyze Metrics:
```python  
compute_average_degree(G, "actor", "Comedy")  # Example: Avg. degree for Comedy actors  
```
## Visualize Results:

- Pre-built functions for plotting trends (e.g., plot_metric()).

## 📈 Key Takeaways for Practitioners
- Network Insights: Genre-specific collaboration patterns can inform talent recruitment or partnership strategies.
- Temporal Dynamics: Recent genres (e.g., Horror) show denser networks, indicating active communities.
- Toolkit: Code provides reusable functions for SNA on collaboration datasets.

## 📚 References
- Concepts: Preferential Attachment (Barabási–Albert Model), Centrality Measures.
- Data Source: Kaggle Netflix Dataset.
