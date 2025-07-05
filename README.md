# capstone-project-iitg-

# 🚗 Dynamic Pricing for Urban Parking Lots

## 📚 Project Overview
This project builds a **real-time dynamic pricing system** for urban parking spaces using historical and live parking data.  
We develop **three pricing models** of increasing complexity to optimize parking utilization based on demand, congestion, and competitor pricing.

Real-time simulation is achieved using **Pathway’s streaming engine**, and the pricing results are visualized through **Bokeh dashboards.**

---

## 🚀 Tech Stack Used
- Python 3.10+
- Pandas - Data manipulation
- NumPy - Numerical operations
- Bokeh - Real-time visualization
- Pathway - Real-time streaming and simulation
- Google Colab - Model development environment
- Mermaid - Architecture diagram (GitHub compatible)

---

## 🏗️ Project Architecture

```mermaid
graph TD
    A[Dataset Streaming]
    B[Pathway Streaming Engine]
    C[Dynamic Pricing Models<br>- Model 1: Baseline Linear<br>- Model 2: Demand-Based<br>- Model 3: Competitive Adjustment]
    D[Real-Time Streaming Output]
    E[Bokeh Dashboard]

    A --> B
    B --> C
    C --> D
    D --> E

```


Workflow and Architecture Explained in Simple Terms

Step 1: Real-Time Data Streaming with Pathway**

We start by feeding the parking lot dataset into the system as if it's being received live in real-time.
To make this happen, we use **Pathway’s streaming engine** which helps us process the incoming data step-by-step in **small batches**.
This ensures the system can **simulate real-time updates** while keeping the time sequence correct.



Step 2: Real-Time Pricing Calculation**

As the live data flows in, the system instantly calculates the updated parking prices using **three different pricing models:

* Model 1 (Simple Linear Model):
  This model increases the price slowly as the parking lot fills up. It only looks at how full the parking lot is.

* Model 2 (Demand-Based Pricing):
  This model uses more factors to calculate the price. It looks at:

  * How full the parking lot is (occupancy)
  * How many vehicles are waiting to enter (queue length)
  * The nearby traffic condition (low, medium, high)
  * Whether it’s a special day (like an event or holiday)
  * What type of vehicle is entering (cars, bikes, or trucks)

* Model 3 (Competitive Pricing):
  This model checks if nearby parking lots are cheaper or more expensive.
  If competitors are cheaper, this model slightly lowers the price to stay attractive.
  If competitors are more expensive, it raises the price a little to maximize profit.



Step 3: Streaming the Output

After the system calculates the new prices, it **writes them to a CSV file continuously.**
This file acts as a **live feed** that the dashboard will monitor and display.



Step 4: Real-Time Visualization

We use a **Bokeh dashboard** that keeps an eye on the live CSV file.
It refreshes automatically to show the most recent prices for each parking lot.

The dashboard helps users to:

* Watch the parking prices changing live.
* Compare how each of the three models is behaving side-by-side.


Summary:

* The system continuously takes live data, calculates new prices, streams the results, and instantly visualizes them.
* It gives users **real-time insights** into how parking prices change throughout the day under different conditions.
