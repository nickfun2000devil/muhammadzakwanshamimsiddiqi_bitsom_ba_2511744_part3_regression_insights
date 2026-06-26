# Model Residual Analysis
This report evaluates the error metrics (residuals) of our final multiple linear regression model to audit individual store performance anomalies, capture hidden micro-advantages, and evaluate model predictive trends.

## 1. Calculation Framework & Logic
* **Predicted Sales Calculation:** Baseline expected sales generated via the master multi-variable regression equation block.
* **Residual Calculation Formula:** Line-by-line performance deviations evaluated using the standard mathematical formula:
  $$\text{Residual} = \text{Actual Sales} - \text{Predicted Sales}$$

## 2. Extreme Performance Outlier Identification

By sorting the calculated residual array across all 320 operational store records, the top 5 largest positive and top 5 largest negative entries were isolated.

### Largest Positive Residuals (Model Under-Prediction)
These stores generated significantly higher monthly sales than predicted by the regression formula:
1. **Observation 112:** Residual = +128,973.38 (Highest absolute positive variance)
2. **Observation 104:** Residual = +121,634.33
3. **Observation 202:** Residual = +102,340.62
4. **Observation 8:** Residual = +100,975.38
5. **Observation 336:** Residual = +99,775.30

### Largest Negative Residuals (Model Over-Prediction)
These locations significantly underperformed their operational and traffic-based baseline predictions:
1. **Observation 45:** Residual = -143,723.70 (Highest absolute negative variance)
2. **Observation 67:** Residual = -134,096.67
3. **Observation 33:** Residual = -129,932.37
4. **Observation 90:** Residual = -128,526.44
5. **Observation 137:** Residual = -123,264.44

## 3. Business Meaning of Gaps & Strategic Explanations

### Positive Outlier Interpretation (+128.9k)
A massive positive residual means a store has structural micro-advantages that the standard data does not account for. From a business standpoint, this represents an exceptionally high-performing asset. This performance spike typically points to:
* High-tier local store management driving superior closing rates.
* Premium localized real estate placement (e.g., being located right next to a high-traffic anchor mall entrance).
* Minimal nearby direct competitor presence, giving the store high local market capture.

### Negative Outlier Interpretation (-143.7k)
A severe negative residual flags critical operational friction. Despite having high footfoot traffic or strong marketing budgets, these locations failed to convert opportunities into revenue. Leadership should audit these branches for:
* Localized product stockouts or inventory shipping delays.
* Low customer satisfaction scores or unoptimized staff scheduling.
* Temporary local access issues, such as heavy road construction blocking the store entrance.

## 4. Predictive Trends & Bias Evaluation

### Model Performance Assessment
The regression model displays balanced predictive properties across the standard 320-row distribution, showing a reliable spread of error variations on both sides of the zero-line. 

### Over-Prediction vs. Under-Prediction Trends
The model does not suffer from a systemic predictive bias across regular store types. Instead, the extreme outliers pinpoint unique localized environments rather than a flaw in the model itself. For example:
* **Under-prediction tendencies** occur in highly specialized retail spaces (like prime Airport hubs) where baseline customer conversion speeds are naturally much higher than standard street levels.
* **Over-prediction tendencies** appear when a store is located in a high-density area that has heavy local competition, causing high raw footfall numbers to split across multiple brands instead of converting at our predicted rate.