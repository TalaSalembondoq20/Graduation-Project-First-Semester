# 05 Chapter 5 Simulation Results and Analysis

5.  <span id="_Toc229233532" class="anchor"></span>Chapter 5: Simulation
    Results and Analysis

    1.  <span dir="rtl"><span id="_Toc229233533"
        class="anchor"></span></span>**Base Case Simulation Results**

In this section, the results obtained will be discussed concerning the
application of the simulation model developed based on the modified
system assumptions. <span dir="rtl"></span>It should be noted that in
the created model, the process of waste tyres pyrolysis can be
considered a continuous process of <span dir="rtl">48</span>-hour
duration. Moreover, the entire process depends on specific parameters
which are considered in the system.

In the created simulation model, each tire passes through the stages of
preprocessing, which include, in the first place, the debading to
eliminate steel wires. In addition, each tire is divided into four
parts.

Further, the four obtained pieces go through the shredding process to
get small enough pieces ready for heating. Taking into consideration
that the process of pyrolysis in the reactor is conducted based on the
batch principle, while one tire is divided into four parts, it is
necessary to consider batches consisting of these parts but not tires
themselves.

According to the proposed modification, **1 tire consists of 4 pieces;
1000 tires make up 10 tons; 4000 pieces make up one batch**. It means
that to start the reactor, there should be 4000 pieces accumulated in
the buffer (or 1000 tires and 10 tons).

**Table 4** contains the general system production characteristics.
First, the simulation model assumes that the average weight of the tire
is 10 kg. It means that the daily production of the system falls in the
range of **10-15 tons**, which means that there are to be processed
between 1000 and 1500 tires per day.

**Table 5** represents the processing times and capacity limitations for
the system components. All preprocessing procedures are estimated to be
using **triangular distribution**, since this process is continuous and
includes one unit processing. As for the reactor, it functions as a
batch unit and takes about 18-23 hours to process 10 tons of material in
one batch.

Analyzing the obtained data regarding system operation, it is possible
to suggest that the preprocessing procedure should process approximately
2.8-4.2 tire pieces per minute, which implies a constant inflow of
material to the reactor.

The results obtained through conducting simulations prove that it is
possible to accumulate full batches, whose volume corresponds to the
capacity of the reactor. This indicates the interaction of both
continuous operation and batch accumulation mechanisms.

It is obvious that the reactor is the only system component that
requires considerable amount of time to conduct its function (about
18-23 hours). Thus, it is the bottleneck of the system and defines its
capacity and the total production capacity.

In this way, the results received within the simulation model
development prove that it is possible to meet the necessary production
range of 10-15 tons per day.

2.  <span id="_Toc229233534" class="anchor"></span>**Throughput
    Analysis**

This part analyzes the throughput of the proposed system based on the
simulation results received during base case scenario setting up.
<span dir="rtl"></span>Throughput is considered as an indicator
measuring the speed of transformation of material into batches of
material that needs to be sent to thermal treatment.

Based on the described system, the throughput rate is associated with
batching and the capacity of the reactor. Thus, the throughput rate will
directly depend on the number of batches produced daily with the use of
the batch size of 10 tons defined in the simulation.

According to the system load calculation presented in table 3, to meet
the production objective of 10-15 tons of material per day, the
pre-processing stage should provide the reactor with the average rate of
about 2.8-4.2 pieces per minute.

According to the simulation results, the system can guarantee
uninterrupted throughput in the pre-processing stage, that is, feeding
of the system with material. This implies that the material is being
supplied to the PartsCombiner where all parts of materials are combined
to form a batch.

Consequently, the throughput rate will depend only on the batching speed
because the reactor can process each batch within about 18-23 hours.
<span dir="rtl"></span>Under the current conditions, the system can
handle about one batch per day and reach the throughput rate of about:

**10 tons per day (per reactor)**

Hence, the maximum throughput of the system is limited by the speed of
batches' processing in the reactor **as shown in the figure below.**
Although the pre-processing stages can provide a higher throughput rate
of material, this rate is constrained by the batching rate and a long
cycle time.

Overall, the results prove that the throughput rate is stable and
consistent. At the same time, there were no material losses associated
with batching.

Throughput rate can be increased due to reducing the reactor cycle time
or installing additional reactors.

<img src="../media/image12.png"
style="width:3.98611in;height:2.98958in" />

<span id="_Toc229236193" class="anchor"></span>**Figure 6: Process
Capacity Comparison Across System Stages.**

This figure presents key performance indicators extracted from the
simulation results, including total entities entered, total entities
exited, and average buffer level.

<img src="../media/image13.png"
style="width:4.40741in;height:3.30556in" />

<span id="_Toc229236194" class="anchor"></span>**Figure 7: Key System
Performance Indicators.**

3.  <span id="_Toc229233535" class="anchor"></span>**Resource
    Utilization Analysis**

