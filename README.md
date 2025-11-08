# R and D_AI_Assignment
Parameter Estimation of a Parametric Curve  
The goal of this project was to estimate the unknown parameters θ, M, and X in a specific parametric curve equation. The curve is defined as  
x = t cos(θ) − e^M |t| sin(0.3t) sin(θ) + X,  
y = 42 + t sin(θ) + e^M |t| sin(0.3t) cos(θ)  
where t lies between 6 and 60. The parameters are limited to the ranges 0° < θ < 50°, −0.05 < M < 0.05, and 0 < X < 100.  
The provided dataset included only the x and y coordinates of the curve. Since the t values were missing, they were reconstructed as evenly spaced values between 6 and 60, assuming the points were sampled uniformly along the curve. The mathematical model was built in Python using NumPy and SciPy libraries. We performed optimization by minimizing the L1 loss function, which measures the total absolute difference between the observed and predicted values. The optimization used the L-BFGS-B algorithm, which effectively applies parameter constraints. We created visualizations using Matplotlib to check that the predicted curve closely matched the provided data points.  

After running the optimization, the estimated parameters were θ = 28.119469°, M = 0.021383, and X = 54.899953. These values fit comfortably within the specified ranges. The model reached a total L₁ distance of 37,865.0955 and an average L₁ error per sample of 25.2434. This indicates a strong fit between the model and the observed data. The final parametric equation of the curve can be expressed as  

(t cos(28.119469°) − e^0.021383 |t| sin(0.3t) sin(28.119469°) + 54.899953,  
42 + t sin(28.119469°) + e^0.021383 |t| sin(0.3t) cos(28.119469°))  

The implementation and results are in the Colab notebook named code.ipynb, along with the input file xy_data.csv, the predicted output file xy_predictions.csv, and the visualization image xy_fit_scatter.png. The code follows a reproducible structure so anyone can easily verify the process by running the notebook in Google Colab. The results show that the optimization method accurately estimated the parameters and that the fitted curve correctly represents the provided data points.  

This assignment illustrates the practical application of numerical optimization in curve fitting and parametric modeling within AI. It shows how exponential and sinusoidal components can be combined to create complex mathematical curves that can be fitted to data through computational methods. The work aligns with earlier research in estimating exponential signals, particularly as discussed by Stoica, Li, and He (2013) in their paper "Parameter Estimation of Exponential Signals: A System Identification Approach," published in Signal Processing, Volume 93, Issue 6, pages 1614–1624. The DOI for this reference is 10.1016/j.sigpro.2013.03.015.  

In conclusion, the task was successfully completed with the estimation of all three unknown parameters, achieving a smooth and accurate curve fit within the given limits. The resulting model shows the effectiveness of computational methods for parameter estimation in AI-driven mathematical modeling.
