---
layout: post
title: "Finding Compute Expensive Visuals in Power BI – An End-to-End Guide"
date: 2025-07-20
categories: [Power BI, Microsoft Fabric Capacity Metrics App, Azure Log Analytics Workspace, Performance]
---

# Finding Compute Expensive Visuals in Power BI – An End-to-End Guide

This blog deals with a very specific problem end-to-end: how to find visuals which have been eating a lot of compute units in your Power BI/Fabric capacity. While there is a wealth of information available elsewhere in bits and pieces, this post providea a walkthrough with code snippets, making it easier for a capacity admin to pinpoint problematic visuals.

So, one fine morning you open up the Fabric Capacity Metrics app and you see a whopper of a spike in the utilization tab, or worse, the capacity is just sluggish one afternoon because it had to deal with one too many hefty interactive operations and now everything is just moving at snail's pace. 

Hopefully none of this has happened to you and you are just here because you believe in preventive maintenance and when you see a query use more than 5/10/20% of Base capacity on a P1/F64, you would rather investigate than ignoring it and hoping it goes away.

## What We'll Cover

- Identifying performance bottlenecks
- Using Fabric Capacity Metrics effectively  
- Code snippets for analysis
- Actionable steps for optimization