This part of the analysis will consider resource utilization metrics
which are calculated according to the simulated model of the waste tire
pyrolysis process. Resource utilization is one of the critical metrics
used to evaluate the performance of manufacturing and simulation systems
as it reflects the efficiency of each component's usage of its capacity.
In the current system, the preprocessing processes (debeading, cutting,
and shredding) are simulated as continuous machine-based operations that
have short processing times. Therefore, because of the fast execution of
these processes, the machines can operate without serious interruptions,
and their utilization rates are rather low in most parts of the
simulation period.

On the other hand, pyrolysis is modeled as a batch-based machine-based
operation with a long cycle. The reactor operation cycle begins after
the arrival of the whole batch, and the processing time for each batch
is estimated as 18–23 hours. This explains why utilization rate dynamics
differ considerably from the others.

**Figure 8** illustrates the variation in utilization rates among the
different system components. According to the chart shown below,
utilization rates for the preprocessing operations remain relatively low
because of the continuous work and short processing times. Also, the
utilization rates of the debeading and cutting operations are about the
same because their processing times are identical. Still, the
utilization rate for the shredding machine is slightly higher than the
previous ones because the number of processed entities is greater.

The utilization rate for the buffer is relatively high since the
shredded tires keep coming to this place until the batching process
starts. It is worth mentioning that the lowest utilization rate is
provided by the combiner machine as this machine only starts its
operation after gathering the necessary batch of materials. In contrast,
the reactor machine turns out to be the most utilized one. The extremely
high utilization rate of the reactor is explained by the large cycle
time, capacity (10 tons), and high utilization rate. Consequently,
during most of the simulation period, the reactor is occupied with the
process of pyrolysis, resulting in the reactor machine's high
utilization rate affecting the productivity of the entire process
considerably.

As seen from the results, the preprocessing operations can provide
enough material for continuous loading of the reactor without
significant delays. However, the productivity of the system as a whole
depends on the reactor's capacity and processing time. This fact means
that the productivity of the system is limited by the productivity of
the reactor. Moreover, the introduction of a buffer in the system
reduces the influence of the differing operational regimes of continuous
and batch-processing components. The process of accumulating shredded
tires in the buffer helps in maintaining smooth functioning and
preventing stages from being blocked due to differing processing.
However, it is still possible to observe different utilization rates
based on the characteristics of components.

<img src="../media/image14.png"
style="width:5.75379in;height:2.59705in" />

<span id="_Toc229236195" class="anchor"></span>**Figure 8: Resource
Utilization Comparison Across System Components.**

Additionally, **Table 7** summarizes the expected utilization behavior
and interpretation of each resource in the system. The preprocessing
machines maintain moderate utilization levels due to their short
processing times, while the shredding machine shows relatively higher
utilization because of the increased number of processed tire pieces.
The buffer utilization varies depending on the accumulation of material
before batching, whereas the reactor records the highest utilization
level because of its long batch-processing cycle.

Thus, because of the conducted analysis, it becomes obvious that the
reactor represents the main restriction for the process under
discussion. High utilization rates of this resource compared to other
components indicate that the reactor is responsible for defining the
capacity and throughput of the entire process. Increasing reactor
performance by reducing cycle time or expanding capacity will lead to
increased productivity of the system.

<span id="_Toc229236266" class="anchor"></span>**Table 7: Resource
Utilization Interpretation.**

| Resource          | Expected Utilization Level | Interpretation                          |
|-------------------|----------------------------|-----------------------------------------|
| Debeading Machine | Moderate                   | Fast preprocessing stage                |
| Cutting Machine   | Moderate                   | No major delay expected                 |
| Shredding Machine | Medium to High             | Handles four pieces per tire            |
| Buffer            | Variable                   | Accumulates material for batching       |
| Reactor           | Very High                  | Main bottleneck due to long batch cycle |

4.  <span id="_Toc229233536" class="anchor"></span>**Queue and Waiting
    Time Analysis**

The behavior of queues and waiting times will be considered here since
it is a crucial indicator of the system's efficiency. In general, a
queue is formed due to a higher arrival rate of entities than the
processing capability of a particular stage or due to slow processing.

The formation of a queue in our system takes place in front of batching
and the reactor stage because all actions of preprocessing occur
continuously, whereas the reactor performs in batches. That is why
material accumulates until the formation of a new batch is ready for
processing.

Analyzing the results obtained of modeling, we can see that the average
queue size in the output buffer is close to zero and does not exceed one
unit per minute. It means that the system functions effectively without
any issues of congestion. <span dir="rtl"></span>However, it needs to be
noted that such a level of waiting time in the system is quite logical
because it is conditioned by the peculiarities of the batch formation
process. The queue occurs as soon as the required number of entities is
formed (4000 units). The behavior of the queue reveals how batching
influences system performance. In contrast to the usual queue, in the
case we have, it means periodic system congestion followed by
processing. Hence, it is quite a regular occurrence in the
batch-oriented system. It should be mentioned that no additional queues
in the system indicate that preprocessing is balanced with batching
activities.

