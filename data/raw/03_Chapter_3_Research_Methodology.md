# 03 Chapter 3 Research Methodology

3.  <span id="_Toc229233515" class="anchor"></span>Chapter 3: Research
    Methodology

    1.  <span id="_Toc229233516" class="anchor"></span>**Research
        Approach**

In this regard, the study will employ applied quantitative research
design to evaluate the feasibility of the small-scale waste tyre
pyrolysis plant, taking into consideration the technological, economic
and environmental aspects. In particular, the research seeks to develop
a systematic simulation model in analyzing the operations of the plant
and relate its results to the evaluation criteria regarding economy and
environment.

It is appropriate because the waste tyre pyrolysis system is not only a
process of chemical reactions. Instead, it is more like an industrial
system dealing with issues such as material flow, machine capacity,
delay, batching, resources and product recovery. Thus, applied discrete
event simulation combined with feasibility analysis should be used to
undertake this evaluation successfully.

The approach necessitates the following three main analytical dimensions
to be taken into account. First, simulation analysis entails analyzing
the physical performance of the plant. Second, the aspect of economic
feasibility is concerned with investment cost, operating cost, income
earning potential, profitability, payback period and return on
investment. Third, environmental feasibility implies evaluating
sustainability benefits derived from waste tires and avoiding disposal
methods such as landfills and incineration.

2.  <span id="_Toc229233517" class="anchor"></span>**Research Design**

The research design is based on sequential modeling and analysis. First,
there will be identification of the process flow in the waste tyre
pyrolysis plant. It begins at the point where tyres are collected from
various sources until their separation into different end products. The
second step is to create the simulation model with the use of Simio
simulation tool. The third step is to analyze the simulation model by
investigating its output variables such as throughput rate, resource
utilization, queuing, waiting times, etc.

The research design can be summarized as follows:

1.  Define the system boundaries and process stages.

2.  Identify input data, assumptions, capacities, and processing times.

3.  Build the discrete-event simulation model using Simio.

4.  Run the base-case simulation scenario.

5.  Extract and analyze operational performance indicators.

6.  Conduct economic feasibility analysis using cost and revenue
    assumptions.

7.  Evaluate environmental benefits based on waste reduction, product
    recovery, and energy recovery.

8.  Develop a prototype mobile application interface to represent the
    digital monitoring concept used for tracking machine status,
    material levels, reactor condition, alerts, and reports.

9.  Discuss integrated findings and provide recommendations.

This design allows the study to move from technical modeling to
practical decision-making. It also helps identify whether the proposed
plant can operate efficiently and whether the project is financially and
environmentally feasible.

**3.3 System Modeling Strategy**

The system modeling strategy is based on representing the waste tyre
pyrolysis plant as a discrete-event production system. In this approach,
tyres are modeled as entities moving through a sequence of processing
stages. Each stage is represented by simulation objects such as sources,
servers, queues, combiners, separators, and sinks.

The model begins with the arrival of waste tyres into the system. Each
tyre passes through preprocessing operations including debeading,
cutting, and shredding. After cutting, each tyre is divided into four
pieces. These pieces are then processed through shredding and stored in
a buffer before being combined into a batch for the pyrolysis reactor.

The pyrolysis reactor is modeled as a batch-processing unit because it
cannot process individual tyre pieces continuously. Instead, the reactor
starts operation only when a full batch is available. In this study, one
batch is equivalent to 10 tons of shredded tyre material. Since the
average tyre weight is assumed to be 10 kg, 1000 tyres are required to
form one 10-ton batch. Because each tyre is divided into four pieces,
the model requires 4000 pieces to create one reactor batch.

This modeling strategy allows the study to capture the interaction
between continuous preprocessing operations and batch-based thermal
treatment. It also supports the identification of bottlenecks,
especially at the reactor stage.

**3.4 Process Flow Definition**

The process flow of the proposed system begins with the arrival of waste
tyres at the plant. The tyres first enter the debeading process, where
steel wires are removed. This stage is important because it protects
downstream equipment and allows partial recovery of steel material.

After debeading, the tyres move to the cutting process. During this
stage, each tyre is divided into four pieces to make handling and
shredding easier. The pieces then enter the shredding process, where
they are reduced into smaller material suitable for pyrolysis.

The shredded material is then sent to a buffer area. The buffer is
necessary because the preprocessing stages operate continuously, while
the pyrolysis reactor operates in batches. Once 4000 pieces are
accumulated, the combiner creates one full batch equivalent to 10 tons
of material. This batch is then transferred to the pyrolysis reactor.

Inside the reactor, the material undergoes thermal decomposition. After
the reaction cycle is completed, the output is separated into different
product streams, including pyrolysis oil, carbon black, gas, light fuel
fraction, and steel wires.

The process flow can therefore be summarized as:

**Waste Tyre Arrival → Debeading → Cutting → Splitting into Four Pieces
→ Shredding → Buffering → Batch Formation → Pyrolysis Reactor → Product
Separation → Final Product Streams**

**3.5 Model Assumptions**

Several assumptions were adopted to simplify the simulation model while
maintaining realistic representation of the system. These assumptions
are necessary because some industrial data may vary depending on tyre
type, machine condition, reactor design, operating temperature, and
market conditions.

The main model assumptions are:

1.  The average weight of one tyre is assumed to be 10 kg.

2.  The plant processes approximately 1000 to 1500 tyres per day.

3.  The daily production capacity is estimated at 10 to 15 tons per day.

4.  Each tyre is divided into four pieces after the cutting stage.

5.  One reactor batch requires 4000 tyre pieces, equivalent to 1000
    tyres or 10 tons.

