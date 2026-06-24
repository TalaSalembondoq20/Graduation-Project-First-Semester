# 04 Chapter 4 Simulation Model Development

4.  <span id="_Toc229233518" class="anchor"></span>Chapter 4: Simulation
    Model Development

    1.  <span id="_Toc229233519" class="anchor"></span>**Model
        Overview**

The presented model is designed to describe the work of the tire
pyrolysis system **as shown in the figure below**. It was created using
the discrete-event simulation technique, with Simio being the
development platform.

As for the boundaries of the simulation, they start from the moment when
the tyres arrive at the plant and end with producing their final
outputs, which include oil, carbon black, steel, and gas. As for the
main elements of the system, it is worth admitting that its description
implies not only mechanical operations but also thermal treatment of
tires, creating a hybrid production system.

As for the pre-processing, it involves three processes, including
debeading, cutting, and shredding of tires. Preprocessed material is put
in the buffer storage and then organized into batches. Each of them is
sent for processing to the pyrolysis reactor, which represents a key
unit of the whole process.

According to its peculiarities, it can be claimed that the pyrolysis
reactor works in the batch mode and is characterized by quite a long
period of processing compared to other processes, thus being a
bottleneck of the system. Finally, after the thermal treatment, the
material is divided according to the yield ratio of each output.

<img src="../media/image7.jpeg"
style="width:5.12418in;height:2.40397in" />

<span id="_Toc229236188" class="anchor"></span>**Figure 1: Real Waste
Tire Pyrolysis Plant Used as Reference for the Simulation Model
Development.**

2.  <span dir="rtl"><span id="_Toc229233520"
    class="anchor"></span></span>**Entity Definition and Flow Logic**

In this simulation model, the primary entity is defined as a *tire*,
representing a single unit of raw material entering the system. Each
tire undergoes a sequence of preprocessing operations before being
thermally processed in the pyrolysis reactor.

During the preprocessing stage, each tire is mechanically transformed
into smaller components to facilitate further processing. Specifically,
after the cutting stage, each tire is divided into four equal pieces.
These pieces then continue through the system as the main processing
units. This transformation allows for a more accurate representation of
material flow and handling within the system.

The flow logic of the model follows a sequential process, starting from
the arrival of tires into the system and ending with the generation of
final products. Tires are first introduced through the arrival source,
after which they pass through the debeading process, where steel wires
are removed. The tires are then processed in the cutting stage and
subsequently split into multiple pieces. These pieces are further
reduced in size during the shredding process.

After shredding, the processed pieces are directed to a buffer area,
where they are temporarily stored. This buffer plays a critical role in
regulating the flow of materials, particularly due to the batch nature
of the pyrolysis reactor. Once sufficient material is accumulated,
pieces are grouped into batches before entering the reactor.

The pyrolysis reactor operates as a batch-processing unit, where grouped
materials are subjected to thermal decomposition. Upon completion of the
reaction cycle, the outputs are separated into different product streams
based on predefined yield ratios.

The flow of entities within the system is governed by queue-based logic,
where materials move between processes based on availability and
capacity constraints. This structure enables the model to capture
real-world system dynamics such as waiting times, congestion, and
bottleneck formation.

Overall, the defined entity structure and flow logic provide a realistic
and scalable representation of the waste tyre pyrolysis system **as
shown in the figure below**, supporting detailed analysis of system
performance and behavior under different operating conditions.

<img src="../media/image8.png"
style="width:5.485in;height:2.50139in" />

<span id="_Toc229236189" class="anchor"></span>**Figure 2: The pyrolysis
process flows.**

3.  <span id="_Toc229233521" class="anchor"></span>**Processes
    Modeling**

This part discusses the process modeling of the main operations in the
waste tyres pyrolysis system. As was mentioned previously, all processes
are represented as services that operate based on specified time
distributions and capacities.

1.  <span id="_Toc229233522" class="anchor"></span>**Debeading**

