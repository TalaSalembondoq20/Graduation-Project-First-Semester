# Simulation Model Description

## Model Type

The project uses a discrete-event simulation model developed in Simio to represent the waste tyre pyrolysis process as an industrial production system.

## Process Flow

The modeled process follows this sequence:

Waste Tyre Arrival → Debeading → Cutting → Splitting into Four Pieces → Shredding → Buffering → Batch Formation → Pyrolysis Reactor → Product Separation → Final Product Streams

## Main Entities

The primary entity is the waste tyre. After cutting, each tyre is divided into four pieces. These pieces continue through shredding, buffering, batching, and reactor processing.

## Main Model Objects

The simulation model uses the following object types:

- Source
- Server
- Buffer / Queue
- Combiner
- Separator
- Sink

## Main Bottleneck

The pyrolysis reactor is the main bottleneck because it operates as a batch-processing unit with a long processing time of approximately 18 to 23 hours per batch.

## Key Performance Indicators

The simulation model evaluates:

- Throughput
- Reactor utilization
- Machine utilization
- Queue size
- Waiting time
- Buffer level
- Completed batches
- Bottleneck location
- System stability
