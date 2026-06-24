# 08 Chapter 8 Mobile Application Interface

8.  <span id="_Toc229301131" class="anchor"></span>Chapter
    **<span dir="rtl">8</span>**: Proposed BioFuel Mobile Application
    Interface

    1.  <span id="_Toc229301132" class="anchor"></span>**Concept of the
        Application**

As an additional practical contribution to the project, a simple mobile
application interface was proposed under the name BioFuel. The
application is designed as a front-end prototype that supports the
monitoring of the waste tyre pyrolysis system. It does not represent a
fully connected industrial control system at this stage; rather, it
demonstrates how the operational data of the plant can be presented in a
clear, visual, and decision-supporting format.

The proposed interface is linked to the main logic of the simulation
model, where the plant consists of several connected operations such as
debeading, cutting, shredding, buffering, batching, pyrolysis, and
product separation. Since the reactor is the most critical unit in the
system and represents the main bottleneck, the application gives special
attention to reactor status, material level, temperature, humidity,
batch readiness, and maintenance needs.

2.  <span id="_Toc229301133" class="anchor"></span>**Application
    Objectives**

The main objective of the BioFuel mobile interface is to improve
operational visibility by allowing the user to monitor the plant
condition through a simple dashboard. The application also aims to
support faster decision-making by showing machine status, material
availability, reactor loading percentage, alerts, and basic production
reports.

The application concept supports the project by transforming simulation
and feasibility results into a practical monitoring idea. Instead of
presenting the plant only as a simulation model, the mobile interface
shows how the same operational logic can be used in a real industrial
environment for tracking, control support, and preventive maintenance
planning.

3.  <span id="_Toc229301134" class="anchor"></span>**General Dashboard
    Interface**

The first screen of the application is a general dashboard that
summarizes the overall status of the BioFuel plant. It provides a quick
view of daily capacity, system status, available material, active
alerts, and the condition of each major machine. The dashboard includes
the debeading machine, cutting machine, shredding machine, and pyrolysis
reactor.

For each machine, the interface displays the current operating
condition, such as Good, Bad, High Load, or Needs Maintenance. It also
presents the amount of material currently being handled, machine
temperature, humidity level, and operation load. This makes the
dashboard useful for identifying abnormal behavior before it causes
production delay.

<img src="../media/image22.png"
style="width:4.312in;height:3.29986in" />

<span id="_Toc229300394" class="anchor"></span>**Figure 16: General
Dashboard Interface.**

4.  <span id="_Toc229301135" class="anchor"></span>**Reactor-Specific
    Interface**

The second major screen is dedicated to the pyrolysis reactor. This
screen is important because the reactor controls the total throughput of
the system. The reactor interface shows the current material inside the
reactor, the required amount for a full batch, the remaining material
needed, reactor temperature, humidity, estimated time left, and
maintenance status.

The reactor screen also includes a circular batch-fill indicator. This
indicator shows the percentage of reactor loading and helps the operator
understand whether the reactor is still waiting for material, operating
under high utilization, or ready to start a new batch. Since one reactor
batch requires approximately 10 tons of material, the visual indicator
makes the batch condition easier to interpret.

<img src="../media/image23.png"
style="width:5.08133in;height:3.872in" />

<span id="_Toc229300395" class="anchor"></span>**Figure 17:
Reactor-Specific Interface.**

5.  <span id="_Toc229301136" class="anchor"></span>**Monitoring
    Parameters Included in the Application**

<span id="_Toc229300490" class="anchor"></span>**Table 26: Monitoring
Parameters Included in the Application.**

| Monitoring Element | Displayed Data                                  | Purpose                                                    |
|--------------------|-------------------------------------------------|------------------------------------------------------------|
| Machine Status     | Good, Bad, High Load, Needs Maintenance         | To identify operational problems quickly.                  |
| Material Level     | Current material quantity and required material | To track feeding and batching readiness.                   |
| Temperature        | Machine and reactor temperature                 | To monitor thermal condition and safety.                   |
| Humidity           | Humidity percentage around the process          | To support environmental and operating condition tracking. |
| Reactor Fill Level | Percentage of batch completion                  | To show whether the reactor is ready for operation.        |
| Alerts             | Critical warnings and maintenance notifications | To support preventive action and reduce downtime.          |
| Reports            | Daily, weekly, and monthly production summaries | To evaluate throughput, utilization, and profitability.    |

6.  <span id="_Toc229301137" class="anchor"></span>**Reports and Alerts
    Features**

The application includes a reports screen that presents simplified
operational results. The report can show daily, weekly, and monthly
summaries, such as processed material, completed batches, average
reactor utilization, and estimated net profit. This feature links the
operational side of the project with the economic feasibility analysis,
because production stability and reactor utilization directly affect
profitability.

The alerts screen provides warnings related to high reactor utilization,
shredding machine temperature, buffer accumulation, and maintenance
needs. Each alert can be marked as resolved, and the interface can
display suggested actions such as viewing the reactor screen or
generating a maintenance work order. This feature supports preventive
maintenance and reduces the risk of unplanned downtime.

<img src="../media/image24.png"
style="width:5.187in;height:3.13857in" />

<span id="_Toc229300396" class="anchor"></span>**Figure 18: Reports and
Alerts Features.**

7.  <span id="_Toc229301138" class="anchor"></span>**Interactive
    Features of the Prototype**

The prototype is designed to be more than a static screen. It includes
simple interactive functions such as refreshing live data, simulating
reactor filling, requesting maintenance, starting a batch when the
reactor is ready, filtering alerts, and switching between report
periods. These features demonstrate how a future full application could
help operators interact with plant data in real time.

8.  <span id="_Toc229301139" class="anchor"></span>**Added Value to the
    Project**

Adding the BioFuel mobile application concept improves the practical
value of the project. The original study evaluates the plant
technically, economically, and environmentally, while the application
adds an operational management layer. This means that the proposed
project is not only a feasible pyrolysis system, but also a system that
can be monitored and managed through a smart digital interface.

The application also strengthens the connection between simulation and
industrial implementation. The simulation identifies the reactor as the
main bottleneck, and the mobile interface translates this finding into a
practical monitoring feature by focusing on reactor load, temperature,
batch readiness, and maintenance condition. Therefore, the application
supports better process control, faster response to problems, and
improved operational reliability.

9.  <span id="_Toc229301140" class="anchor"></span>**Future Development
    of the Application**

In future work, the BioFuel interface can be developed from a front-end
prototype into a complete monitoring system. This can be achieved by
connecting the application to real sensors, machine controllers,
databases, and cloud dashboards. Temperature sensors, humidity sensors,
weight sensors, and machine status signals can provide live data to the
application.

A future version may also include artificial intelligence features, such
as predicting reactor downtime, recommending the best feeding strategy,
estimating product output, and warning the operator before machine
failure occurs. In this way, the application can become a smart
decision-support tool for waste tyre pyrolysis plant management.
