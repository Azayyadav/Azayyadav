- 👋 Hi, I’m @Azayyadav
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

# Project Name

### Steps to include the radar chart image:
1. Save your radar chart image as a PNG file (e.g., `radar-chart.png`).
2. Place the image in an appropriate directory within your repository (e.g., in a folder named `images`).
3. Update the `![Radar Chart](path/to/your/radar-chart.png)` line in the README to point to the correct path of your radar chart image.

### Optional: Generating the Radar Chart with Python
If you need to generate the radar chart programmatically, here's a complete Python script example:

```python
import matplotlib.pyplot as plt
import numpy as np

# Data
labels = ['Commit', 'Issue', 'PullReq', 'Review', 'Repo']
stats = [1000, 100, 50, 20, 10]  # Example data points for each category

# Number of variables
num_vars = len(labels)

# Compute angle of each axis
angles = np.linspace(0, 2 * np.pi, num_vars, endpoint=False).tolist()

# Complete the loop
stats += stats[:1]
angles += angles[:1]

# Plot
fig, ax = plt.subplots(figsize=(6, 6), subplot_kw=dict(polar=True))
ax.fill(angles, stats, color='green', alpha=0.25)
ax.plot(angles, stats, color='green', linewidth=2)

# Labels
ax.set_yticklabels(['10', '100', '1k', '10k'], color='grey', size=10)
ax.set_xticks(angles[:-1])
ax.set_xticklabels(labels)

plt.savefig('images/radar-chart.png')
plt.show()

