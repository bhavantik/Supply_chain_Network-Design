# Supply chain Network Design to satisfy customer demand with Minimum Shipping cost
- In this Project, we have to minimize shipping costs to satisfy known customer demand from the direct
manufacturer or Depot with known transportation costs using GUROBI optimizer.

## Objective
-  Given a set of factories, depots, and customers, the goal is to determine how to satisfy customer demand while minimizing shipping costs.

## Problem Description

In this problem, we have six end customers(C1,C2,C3,C4,C5,C6), each with a known demand for a product.  Customer demand can be satisfied from a set of four depots(Newcastle, Birmingham, London, Exeter), or directly from a set of two factories(Liverpool, Brighton).  
Each depot can support a maximum volume of product moving through it, and each factory can produce a maximum amount of product.  There are known costs associated with transporting the product, from a factory to a depot, from a depot to a customer, or from a factory directly to a customer.

Our supply network has two factories, in Liverpool and Brighton, that produce a product.  Each has a maximum production capacity:

| Factory | Supply (tons) |
| --- | --- |
| Liverpool | 150,000 |
| Brighton |  200,000 |

The product can be shipped from a factory to a set of four depots.  Each depot has a maximum throughput.  Depots don't produce or consume the product; they simply pass the product on to customers.

| Depot | Throughput (tons) |
| --- | --- |
| Newcastle | 70,000 |
| Birmingham | 50,000 |
| London | 100,000 |
| Exeter | 40,000 |

Our network has six customers, each with a given demand.

| Customer | Demand (tons) |
| --- | --- |
| C1 | 50,000 |
| C2 | 10,000 |
| C3 | 40,000 |
| C4 | 35,000 |
| C5 | 60,000 |
| C6 | 20,000 |

Shipping costs are given in the following table (in dollars per ton).  Columns are source cities and rows are destination cities.  Thus, for example, it costs $1 per ton to ship the product from Liverpool to London.  A '-' in the table indicates that that combination is not possible, so for example it is not possible to ship from the factory in Brighton to the depot in Newcastle.

| To | Liverpool | Brighton | Newcastle | Birmingham | London | Exeter |
| --- | --- | --- | --- | --- | --- | --- |
| Depots |
| Newcastle  | 0.5 |   - |
| Birmingham | 0.5 | 0.3 |
| London     | 1.0 | 0.5 |
| Exeter     | 0.2 | 0.2 |
| Customers |
| C1 | 1.0 | 2.0 |   - | 1.0 |   - |   - |
| C2 |   - |   - | 1.5 | 0.5 | 1.5 |   - |
| C3 | 1.5 |   - | 0.5 | 0.5 | 2.0 | 0.2 |
| C4 | 2.0 |   - | 1.5 | 1.0 |   - | 1.5 |
| C5 |   - |   - |   - | 0.5 | 0.5 | 0.5 |
| C6 | 1.0 |   - | 1.0 |   - | 1.5 | 1.5 |

**Question:** The question to be answered is how to satisfy the demands of the end customers while minimizing shipping costs.
  
 ## Python Code with Gurobi Python API
 - Above given file represent solution of given problem.
   


## Reference
- This model is example 19 from the fifth edition of Model Building in Mathematical Programming, by H. Paul Williams on pages 273-275 and 330-332.
