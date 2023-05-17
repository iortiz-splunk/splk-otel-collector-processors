---
title: 3. OTel Collector Processors
weight: 2
description: Provide a description of OTel Collector Processors 
---

## OpenTelemetry Collector Distributions

Before digging into the collectors' processors we need to discuss about the different distributions of the OTel Collector. There are two official distributions of the collector: 

- [opentelemetry-collector](https://github.com/open-telemetry/opentelemetry-collector): This is the core repository that only contains the most crucial components 
- [opentelemetry-collector-contrib](https://github.com/open-telemetry/opentelemetry-collector-contrib): This repository contains most of the core and all additional available components.

It is encouraged that each user builds their own distrubition using the components that they need from either repository or custom built components. 
</br>  


## Splunk OpenTelemetry Collector Distribution 

The Splunk Distribution of OpenTelemetry Collector is a distribution of the OpenTelemetry Collector. The distribution is a project that bundles components from OpenTelemetry Core, OpenTelemetry Contrib, and other sources to provide data collection for multiple source platforms. The customizations in the Splunk distribution include these features:

- Better defaults for Splunk products
- Fluentd for log capture
- Tools to support migration from SignalFx products

It is important to understand which distribution of the OTel Collector is being used as components may or may not be available. To see a list of all the components available in the Splunk distribution see [Splunk OTel Components](https://docs.splunk.com/Observability/gdi/opentelemetry/components.html#otel-components)


## Processors

As described before, procesors allow you to modify the data flowing through the OTel Collector via a YAML configuration. In this workshop we will go over the configuration of some of the most commonly used processors available within the Splunk distribution of the OTel collector: 

- [Filter Processor](): We will use this to drop specific metrics 
- [Resource Processor](): We will use this to add and remove attributes from our metrics
- [Transform Processor](): 
- [Tail Sampling Processor](): We will use this processor to filter out spans that are 

## Memory Limiter 

The [memorylimiterprocessor](https://github.com/open-telemetry/opentelemetry-collector/blob/main/processor/memorylimiterprocessor/README.md) limits the amount of memory consumed by the OTel Collector when processing data. The processor perform periodic checks of memory usage; if it exceeds defined limits it will begin refusing data and forcing GC to reduce memory consumption. 

It is highly recommended to configure ballastextension as well as the memory_limiter processor on every collector. We won't go in depth regarding this processor, but it is important to understand how it works in order to properly size a collector

