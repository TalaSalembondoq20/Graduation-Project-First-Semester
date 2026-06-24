# 12 Appendices

12. <span id="_Toc229301152" class="anchor"></span>Appendices

    1.  <span id="_Toc229301153" class="anchor"></span>**Appendix A:
        Source of Project Data**

The principal data on operation and economics in the context of the
current investigation have been collected from the **Bio Fuel Company**.
This organization has been chosen as a reference point for the
development of small-scale waste tyre pyrolysis technology.

This organization supplied relevant data for the establishment of
capacity, process flow diagram, equipment, assumptions on operations,
and parameters concerning economic aspects of the investigated system
**as shown in the figure below**. Such data included information on
capacity for daily processing of tyres, average weight of one tyre,
batch capacity of reactors, preprocessing of tyres, man-hours required
for one batch, operating costs, assumptions on capital investments, and
product outputs.

In order to conduct a preliminary analysis, all data gathered from the
Bio Fuel Company have been supplemented by additional literature
assumptions when necessary.

<img src="../media/image26.png"
style="width:6.4292in;height:8.31191in" />

2.  <span id="_Toc229301154" class="anchor"></span>**Appendix B:
    Production and Process Data**

The production data used in the simulation model were based on the
practical information provided by **Bio Fuel Company**. These data were
used to define the material flow and production scale of the proposed
plant.

| Parameter                     | Value                |
|-------------------------------|----------------------|
| Average tyre weight           | 10 kg                |
| Daily tyre input              | 1000–1500 tyres/day  |
| Daily production capacity     | 10–15 tons/day       |
| Pieces per tyre after cutting | 4 pieces             |
| Total pieces per day          | 4000–6000 pieces/day |
| Reactor batch capacity        | 10 tons/batch        |
| Required tyres per batch      | 1000 tyres           |
| Required pieces per batch     | 4000 pieces          |
| Reactor cycle time            | 18–23 hours/batch    |

These values were used to configure the discrete-event simulation model
and to represent the interaction between continuous preprocessing stages
and batch-based pyrolysis operation.

3.  <span id="_Toc229301155" class="anchor"></span>**Appendix C:
    Simulation Input Parameters**

The simulation model was developed using Simio software. The processing
times and capacities were assigned based on the system structure and
production assumptions obtained from Bio Fuel Company.

| Process Stage     | Processing Time                    | Unit                 | Capacity |
|-------------------|------------------------------------|----------------------|----------|
| Debeading         | Random.Triangular(0.2, 0.3, 0.5)   | min/tyre             | 1 tyre   |
| Cutting           | Random.Triangular(0.15, 0.25, 0.4) | min/tyre             | 1 tyre   |
| Shredding         | Random.Triangular(0.25, 0.4, 0.6)  | min/piece            | 1 piece  |
| Buffer            | No processing time                 | Waiting/storage only | Large    |
| Pyrolysis Reactor | Random.Triangular(18, 20, 23)      | hours/batch          | 10 tons  |

The triangular distributions were selected to represent processing-time
variability under practical operating conditions. These distributions
allow the model to capture minimum, most likely, and maximum processing
times for each operation.

4.  <span id="_Toc229301156" class="anchor"></span>**Appendix D:
    Batching Logic Used in the Simulation Model**

The batching logic was one of the most important elements in the
simulation model because the pyrolysis reactor operates in batch mode.

The logic was developed as follows:

| Item                                | Value       |
|-------------------------------------|-------------|
| Average tyre weight                 | 10 kg       |
| Reactor capacity                    | 10 tons     |
| Number of tyres required per batch  | 1000 tyres  |
| Number of pieces per tyre           | 4 pieces    |
| Number of pieces required per batch | 4000 pieces |

**Therefore:**

1 tyre = 4 pieces  
1000 tyres = 10 tons  
4000 pieces = 1 reactor batch

In the simulation model, shredded tyre pieces accumulate in the buffer
until 4000 pieces are available. Once this quantity is reached, the
combiner forms one complete batch and sends it to the pyrolysis reactor.

This logic was necessary to represent the difference between continuous
preprocessing operations and batch-based reactor operations.

5.  <span id="_Toc229301157" class="anchor"></span>**Appendix E:
    Economic Data and Financial Assumptions**

The economic data used in the feasibility analysis were mainly based on
the practical information obtained from **Bio Fuel Company**, supported
by market-based assumptions where needed.

| Economic Parameter            | Value                 |
|-------------------------------|-----------------------|
| Estimated initial investment  | 700,000 JD            |
| Monthly operating cost        | 7,000–10,000 JD/month |
| Daily operating cost          | 233–333 JD/day        |
| Expected daily product profit | 2,150–2,850 JD/day    |
| Expected net daily profit     | 2,217 JD/day          |
| Expected annual net profit    | 798,120 JD/year       |
| Expected payback period       | 0.88 years            |
| Expected ROI                  | 114%                  |

The economic feasibility analysis was developed to evaluate whether the
project can generate sufficient financial return under different
operating scenarios. Three scenarios were considered: conservative,
expected, and optimistic.