The queue sizes and average waiting times obtained from the simulation
results for each processing stage are summarized in **Table 8** below.

<span id="_Toc229236267" class="anchor"></span>**Table 8: Queue Size and
Average Waiting Time Across Process Stage.**

| Process Stage         | Average Queue Size | Average Waiting Time |
|-----------------------|--------------------|----------------------|
| Debeading             | 0.5                | 0.2 min              |
| Cutting               | 0.7                | 0.3 min              |
| Shredding             | 1.5                | 0.8 min              |
| Buffer Before Reactor | 18                 | 6.5 hr               |
| Reactor Queue         | 22                 | 8.2 hr               |

5.  <span id="_Toc229233537" class="anchor"></span>**Bottleneck Analysis
    and System Improvement Opportunities**

This section analyzes the main bottlenecks identified in the waste tire
pyrolysis system and discusses possible improvements to enhance overall
system performance and productivity. Based on the simulation results
obtained in the previous sections, the pyrolysis reactor represents the
primary bottleneck of the system due to its long batch-processing cycle
and high utilization rate.

The preprocessing stages, including debeading, cutting, and shredding,
operate efficiently with relatively low waiting times and moderate
utilization levels. These processes can supply material continuously
without causing significant congestion. However, because the reactor
requires a complete batch before operation and needs approximately 18–23
hours to complete one cycle, material accumulates in the buffer before
the reactor stage.

The simulation results indicate that the throughput of the entire system
is mainly constrained by reactor performance. Consequently, any
improvement in reactor operation would directly affect total system
productivity. Several improvement opportunities can therefore be
considered.

One possible improvement is reducing the reactor cycle time through
process optimization or operational adjustments. Another potential
solution is to increase reactor capacity or introducing an additional
reactor unit to distribute the processing load and reduce waiting times
before batching.

Furthermore, optimizing batching policies and buffer management could
improve material flow and reduce unnecessary accumulation before the
reactor stage. These modifications would help improve throughput, reduce
congestion, and increase overall system efficiency.

Overall, the bottleneck analysis confirms that the reactor is the
dominant limiting factor within the proposed pyrolysis system, and
improving reactor-related operations would provide the greatest
enhancement in system performance.

6.  <span id="_Toc229233538" class="anchor"></span>**System Performance
    Evaluation**

System Performance Evaluation was carried out to determine the
efficiency and effectiveness of the operation of the proposed waste tire
pyrolysis plant. Such performance metrics as the rate of throughput,
resource utilization, behavior of queues, waiting times, and stability
of production were analyzed.

According to the simulation results, it can be claimed that the system
has the capability to reach the target production capacity, which is
10–15 tons of waste tires daily under chosen conditions of operation.
Besides, the operation of the preprocessing phases of debeading,
cutting, and shredding of materials proves their stability, low waiting
times, and resource utilization. It means that the preprocessing unit
can provide a constant supply of materials for the batching stage
without any disruptions.

The analysis of the throughput shows that stable material supply to all
phases of the preprocessing process of waste tires can take place. As a
result, stable material supply from the preprocessing stage to the
batching stage ensures the creation of a complete reactor batch without
material losses. According to the chosen configuration of reactors, one
reactor batch can be processed daily.

However, at the same time, the reactor stage demonstrates the highest
rate of utilization among all the stages of the process and the most
extended waiting times. Because of the long processing time of one
reactor batch, a queue occurs in front of the reactor because of its
limited capacity. Nevertheless, the occurrence of waiting times does not
cause any disruptions in the operation of the system or its blocking.

As far as the behavior of queues is concerned, it is essential to
mention that they occur in front of the reactor and batching stages. On
the contrary, the other stages show balance, effective performance, and
absence of material supply issues.

Therefore, based on the simulation results, it can be said that the
waste tire pyrolysis system will be capable of efficient and steady
operation. The system is technically possible, whereas the reactor may
act as a limiting factor because of its high productivity.

<span id="_Toc229236268" class="anchor"></span>**Table 9: summarizes the
overall evaluation of the major system performance indicators.**

| Performance Indicator     | Evaluation Result                |
|---------------------------|----------------------------------|
| Throughput Stability      | Stable                           |
| Preprocessing Performance | Efficient                        |
| Reactor Utilization       | Very High                        |
| Queue Formation           | Mainly before reactor            |
| Waiting Times             | Acceptable under batch operation |
| System Congestion         | Limited                          |
| Overall Productivity      | Satisfactory                     |
| Main Limitation           | Reactor cycle time               |