6.  The reactor operates in batch mode.

7.  The reactor processing time follows a triangular distribution
    between 18 and 23 hours.

8.  The preprocessing stages operate as continuous machine-based
    processes.

9.  The buffer before the reactor has sufficient capacity to accumulate
    material for batching.

10. Product yields are assumed based on common pyrolysis output ranges
    and project assumptions.

11. Gas is reused internally as an energy source and is not treated as
    direct sales revenue.

12. The simulation focuses on operational performance and does not model
    detailed chemical reaction kinetics.

These assumptions make the model suitable for preliminary technical and
economic evaluation.

**3.6 Data Collection and Input Parameters**

The input data used in the model were collected from project
assumptions, literature-based values, supplier information, and
estimated operational parameters. The simulation model requires data
related to production capacity, processing times, machine capacities,
batch size, product yield, and financial assumptions.

The main production data include an average tyre weight of 10 kg, a
daily input range of 1000–1500 tyres, and a production range of 10–15
tons per day. The reactor capacity is assumed to be 10 tons per batch.
Since each tyre is divided into four pieces, the total number of pieces
processed per day ranges from 4000 to 6000 pieces.

Processing times are modeled using triangular distributions because they
reflect minimum, most likely, and maximum processing durations. This is
suitable for industrial systems where exact processing times may vary
due to operator performance, machine condition, and material
variability.

The key processing time assumptions are:

<span id="_Toc229300468" class="anchor"></span>**Table
1<span dir="rtl">:</span> The key processing time assumptions.**

| Process   | Processing Time                    | Unit        |
|-----------|------------------------------------|-------------|
| Debeading | Random.Triangular(0.2, 0.3, 0.5)   | min/tyre    |
| Cutting   | Random.Triangular(0.15, 0.25, 0.4) | min/tyre    |
| Shredding | Random.Triangular(0.25, 0.4, 0.6)  | min/piece   |
| Reactor   | Random.Triangular(18, 20, 23)      | hours/batch |

The financial input parameters include an estimated capital investment
of 700,000 JD, monthly operating costs ranging from 7,000 to 10,000 JD,
and daily product profit ranging from 2,150 to 2,850 JD/day.

**3.7 Simulation Setup and Configuration**

The simulation model was developed using Simio as an object-oriented
discrete-event simulation platform. The model was configured to
represent the physical and logical flow of the waste tyre pyrolysis
plant.

The main Simio objects used in the model include:

<span id="_Toc229300469" class="anchor"></span>**Table 2: The main Simio
objects used in the model .**

| Simio Object   | Function in the Model                                            |
|----------------|------------------------------------------------------------------|
| Source         | Generates arriving waste tyres                                   |
| Server         | Represents debeading, cutting, shredding, and reactor operations |
| Buffer / Queue | Stores shredded material before batching                         |
| Combiner       | Combines 4000 pieces into one reactor batch                      |
| Separator      | Splits reactor output into different product streams             |
| Sink           | Represents final exit points for products                        |

The model was configured for a 48-hour operating period to observe
system behavior across more than one production cycle. Processing times
were assigned using triangular probability distributions. The reactor
was configured as the main batch-processing resource with a capacity of
10 tons per batch.

The simulation model was used to evaluate whether the preprocessing
stages can supply enough material to the reactor, whether the buffer can
support batch formation, and whether the reactor creates a bottleneck in
the system.

**3.8 Key Performance Indicators (KPIs)**

The performance of the simulation model was evaluated using several key
performance indicators. These KPIs were selected because they reflect
the operational efficiency, capacity, and stability of the proposed
system.

The main KPIs are:

<span id="_Toc229300470" class="anchor"></span>**Table 3: The main KPIs
used in the project.**

| KPI                         | Purpose                                                                   |
|-----------------------------|---------------------------------------------------------------------------|
| Throughput                  | Measures the amount of material processed by the system                   |
| Reactor utilization         | Measures how intensively the reactor is used                              |
| Machine utilization         | Evaluates the use of preprocessing equipment                              |
| Average queue size          | Identifies congestion points in the system                                |
| Average waiting time        | Measures delays before each process                                       |
| Buffer level                | Evaluates material accumulation before batching                           |
| Number of completed batches | Measures production cycle achievement                                     |
| Bottleneck location         | Identifies the process limiting system performance                        |
| System stability            | Assesses whether the system operates without major blocking or starvation |

These indicators help determine whether the plant can meet the target
production level of 10–15 tons/day and whether the reactor capacity is
sufficient for stable operation.

**3.9 Model Verification and Validation**

Model verification was conducted to ensure that the simulation model was
built correctly according to the defined process logic. This included
checking the sequence of operations, entity transformations, routing
logic, batch formation, processing times, and output separation. Special
attention was given to verifying that each tyre is correctly converted
into four pieces and that 4000 pieces are required to create one reactor
batch.

The verification process also included reviewing the logical behavior of
queues, buffers, and the combiner. The model was checked to ensure that
the reactor does not start until a full batch is available and that
products are separated according to the predefined yield ratios.

Model validation was conducted by comparing the model behavior with
expected industrial logic and project assumptions. The simulated output
was evaluated against the expected daily capacity of 10–15 tons/day and
the reactor batch capacity of 10 tons. The results showed that the model
behavior is consistent with the expected system structure, where
preprocessing operations are relatively fast and the reactor becomes the
main bottleneck due to its long processing time.

Although the model provides a useful representation of the proposed
system, validation remains limited by the availability of actual plant
operating data. Therefore, the model should be considered a preliminary
decision-support model rather than a final industrial design model.
