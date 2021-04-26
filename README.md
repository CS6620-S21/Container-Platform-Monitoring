# Container-Platform-Monitoring

** **

## 1. Vision and Goals Of The Project

* Container platforms (Kubernetes, OpenShift, Cloud Foundry) enable fast, flexible architectures for deploying modern applications and services. The goals of this project are to identify and implement monitoring best practices in the container platform.
* The team will start by developing a list of requirements, then identifying options for tools to use. They will deploy a kubernetes platform and an application on it, then apply the monitoring tool(s) using an iterative approach to see what works and what doesn't. It will be a very hands on project. Work will be done using CONS3RT and the Mass Open Cloud resources. The vision is to have a system with:
    * Real time monitoring to identify issues proactively to avoid system outages. 
    * Track operations and status of different components of containerized platforms
    * Ensure optimal performance in modern microservice architectures.
    * Constantly monitors all services and collects metrics to ensure applications running on containers are performing properly.
    * Identifies problems before it propagates through the whole system. In alerts when any services crashes.


** **

## 2. Users/Personas Of The Project

* Devops engineers
* System administrators
* Software Developers

** **

## 3. Scope and Features Of The Project

* Collect and store logs from the various applications running across multiple containers.
* Enable querying of logs for custom conditions desired by the devops team and setup alerts.
* Strengthen the container to withstand possible security threats.
* Enable Container management and monitoring from dashboard. 


** **

## 4. Solution Concept

Container platform monitoring system will consist of 3 main components:
1. **Metrics Collector**
2. **Metrics Processor**
3. **HTTP Server**

#### Metrics Collector
   * Metric collector is responsible for retrieving different metrics from container platforms.
   * It will leverage different apis exposed by container platforms.
   * IT will pull below metrics
        * Memory Usage
        * CPU usage
        * Memory limit
        * Number of exceptions
        * Number of requests
        
#### Metrics Processor

   * Metrics fetched by a metrics collector are processed in real time by the metrics processor.
   * Metrics processors will analyze collected metrics in real time to determine if an application is meeting expected goals.
   * If an application metrics is not meeting goals, the processor will send configured alerts.
   * Processor will build time series reports like number of requests per seconds, number of errors per second.
   * Metrics processor stores metrics/logs if necessary.
   
![](https://imgur.com/bf0dK38.png)

#### HTTP Server

   * This is the only component exposed to the outer world.
   * Time series data or metrics analysis done by the processor can be retrieved by making HTTP calls to the HTTP server.
   * User configures alarm conditions using HTTP server.
   
#### We will be working on technologies: 
   * CONS3RT
   * Docker
   * Podman
   * Kubernetes

** **   

## 5. Architecture 

   * Prometheus server
   * Prometheus Exporteer
   * Prometheus UI
   * Grafana
   * Alert Manager

![alt text](https://drive.google.com/file/d/1kT7OaS5HlpZ-x8Si9J-zRfXGAWyJDJSg/view?usp=sharing)

** ** 
   
## 6. Acceptance criteria

   * A system which identifies issues with containers which could lead to system failures.
   * The System Monitors different functions and operations performed by the containerized platform.
   * The system helps in having the platform perform satisfactorily by collecting metrics and monitoring various services running on it.
   * The system catches and warns about any problems before the entire system is affected by it.

** ** 

## 7.  Release Planning:

   **Sprint 1:** Setup container platform and deploy applications on it. <br>
   **Sprint 2:** Investigate APIS or log collector technologies (fluentd). <br>
   **Sprint 3:** Integrate fluentd. <br> 
   **Sprint 4:** Analyse logs/metrics in real time and store in Kibana. <br>
   **Sprint 5:** Show aggregated analysis of logs to the user. <br>
   **Sprint 6:** Trigger alerts/alarms when a goal condition is not met. <br>
 

** **
