# Traffic Flow Optimization System Using Graph Theory

## Overview

The Traffic Flow Optimization System is a C++ based simulation project designed to model and optimize traffic flow in an urban road network.

The system represents the city road network as a directed graph and simulates vehicle movement, road congestion, queues at intersections, traffic signals, and dynamic route selection.

The main goal is to reduce traffic congestion and overall travel time by dynamically adapting routes and traffic signals according to the current traffic conditions.

## Features

* Models an urban road network using a directed graph
* Simulates multiple vehicles moving through the network
* Supports multiple traffic sources and destinations
* Models road congestion and vehicle queues
* Calculates congestion-aware travel times
* Uses Dijkstra's algorithm for shortest-path routing
* Dynamically selects routes based on current traffic conditions
* Implements queue-based adaptive traffic signals
* Updates traffic conditions at every simulation step
* Records traffic performance metrics
* Minimizes congestion, delay, and overall travel time

## System Model

The road network is represented as a directed graph:

G = (V, E)

Where:

* V represents intersections or nodes
* E represents roads or edges

Each road contains information such as:

* Road length
* Maximum speed
* Road capacity
* Number of vehicles currently on the road
* Number of vehicles waiting at the downstream intersection
* Current travel time

## Traffic Simulation

The system operates using discrete simulation time steps.

At every simulation step:

1. Vehicle arrivals are updated.
2. Road traffic and congestion are recalculated.
3. Travel times are updated.
4. Optimal routes are calculated.
5. Traffic signals are adjusted.
6. Vehicle movement and queues are updated.
7. Performance metrics are recorded.

This process continues to simulate traffic behavior over time.

## Congestion Model

The congestion level of a road is calculated using:

ρ = f / c

Where:

* f = number of vehicles currently on the road
* c = maximum capacity of the road
* ρ = congestion level

A value close to 0 represents a relatively free road, while a value close to 1 represents a highly congested road.

## Travel Time Model

Travel time increases as congestion increases.

The system uses a nonlinear congestion-based model:

w(t) = w_free (1 + α(f(t)/c)^β)

Where:

* w(t) = current travel time
* w_free = travel time under free-flow conditions
* α = congestion sensitivity factor
* β = nonlinearity factor
* f(t) = current traffic on the road
* c = road capacity

The free-flow travel time is calculated using:

w_free = l / v_max

Where:

* l = road length
* v_max = maximum allowed speed

## Vehicle Model

Each vehicle maintains information about:

* Source
* Destination
* Current road
* Remaining travel time
* Current status

The vehicle can have one of three states:

* Moving
* Waiting
* Arrived

When a vehicle enters a road, its remaining travel time is initialized according to the current congestion level of that road.

## Dynamic Routing

Vehicles dynamically select routes according to the current traffic conditions.

The cost of an edge is its current travel time:

cost(e) = w(t)

Dijkstra's algorithm is used to calculate the shortest path from the vehicle's source to its destination.

This allows vehicles to avoid highly congested roads whenever a faster alternative route is available.

## Adaptive Traffic Signals

Traffic signals control the movement of vehicles at intersections.

For each incoming road:

* Green signal = 1
* Red signal = 0

The system gives the green signal to the incoming road with the longest queue.

At a given intersection, only one incoming road is allowed to move at a time.

Vehicles on the green road can proceed, while vehicles on red roads remain in queues.

The signal can remain active for a fixed number of simulation steps or until the queue falls below a defined threshold.

## Queue Model

Vehicles reaching an intersection may have to wait because of:

* Red traffic signals
* Congestion on the next road
* Limited road capacity

The queue is updated during every simulation step.

This allows the system to model realistic traffic buildup and discharge at intersections.

## Optimization Objective

The main objective of the system is to minimize traffic congestion and delay throughout the road network.

The optimization considers:

* Queue lengths
* Road congestion
* Vehicle travel time
* Overall traffic flow

The system aims to improve traffic movement while maintaining computational efficiency.

## Performance Metrics

The system evaluates traffic performance using:

### Average Travel Time

Measures the average time required by vehicles to reach their destinations.

### Total Delay

Measures the additional travel time experienced by vehicles compared to free-flow conditions.

### Throughput

Measures the number of vehicles reaching their destinations per unit of time.

### Average Congestion Level

Measures the average utilization of roads throughout the network.

## Algorithms and Data Structures

The project focuses on the practical use of data structures and algorithms, including:

* Graph representation
* Directed graphs
* Shortest-path algorithms
* Dijkstra's algorithm
* Queues
* Dynamic traffic state updates
* Vehicle and road data management

## Technologies Used

* C++
* Data Structures
* Algorithms
* Graph Theory
* Dijkstra's Algorithm
* Mathematical Modelling
* Traffic Simulation

## System Workflow

```text
              Start Simulation
                     |
                     v
             Generate Vehicles
                     |
                     v
          Update Traffic Flow
                     |
                     v
          Calculate Congestion
                     |
                     v
         Calculate Travel Times
                     |
                     v
          Find Optimal Routes
          (Dijkstra Algorithm)
                     |
                     v
        Update Traffic Signals
                     |
                     v
          Move Vehicles / Queues
                     |
                     v
         Record Performance Data
                     |
                     v
              Next Time Step
                     |
                     +-------> Repeat
```

## Project Objective

The project demonstrates how graph theory, data structures, algorithms, and mathematical modelling can be combined to develop a simulation-based traffic management system.

By continuously updating traffic conditions and adapting vehicle routes and traffic signals, the system aims to reduce congestion, minimize travel time, and improve overall traffic flow.

## Project Information

**Project:** Traffic Flow Optimization System Using Graph Theory

**Language:** C++

**Difficulty Level:** Full

**Team Size:** Up to 3 Members

**Core Skills:** C++, Data Structures, Algorithms, Graph Theory
