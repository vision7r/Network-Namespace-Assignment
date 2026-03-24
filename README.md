# Linux Network Namespace Simulation Assignment

## Project Overview
এই প্রজেক্টে আমরা Linux Network Namespaces ব্যবহার করে দুইটা আলাদা নেটওয়ার্ক তৈরি করেছি এবং একটা Router Namespace দিয়ে তাদের মধ্যে রাউটিং সেটআপ করেছি।

## Topology Diagram
Network 1 (10.0.1.0/24)          Network 2 (10.0.2.0/24)
ns1                               ns2
10.0.1.10                       10.0.2.10
|                                 |
veth-ns1                         veth-ns2
|                                 |
br0                              br1
|             router-ns            |
veth-br0-r                     veth-br1-r
10.0.1.1                       10.0.2.1   

## IP Addressing Scheme
ns1: 10.0.1.10/24 (Default Gateway: 10.0.1.0)
ns2: 10.0.2.10/24 (Default Gateway: 10.0.2.0)
router-ns:
  - veth-r0: 10.0.1.1/24
  - veth-r1: 10.0.2.1/24

## Components Used
- Bridges: br0, br1
- Namespaces: ns1, ns2, router-ns
