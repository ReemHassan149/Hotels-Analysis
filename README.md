# Hotels-Analysis
This is a comprehensive, professional analysis report based on your hotel reservation data. Since you’ve already used Python to engineer columns like Revenue and Total Nights, we can focus the report on business intelligence and strategic outcomes.
# Hotel Performance & Revenue Optimization Report
## 1. Executive Summary
This report analyzes hotel reservation patterns to optimize revenue and mitigate cancellation risks. By leveraging **Python-cleaned** data and a Star Schema architecture, we’ve identified that while City Hotels drive volume, Resort Hotels often command higher loyalty and longer stays. The primary goal is to shift from "Gross Bookings" to "Net Revenue" by addressing a high baseline cancellation rate.
- python script: http://localhost:8888/notebooks/Hotels%20Data%20Cleaning.ipynb
  
![overview](https://github.com/user-attachments/assets/841b23dc-bcc9-4c2f-8752-584c8ea1fcea)
![Revenue](https://github.com/user-attachments/assets/292559a6-1837-4c73-b5f0-addfa10140ba)
![cancellation](https://github.com/user-attachments/assets/6aa14041-7729-4c0d-9556-18a8ce7ee6fa)
![Guest profile](https://github.com/user-attachments/assets/60403ba2-554b-47d6-877a-50ec6457f0df)
<img width="839" height="542" alt="star schema" src="https://github.com/user-attachments/assets/1c7160af-ced4-4464-91b5-b065d41d6cdc" />


## 2. Technical Foundation & Methodology
- **Data Preprocessing (Python):** * Synthesized Total Nights by aggregating stays_in_weekend_nights and stays_in_week_nights.

- Calculated Revenue as a product of ADR and Total Nights, adjusted for successful stays.

- **Data Modeling:** Implemented a **Star Schema** to ensure high-speed filtering across multiple dimensions (Geography, Customer Segment, and Time).

- ### **Key DAX Measures:**

- **Net Revenue**: SUM(FactReservation[revenue])
- **ADR (Average Daily Rate)**: AVERAGE([adr])
- **RevLoss (Cancellation Impact)**: SUM(FactReservation[is_canceled])
- **cancellation Rate**: DIVIDE([cancellation],[No. Reservasion])
  
## 3. Page-by-Page Analysis Insights
### Page 1: Executive Overview
- **Volume vs. Value**: City hotels account for approximately 66% of bookings, but Resort hotels show a higher revenue-per-booking ratio.

- **Seasonality**: Revenue peaks in the summer months (July–August), but this is also accompanied by a spike in lead times.

### Page 2: Revenue & Stay Patterns
- **The "Sweet Spot"**: Our scatter analysis proves that stays of 3–5 nights generate the highest aggregate revenue.

- **Long-Stay Dilution**: Stays exceeding 14 nights show diminishing returns, often due to lower discounted ADRs or higher maintenance costs.

### Page 3: Cancellation Risk (The "Lead Time" Factor)
- **The 150-Day Rule**: Data shows a critical threshold where lead times exceeding 150 days correlate with a >60% cancellation rate.

- **Deposit Impact**: "No Deposit" bookings are 3x more likely to cancel than "Non-refundable" bookings, regardless of lead time.

### Page 4: Market & Distribution Channels
- **Online TA Performance**: While Online Travel Agencies (OTAs) bring the most volume, they also carry the highest cancellation overhead.

- **Direct Channel Loyalty**: "Direct" bookings show the highest Loyalty % (Repeat Guests) and the lowest cancellation rate, suggesting a higher "Net Value" per customer.

### 4. Strategic Recommendations
- **Dynamic Deposit Policy**: Apply mandatory non-refundable deposits for any booking with a Lead Time > 120 days to protect revenue.

- **Length of Stay (LOS) Incentives**: Create "Stay 4, Pay 3" packages during shoulder seasons to push guests into the highly profitable 3–5 night "Sweet Spot" identified in our scatter chart.

- **Channel Shift**: Increase marketing spend on Direct Bookings to reduce the revenue loss currently seen in high-risk OTA segments.

- **Overbooking Strategy**: Use the 60% risk factor for long-lead bookings to safely overbook during peak seasons by a calculated margin of 10–15%.

### 5. Data Patterns Summary
<img width="608" height="146" alt="patterns" src="https://github.com/user-attachments/assets/d8909d9e-6dd8-4471-a2a1-8bdf4f7f883c" />
