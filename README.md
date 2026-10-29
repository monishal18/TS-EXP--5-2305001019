# EXPERIMENT 5: DEVELOP A POPULATION GROWTH MODEL
## NAME: MONISHA 
## REG NO : 2305001019

## Aim
To develop a simple mathematical model for population growth using Python and predict future population.

## Software Required
- Python 3
- Google Colab or Jupyter Notebook
- NumPy
- Matplotlib

##  Procedure
1. Import the required libraries.
2. Enter the population data.
3. Plot the actual population.
4. Create a linear growth model.
5. Calculate the predicted population.
6. Forecast population for future years.
7. Plot actual, predicted, and forecast values.

##  Program
```

import numpy as np
import matplotlib.pyplot as plt

# Population data
year = np.array([2020, 2021, 2022, 2023, 2024])

population = np.array([
    10000, 10500, 11000, 11600, 12000
])

# Convert year into time
t = np.array([0, 1, 2, 3, 4])

# Plot actual population
plt.plot(
    year, population,
    marker="o",
    label="Actual"
)

# Find the best-fit linear model
b, a = np.polyfit(t, population, 1)

# Calculate predicted population
predicted = a + b * t

print("Starting Population =", round(a, 2))
print("Growth per Year =", round(b, 2))

print("\nYear              Actual   Predicted")

for i in range(len(year)):
    print(
        year[i],
        population[i],
        round(predicted[i], 2)
    )

# Predict future population
future_year = np.array([2025, 2026, 2027])
future_t = np.array([5, 6, 7])

future_population = a + b * future_t

print("\nFuture Population")

for i in range(len(future_year)):
    print(
        future_year[i],
        round(future_population[i], 2)
    )

# Plot the model
plt.plot(
    year, predicted,
    marker="x",
    linestyle="--",
    label="Model"
)

# Plot the forecast
plt.plot(
    future_year, future_population,
    marker="s",
    linestyle=":",
    label="Forecast"
)

plt.title("Population Growth Model")
plt.xlabel("Year")
plt.ylabel("Population")
plt.legend()
plt.grid(True)
plt.show()
```

##  Expected Output
- Starting population and growth rate.
 <img width="416" height="75" alt="image" src="https://github.com/user-attachments/assets/34cc7f27-60bd-44c2-8852-0f2321190283" />

- Actual and predicted population values.
 <img width="532" height="168" alt="image" src="https://github.com/user-attachments/assets/b032d9ae-7211-4b27-bc21-3c8f3f14988c" />

- Future population forecasts for 2025, 2026, and 2027.
 <img width="335" height="102" alt="image" src="https://github.com/user-attachments/assets/879688d3-7c49-450e-a80d-f7d7a25d0546" />

- Graph showing actual, predicted, and forecast population.
 <img width="602" height="473" alt="image" src="https://github.com/user-attachments/assets/40073cfe-85a6-4a61-a630-5a0e8816fa84" />


##  Observation
The population shows an increasing trend over time. A linear model is fitted to the historical data to estimate population growth and forecast future population.

The model is represented by:

P = a + bt

Where:
- P = predicted population
- a = starting population
- b = growth per year
- t = time

##  Result
Thus, a simple population growth model was developed using Python. The model was used to estimate future population and visualize the actual, predicted, and forecast population trends.
