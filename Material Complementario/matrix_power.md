import numpy as np
import matplotlib.pyplot as plt
import matplotlib.gridspec as gridspec

P = np.array([[0.1, 0.9],
              [0.8, 0.2]])

N = 50

powers = [None, P.copy()]
M = P.copy()
for n in range(2, N + 1):
    M = M @ P
    powers.append(M.copy())

print(f"P^1 =\n{P}\n")
for n in range(2, N + 1):
    print(f"P^{n} =\n{np.round(powers[n], 6)}\n")

# --- Plot ---
labels = ["P[0][0]", "P[0][1]", "P[1][0]", "P[1][1]"]
colors = ["#e17055", "#74b9ff", "#55efc4", "#fdcb6e"]
series = [
    [powers[n][0][0] for n in range(1, N+1)],
    [powers[n][0][1] for n in range(1, N+1)],
    [powers[n][1][0] for n in range(1, N+1)],
    [powers[n][1][1] for n in range(1, N+1)],
]

fig = plt.figure(figsize=(12, 5), facecolor="#1a1a2e")
gs = gridspec.GridSpec(1, 2, width_ratios=[2, 1])

# Main chart
ax = fig.add_subplot(gs[0])
ax.set_facecolor("#16213e")
ns = list(range(1, N + 1))
for i, s in enumerate(series):
    ax.plot(ns, s, label=labels[i], color=colors[i], linewidth=2)
ax.set_xlabel("n (potencia)", color="#aaa")
ax.set_ylabel("valor", color="#aaa")
ax.set_title("P^n — evolución de celdas", color="#a8d8ea")
ax.legend(facecolor="#1a1a2e", labelcolor="white")
ax.tick_params(colors="#aaa")
for spine in ax.spines.values():
    spine.set_edgecolor("#2d3561")
ax.grid(color="#2d3561", linewidth=0.5)

# Zoom: first 15 steps
ax2 = fig.add_subplot(gs[1])
ax2.set_facecolor("#16213e")
zoom_n = 15
for i, s in enumerate(series):
    ax2.plot(ns[:zoom_n], s[:zoom_n], label=labels[i], color=colors[i], linewidth=2, marker='o', markersize=4)
ax2.set_xlabel("n (zoom: 1–15)", color="#aaa")
ax2.set_title("Zoom primeros pasos", color="#a8d8ea")
ax2.tick_params(colors="#aaa")
for spine in ax2.spines.values():
    spine.set_edgecolor("#2d3561")
ax2.grid(color="#2d3561", linewidth=0.5)

plt.tight_layout(pad=2)
plt.show()