The process of debeading is the first mechanical operation that should
be performed. It involves the removal of steel wires from the tyre and
serves both protection of the subsequent operations from damage and
material acquisition.

In the simulated model, the operation is represented as a server with a
triangular distribution of the processing times:

**Random.Triangular(0.2, 0.3, 0.5) minutes per tyre**

The operation is performed with the capacity of 1 tyre per machine at a
time; in order to increase the capacity, several parallel machines are
employed in the system:

Capacity per machine: 1 tyre

2.  <span id="_Toc229233523" class="anchor"></span>**Cutting**

After devebading of the tyres, they pass to the cutting process, which
entails their cutting in order to prepare the tyres for further
processing and reduce handling costs.

The process is modeled using a triangular distribution of the processing
times as well:

**Random.Triangular(0.15, 0.25, 0.4) minutes per tyre**

The same principle as above applies to the process capacity; there is a
limited amount of space on one machine, therefore several parallel
servers are introduced to increase the total capacity:

Capacity per machine: 1 tyre

3.  <span id="_Toc229233524" class="anchor"></span>**Shredding**

The third process – shredding – involves the reduction of tyre parts in
order to make them suitable for being put into the pyrolysis reactor.
The shredding operation is considered the most important one because it
is labour-intensive.

The process is also simulated using a triangular distribution of
processing times; however, since now tyres are not whole but split into
pieces, the time distribution is applied to every piece:

**Random.Triangular(0.25, 0.4, 0.6) minutes per piece**

It is evident that in this stage there will be more entities processed
because of the splitting, thus there will be a need for increased
capacity; in order to meet this goal, two or three machines may be used
depending on the requirements:

Capacity per machine: 1 piece

4.  <span id="_Toc229233525" class="anchor"></span>**Buffering**

The next step of the process is passing to the buffering operation,
which is crucial for the effective work of the system because of the
batch-wise processing of the reactor. Buffering involves putting
processed material pieces into a buffer, where they will wait until
their turn comes.

Buffering is represented in the simulation as a queue without processing
times, as the buffer will only be used for storing the pieces:

Processing time: None (waiting only)

5.  <span id="_Toc229233526" class="anchor"></span>**Pyrolysis Reactor
    (Oven)**

The pyrolysis reactor represents the core component of the system, where
thermal decomposition of shredded tire material takes place. This
process converts the material into oil, carbon black, steel, and gas.

The reactor operates in a batch mode and is characterized by a long
processing cycle compared to other processes.

In the simulation model, the reactor processing time is defined as:

**Random.Triangular(18, 20, 23) hours per batch**

The reactor has a fixed capacity:

- Reactor capacity: **10 tons per batch**

This means that each batch processed in the reactor contains material
equivalent to 10 tons of shredded tire pieces.

Due to its long processing time and batch operation, the reactor is
considered the primary bottleneck in the system.

This table summarizes the main production characteristics of the
simulated system.

<span id="_Toc229236263" class="anchor"></span>**Table 4: General
Production Data.**

| Parameter            | Value              |
|----------------------|--------------------|
| Average Tire Weight  | 10 kg              |
| Tires per Day        | 1000 – 1500 Tires  |
| Daily Production     | 10 – 15 tons/day   |
| Pieces per Tire      | 4 Pieces           |
| Total Pieces per Day | 4000 – 6000 Pieces |

This table defines the processing times and capacity constraints of all
system components.

<span id="_Toc229236264" class="anchor"></span>**Table 5: Processing
Times and Capacities**

| Process        | Processing Time                    | Unit        | Capacity |
|----------------|------------------------------------|-------------|----------|
| Debeading      | Random.Triangular(0.2, 0.3, 0.5)   | min/tire    | 1        |
| Cutting        | Random.Triangular(0.15, 0.25, 0.4) | min/tire    | 1        |
| Shredding      | Random.Triangular(0.25, 0.4, 0.6)  | min/piece   | 1        |
| Buffer         | —                                  | —           | Large    |
| Reactor (Oven) | Random.Triangular(18, 20, 23)      | hours/batch | 10 tons  |

