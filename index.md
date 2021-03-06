---
title       : Internet Tariff Calculator
subtitle    : Developing Data Products Project
author      : RRR
job         : Pricing Manager
framework   : io2012   # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Outline

1. Introduction
2. Application
3. Example

--- .class #id 

## Introduction

Network operators design their tariff rules so as to optimize the utilization of their network resources. A tariff comprises two components, namely,

1. `Fixed charge`. It is the monthly fee you pay for your connection to be available, and represents the cost you are charged due to the network resources the operator has to reserve in order to guarantee the contract obligations.

2. `Usage charge`. This cost component reflects the traffic volume you actually send to and receive from the internet. This charge depends on the amount of data, measured in `Giga Bytes`, you transfer on your internet channel.

As a customer, you are presented a set of tariff alternatives. These pricing options are designed to encourage users to select, in a self-interested way, their true `expected traffic volume`.
 

---
## Application

The application helps a customer to select an internet tariff. Using the max speed in Mbps (Mega bits per second) of the internet connection, the user can vary the mean rate of the channel so as to obtain,

1. The traffic `volume [GBytes/month]`, i.e. the amount of data, that can be transferred with an average speed of `mean [Mbps/month]`. A parameter called `utilization [hours/month]` is calculated as an indicator of the percentage of time the channel is used.

2. A plot that illustrates the existing dependency of the tariff with the `mean speed` of the channel, i.e. with the actual usage of the connection.

The application is available at <http://rromeror.shinyapps.io/Project>.

---  
## Example

Currently, a mobile operator can offer an LTE internet access with the following contract parameters: 10 GBytes/month, 150 Mbps max speed. 

If you try to guess the corresponding average rate with the tool, you will notice that with a mean rate of 0.2 Mbps, i.e 200 Kbps, you will have a volume of information per month,

```r
Traffic_volume <- paste(0.2*2628000/8000, "[GBytes/month]");Traffic_volume
```

```
## [1] "65.7 [GBytes/month]"
```
Which is 6.5 times higher than the proposed plan. This result means that you are actually using your channel less than 2.92 Hours/month. Although advertisements attempt to lure users with `super high speeds`, in reality, all users are confined to be in the region of the curve (see application) close to "zero", in other words, customers actually do operate at very low average bit rates.

 
