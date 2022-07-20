# overprovisioner-with-proportional-autoscaler





Example 1: let’s assume that 30% of buffer capacity is required on a cluster with 5 x c5.9xlarge nodes / 180 cores.
•	5x c5.9xl = 5 * 36 cores = 180 cores.
•	30% of 180 cores = 54 cores.
•	One Pause Pod = 4 cores
•	(54/4 =13.5) 13.5 pods would be required to maintain 54 cores (30% buffer) worth of buffer capacity in a cluster with 180 cores.
How to adjust cluster-proportional autoscaler ?
•	Use "coresPerReplica". As the name indicate that Replica (of 4cpu here) needs to be added for every "x" amount of cores.
•	To maintain 30% of buffer capacity, for every 14 workload cores a dummy replica (of 4CPU here) needs to be added (14*30%=4.2 ~4 cores).
 
Example 2: let’s assume that 20% of buffer capacity is required on a cluster with 5 x c5.9xlarge nodes / 180 cores.
•	5x c5.9xl = 5 * 36 cores = 180 cores.
•	20% of 180 cores = 36 cores.
•	One Pause Pod = 4 cores
•	(36/4 =9) 9 pods would be required to maintain 36 cores (20% buffer) worth of buffer capacity in a cluster with 180 cores.
How to adjust cluster-proportional autoscaler ?
•	Use "coresPerReplica". As the name indicate that Replica (of 4cpu here) needs to be added for every "x" amount of cores.
•	To maintain 20% of buffer capacity, for every 20 cores a replica (of 4CPU here) needs to be added (20*20%=4 cores)
 
Example 3: let’s assume that 10% of buffer capacity is required on a cluster with 5 x c5.9xlarge nodes / 180 cores.
•	5x c5.9xl = 5 * 36 cores = 180 cores.
•	10% of 180 cores = 18 cores.
•	One Pause Pod = 4 cores
•	(18/4 =4.5) 4.5 pods would be required to maintain 18 cores (10% buffer) worth of buffer capacity in a cluster with 180 cores.
How to adjust cluster-proportional autoscaler ?
•	Use "coresPerReplica". As the name indicate that Replica (of 4cpu here) needs to be added for every "x" amount of cores.
•	To maintain 10% of buffer capacity, for every 40 cores a replica (of 4CPU here) needs to be added (40*10%=4 cores)
![image](https://user-images.githubusercontent.com/35518921/179904662-27203312-3c6b-4229-87e4-da23e9ad3a12.png)