6.  <span id="_Toc229301158" class="anchor"></span>**Appendix F: Product
    Yield Assumptions**

The output distribution of the pyrolysis process was based on the
project data and typical product yield assumptions for waste tyre
pyrolysis systems.

| Product                             | Approximate Yield |
|-------------------------------------|-------------------|
| Pyrolysis oil / diesel-like product | 40%               |
| Carbon black                        | 30–40%            |
| Gas                                 | 10%               |
| Light fuel fraction                 | 10%               |
| Steel wires                         | 10%               |

The gas fraction was not treated as a direct sales revenue stream in the
financial model. Instead, it was assumed to be reused internally as a
heat source for the reactor. This reduces external fuel consumption and
improves the overall operating efficiency of the plant.

7.  <span id="_Toc229301159" class="anchor"></span>**Appendix G:
    Environmental Assessment Assumptions**

The environmental assessment was based on the principle that waste tyre
pyrolysis can support sustainable waste management by converting
end-of-life tyres into useful products.

The environmental evaluation considered the following aspects:

| Environmental Aspect         | Description                                                             |
|------------------------------|-------------------------------------------------------------------------|
| Waste reduction              | Reduces the accumulation of waste tyres in landfills and stockpiles     |
| Resource recovery            | Converts tyres into oil, carbon black, steel wires, gas, and light fuel |
| Energy recovery              | Reuses pyrolysis gas as a heat source for the reactor                   |
| Circular economy             | Treats waste tyres as recoverable resources rather than waste           |
| Avoided environmental burden | Reduces the need for uncontrolled burning or improper disposal          |

The environmental analysis was conceptual and did not include a complete
life cycle assessment. Therefore, the results should be considered
preliminary and should be supported by detailed emission measurements in
future work.

8.  <span id="_Toc229301160" class="anchor"></span>**Appendix H:
    Simulation Model Outputs**

The simulation model was used to evaluate the operational performance of
the proposed waste tyre pyrolysis system. The main outputs considered in
the analysis were:

| Output Indicator    | Purpose                                                   |
|---------------------|-----------------------------------------------------------|
| Throughput          | Measures the quantity of material processed by the system |
| Reactor utilization | Evaluates how intensively the reactor is used             |
| Machine utilization | Measures the use of preprocessing equipment               |
| Queue size          | Identifies congestion points                              |
| Waiting time        | Measures delays before processing stages                  |
| Buffer level        | Evaluates material accumulation before batching           |
| Bottleneck location | Identifies the main system limitation                     |
| Completed batches   | Measures the number of reactor batches processed          |

The simulation results showed that the preprocessing stages can supply
material continuously, while the pyrolysis reactor represents the main
bottleneck due to its long batch cycle time.

9.  <span id="_Toc229301161" class="anchor"></span>**Appendix I:
    Python-Based Financial Sensitivity Analysis**

A Python-based financial sensitivity model was used to evaluate the
effect of changes in operating cost and product profit on project
feasibility. The model calculated the following indicators:

| Financial Indicator | Description                                             |
|---------------------|---------------------------------------------------------|
| Net daily profit    | Daily product profit minus daily operating cost         |
| Monthly net profit  | Net daily profit multiplied by operating days per month |
| Annual net profit   | Monthly net profit multiplied by 12 months              |
| Payback period      | Initial investment divided by annual net profit         |
| ROI                 | Annual net profit divided by initial investment         |

The sensitivity analysis tested different scenarios, including increases
in operating costs and decreases in product profit. This helped identify
the financial risk of the project and evaluate its feasibility under
less favorable conditions.

10. <span id="_Toc229301162" class="anchor"></span>**Appendix J: Notes
    on Data Reliability and Study Boundaries**

The data used in this study were mainly obtained from **Bio Fuel
Company** and were used as the practical foundation for the simulation
and feasibility analysis. However, the study remains a preliminary
evaluation and should not be considered a final investment decision.

Several limitations should be considered:

1.  Actual operating conditions may differ from the assumed values.

2.  Product prices may change depending on market demand and product
    quality.

3.  Reactor downtime can significantly affect profitability.

4.  Environmental performance depends on emission control systems and
    regulatory compliance.

5.  The model does not include detailed chemical kinetics.

6.  The environmental assessment does not include a full life cycle
    assessment.

7.  The financial results depend strongly on the assumed CAPEX, OPEX,
    and daily product profit.

Therefore, future implementation should include detailed engineering
design, supplier quotations, pilot testing, product quality analysis,
environmental permitting, and market verification.

1.  <span id="_Toc229301163" class="anchor"></span>**Appendix K: Summary
    of Data Source**

All primary project data used in the simulation model, economic
feasibility analysis, and environmental assessment were derived from
information provided by **Bio Fuel Company**. The company data served as
the main practical reference for defining the production scale, process
assumptions, equipment requirements, cost structure, and expected
product outputs of the proposed waste tyre pyrolysis system.

Where direct data were unavailable, reasonable assumptions were made
based on project context and supported by literature values. This
approach allowed the study to develop a realistic preliminary evaluation
of the technical, economic, and environmental feasibility of the
proposed system.