This table shows the calculated system load based on production targets.

<span id="_Toc229236265" class="anchor"></span>**Table 6: Derived System
Load.**

| Parameter                   | Value             |
|-----------------------------|-------------------|
| Pieces per Minute (10 tons) | ≈ 2.8 pieces/min  |
| Pieces per Minute (15 tons) | ≈ 4.2 pieces/min  |
| Reactor Cycle               | ≈ 1 batch/day     |
| Reactor Output              | 10 tons per batch |

<span id="_Toc229233527" class="anchor"></span>

1.  **Logic of Batching**

The logic of batching is an essential part of the simulation model
because the pyrolysis reactor runs in batches. Different from the
preprocessing stages, where a continuous flow is maintained, the reactor
needs a certain amount of material to be accumulated before each batch
starts to run.

In the designed model, tires pass the mechanical processes and are
broken down into smaller pieces, which allows handling and further
processing. Particularly, a tire is divided into four pieces after the
cutting process. The tires move on to the next step of shredding and are
sent to the buffer for storage.

Batching logic is used to supply the reactor with a full batch equal to
the capacity of the reactor. Considering the average tire mass of 10 kg,
each tire provides 10 kg of raw material for the system. Thus, in order
to supply the reactor with one batch of 10 tons, 1000 tires should be
accumulated in the buffer.

As each tire is broken into four parts, batching is carried out
according to the amount of pieces, not tires. Thus, the following logic
is applied to determine the required number of entities to create a
batch:

**1 tire = 4 pieces**

**1000 tires = 10 tons**

**4000 pieces = 1 batch**

When 4000 pieces are accumulated in the buffer, they are combined into
one batch using a combiner method and sent to the reactor for further
processing.

Such batching logic is needed to maintain full reactor capacity during
operation to maximize its productivity. At the same time, batching
causes the introduction of waiting times in the process, as entities
have to wait to accumulate a full batch in the buffer.

The combination of continuous processing at the first stages and batch
mode at the last step results in a dynamic process with accumulation and
waiting times being determined by the relationship between the speed of
processing and the capacity of the reactor. Such dynamics is vital to
understand system performance.

2.  <span dir="rtl"><span id="_Toc229233528"
    class="anchor"></span></span>**Reactor Modeling**

The pyrolysis reactor is seen as the core component in the processing
plant, where the process of decomposition of shredded tires occurs. The
reactor operates in batch processing fashion, having a rather long
processing time when compared with all other system components.

According to the simulation model, the reactor is modeled as a server
having the processing time defined as follows:

**Random.Triangular(18, 20, 23) hours per batch**

The reactor has the capacity:

**10 tons per batch**

The capacity mentioned above means that it needs the specific amount of
material to start operating. After being loaded into the reactor, the
system undergoes heating, reaction, and cooling cycles until the process
is completed and the material is unloaded.

Given its long cycle time and limited capacity, the reactor turns into
the bottleneck for the system. Thus, it plays a crucial role in system
efficiency.

The interdependence between the batch formation and reactor operation is
one of the most important aspects of the system operation since if there
is not enough material to feed the reactor, the machine remains idle; if
too much material is supplied, the buffer overflows.

Reactor modeling helps to simulate the real-life operation of an
industrial reactor and evaluate the system behavior.

3.  <span dir="rtl"><span id="_Toc229233529"
    class="anchor"></span></span>**Output Separation Logic**

The output distribution in the created model is established using actual
data of the system. The products obtained as a result of the pyrolysis
are divided into a number of streams according to their percentage
ratio.

The output distribution is presented below:

- Diesel (primary liquid): 40%

- Carbon black: 30% – 40%

- Gas: 10%

