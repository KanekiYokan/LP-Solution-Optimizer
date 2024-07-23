# Data Files Overview

There are currently 23 data files.

These data files are the test problem sets IV to XIII and A to C in Table 1 of J.E. Beasley's "An algorithm for solving large capacitated warehouse location problems" European Journal of Operational Research 33 (1988) 314-325.

These test problems essentially (but see Appendix in the above paper) include the standard Akinc and Khumawala test problems for the capacitated warehouse location problem.

## Relationship Between Test Problem Set and Files

| Problem Set | Files               |
| ----------- | ------------------- |
| VII         | cap71, ..., cap74   |
| VIII        | cap81, ..., cap84   |
| IX          | cap91, ..., cap94   |
| X           | cap101, ..., cap104 |
| XIII        | cap131, ..., cap134 |
| A           | capa                |
| B           | capb                |
| C           | capc                |

## Data Files Format

The format of these data files is:

1. **Header:**

   - Number of potential warehouse locations (m)
   - Number of customers (n)

2. **Warehouse Information:**
   For each potential warehouse location \(i\) (i=1,...,m):

   - Capacity
   - Fixed cost

3. **Customer Information:**
   For each customer \(j\) (j=1,...,n):
   - Demand
   - Cost of allocating all of the demand of \(j\) to warehouse \(i\) (i=1,...,m)

For files capa, capb, and capc (which are large files) in order to save file space, a single data file is used to represent four test problems. The word 'capacity' in these files should be replaced by the appropriate numeric value from Table 1 of the above paper in order to generate each of the four problems in problem sets A, B, and C.

## Optimal Solutions

The value of the optimal solution for each of these data files is given in the file `capopt`.

## File Sizes

- The largest file is `capc` of size 1300Kb (approximately).
- The entire set of files is of size 5000Kb (approximately).

## Additional Information

A full listing of the problem areas covered by OR-library can be found in the file `info`.

- **FTP Access:** available at `mscmga.ms.ic.ac.uk`
- **WWW Access:** available at [http://mscmga.ms.ic.ac.uk/](http://mscmga.ms.ic.ac.uk/)

---

### Note

I added the optimal solutions to this package. For each problem, we have an optimal solution in the corresponding `.opt` file as follows: For each city (in order of appearance in the problem file) we denoted the facility it is connected to in the optimal solution.

Martin Hoefer, 2002

The data file `cap71.txt` is structured according to a specific format for the capacitated facility location problem. Here’s a breakdown of the file content based on the format you provided:

# File Example Format Breakdown

1. **First Line:**

   - Number of potential warehouse locations (m)
   - Number of customers (n)

2. **Next `m` Lines (one for each warehouse location):**

   - Capacity of the warehouse
   - Fixed cost of opening the warehouse

3. **Remaining Lines (one set of `m` values for each customer, repeated `n` times):**
   - For each customer:
     - Demand of the customer
     - Cost of allocating all of the demand of the customer to each warehouse (one cost per warehouse)

### Content of `cap71.txt`

#### First Line

```plaintext
16 50
```

- **Number of warehouse locations (m):** 16
- **Number of customers (n):** 50

#### Next 16 Lines (Warehouse Data)

Each line contains two values: capacity and fixed cost for each warehouse.

```plaintext
58268 7500.
58268 7500.
58268 7500.
58268 7500.
58268 7500.
58268 7500.
58268 7500.
58268 7500.
58268 7500.
58268 7500.
58268 0.
58268 7500.
58268 7500.
58268 7500.
58268 7500.
58268 7500.
```

- **Capacity of each warehouse:** 58268 (for all warehouses)
- **Fixed cost for each warehouse:** Mostly 7500, except for one warehouse which has a fixed cost of 0.

#### Remaining Lines (Customer Data)

Each block of lines represents the data for a single customer. Each customer block contains 16 values, one for each warehouse, indicating the cost to allocate the customer's demand to that warehouse.

```plaintext
146
6739.72500 10355.05000 7650.40000 5219.50000 5776.12500 6641.17500 4374.52500
3847.10000 6429.47500 5396.52500 5219.50000 4182.90000 7391.25000 5038.82500
10349.57500 6051.70000

87
3204.86250 5457.07500 3845.40000 2396.85000 2628.48750 3220.08750 1838.96250
2266.35000 3117.86250 2582.81250 2296.80000 1779.15000 5115.60000 2189.13750
5399.43750 2838.37500

672
4914.00000 26409.60000 19622.40000 13876.80000 9147.60000 14977.20000 21848.40000
35330.40000 15111.60000 23679.60000 9828.00000 19303.20000 57472.80000 11180.40000
22957.20000 15489.60000

1337
32372.11250 29982.22500 21024.32500 29681.40000 21275.01250 20071.71250 64292.98750
80186.57500 25921.08750 69206.46250 23096.67500 48700.22500 135170.70000 40527.81250
60515.96250 52911.77500
```

- **First value in each block:** Demand of the customer.
- **Following 16 values:** Cost of allocating all demand of the customer to each warehouse.

#### Example Breakdown for the First Customer

```plaintext
146
6739.72500 10355.05000 7650.40000 5219.50000 5776.12500 6641.17500 4374.52500
3847.10000 6429.47500 5396.52500 5219.50000 4182.90000 7391.25000 5038.82500
10349.57500 6051.70000
```

- **Demand:** 146
- **Costs to allocate demand to warehouses:**
  - Warehouse 1: 6739.72500
  - Warehouse 2: 10355.05000
  - Warehouse 3: 7650.40000
  - Warehouse 4: 5219.50000
  - Warehouse 5: 5776.12500
  - Warehouse 6: 6641.17500
  - Warehouse 7: 4374.52500
  - Warehouse 8: 3847.10000
  - Warehouse 9: 6429.47500
  - Warehouse 10: 5396.52500
  - Warehouse 11: 5219.50000
  - Warehouse 12: 4182.90000
  - Warehouse 13: 7391.25000
  - Warehouse 14: 5038.82500
  - Warehouse 15: 10349.57500
  - Warehouse 16: 6051.70000

This pattern repeats for all 50 customers.

### Summary

- **Total number of warehouse locations:** 16
- **Total number of customers:** 50
- **Warehouse data:** 16 lines, each with capacity and fixed cost
- **Customer data:** For each customer, demand followed by the cost to allocate demand to each warehouse
