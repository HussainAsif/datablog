---
layout: post
title: "Finding Compute Expensive Visuals in Power BI"
subtitle: "An End-to-End Guide"
date: 2025-01-19
categories: [Power BI, Microsoft Fabric Capacity Metrics App, Azure Log Analytics Workspace, Performance]
---

# Finding Compute Expensive Visuals in Power BI – An End-to-End Guide

This article deals with a very specific problem. How to find visuals which have been eating a lot of compute units in your Power BI/Fabric capacity.

While there is a wealth of information available elsewhere in bits and pieces, this post provides a walkthrough with code snippets, making it easier for a capacity admin to pinpoint problematic visuals.

So, one fine morning you open Fabric Capacity Metrics app and see a whopper of a spike in the utilisation tab, kind of like below, or worse, the capacity is sluggish one afternoon because it had to deal with one too many hefty queries and now it is in the state of interactive delay. While capacity slowly recovers (maybe/hopefully!) you might be sitting there wondering how on earth did one query to a dataset in a dev environment eat up 10% or more of the base capacity.

Before you judge me for assumptions like having production and dev workloads in the same capacity, and not benchmarking compute usage for visuals in dev, bear in mind that in the real world, not all organisations are made of money (to afford multiple capacities) and not all PBI devs have had the chance to cry themselves to sleep while reading the tomes from the italians.

But, lets keep it cheerful and assume that none of the above has happened to you and you are just here because you believe in preventive maintenance and when you see a query use more than 5/10/20% of Base capacity on a P1/F64, you would rather investigate than hoping it goes away.

## Pre-requisites

- Access to Fabric Capacity Metrics App
- Azure Log Analytics Workspace is setup and attached to workspace containing semantic models
- Fabric item creation is enabled
- Access to workspaces containing reports and semantic models

## What We'll Cover

- Picking suitable targets from Fabric Capacity Metrics App
- Identifying Reports and Visuals from Azure Log Analytics Workspace
- Building a Report and Visuals catalog
- Navigating to problematic visuals