- Fuel (light fraction): 10%

- Steel wires: 10%

  1.  <span dir="rtl"><span id="_Toc229233530"
      class="anchor"></span></span>**Resource Allocation and Capacity
      Planning**

Proper resource allocation and capacity planning are required to ensure
efficient functioning of the system and to reach the desired output
levels. For the developed simulation model, there is only one machine
for each processing stage involved, while the use of labor force is
taken into account to provide for the whole system functioning.

Preprocessing stage involves such activities as debeading, cutting, and
shredding. Each activity involves one machine working at a capacity of
one entity at a time.

**Resource allocation can be formulated as follows:**

- Debeading: 1 machine

- Cutting: 1 machine

- Shredding: 1 machine

Along with machines, there is a labor force of around **10–15 people**
involved in the process, performing such operations as material
handling, machine operation and control, loading/unloading procedures,
etc.

Pyrolysis reactor serves as the most important resource of the whole
system due to its nature of batch processing involving a fixed batch
size **(10 tons per batch)** and rather long processing period.
Consequently, it becomes the main bottleneck of the process.

The focus of capacity planning here lies in the interaction between
limited machine resources and batch process. Since every preprocessing
stage involves just one machine, the whole system becomes rather
vulnerable to any disturbances in the process.

Having a labor force in addition contributes to effective operation and
material transportation. Nevertheless, the system is still affected by
limited capacity of machines and long periods of reactor work.

Such resource allocation makes for a rather realistic model of the
system on the experimental level.

1.  <span id="_Toc229233531" class="anchor"></span>**Model
    Implementation in Simio**

A simulation model has been developed using Simio as the object-oriented
discrete-event simulation framework. The objective of developing the
model was to study the behaviour of the Waste Tyre Pyrolysis process via
simulation.

System components have been created using the objects available in
Simio. Simulation objects that can be used to create systems are
standard and each represents a certain functionality. The following
objects are required to create the model for this system:

***Source*:** Tire Arrival with defined interarrival time.

***Server***: Server is used to model processing operations of various
types. Debeading, cutting, shredding and pyrolysis reactor are modelled
as servers with processing times defined using triangular distribution.

***Buffer/ Queue***: Buffer is used to store the shredded material
temporarily before it is placed in batches.

***Combiner***: Combiner is used to implement batch processing of
material and create fixed size batches before releasing it for further
processing.

***Separator***: This is used to split up reactor output into two or
more flows based on yields at predefined ratio.

***Sink***: Sink will be used to mark exit points for final products
from the system.

Logical arrangement of objects has been made to reflect the flow of
entities as in the process. Pre-processing of entities is carried out
first followed by accumulation of them in buffer before releasing in
batches for processing in reactors.

Triangular probability distributions are used to define processing times
for all activities involved. Consistent units of time have been used
throughout the model for processing of entity where pre-processing
activities use minutes and reactor uses hours.

The batch creation mechanism has been implemented using combiner object
which groups a number of pieces equal to the reactor capacity in each
batch. Output separation is done by creating separate paths based on
predefined percentage.

Model has been implemented to run continuously for
<span dir="rtl">48</span>-hour cycle to analyse system performance
<span dir="rtl"></span>**as shown in the figures below**. Relevant
parameters like arrival rate, processing time etc. have been set as per
the required level of production.

<img src="../media/image9.png"
style="width:4.40907in;height:2.75802in" />

<span id="_Toc229236190" class="anchor"></span>**Figure 3: Overall
Simulation Model Layout (3D View).**

<img src="../media/image10.png"
style="width:4.18587in;height:3.31605in" />

<span id="_Toc229236191" class="anchor"></span>**Figure 4: Top View of
the Simulation Model.**

<img src="../media/image11.png"
style="width:4.50874in;height:2.51208in" />

<span id="_Toc229236192" class="anchor"></span>**Figure 5:Operational
View of the Simulation Environment.**
