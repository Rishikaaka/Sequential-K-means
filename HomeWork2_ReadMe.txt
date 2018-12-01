Compilation:
mpicc -o HomeWork2 CS5331_HomeWork2_Sequential_Rishika_Ghazanfar.c


Execution:
mpirun -np 1 HomeWork2


-This homework uses initial constructs of MPI however, it is still sequential version and MPI part is work in progress.

-Data generation:
Every processor is assumed to generate its own data by mapping seed according to total number of data points and available processors. Here it is assumed that 4 processors and 10000 data points.

-constructing k-means build_K_means: 
K centroids are constructed using interface: build_K_centroids(dim, proc_data, data, K, centroids);
 

- K-mean clusters are computed using interface:
  kmean(data, dim, proc_data, K, cluster_assign, centroids, cluster_size, cluster_radius);
  
- Query point: Two kinds of query points are supported:
i) Using Query point out of data set:
 
  double query_point[128] = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17,
          18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34,
          35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51,
          52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68,
          69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85,
          86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 10, 11, 22,
          33, 44, 55, 66, 77, 88, 99, 10, 11, 12, 13, 14, 15, 16,
          17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27};
		
  
ii) get a random number from the data set

kmean_search(query_point, data, dim, proc_data, K, cluster_assign, centroids, cluster_size, cluster_radius, nearest_point);
  

- Printing Query point:
printf("\n*********** Q U E R Y          P O I N T ***********\n");
  
  for (i = 0; i < dim; i++)
	printf (" %.0lf ",query_point[i]);
		
  printf("\n");

- Printing Nearest Point:
  	
  printf("\n*********** N E A R E ST        P O I N T ***********\n");
  
  for (i = 0; i < dim; i++)
	printf (" %.0lf ",nearest_point[i]);
		
  printf ("\n");
  