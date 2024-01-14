Implementation of Sequential and Parallel BFS using CUDA C++
The sequential implementation of Breadth-First Search (BFS) is straightforward but less effective for large graphs, making the parallel approach more advantageous. In Parallel BFS, we used shared memory to manage queues, the kernel initializes the process by marking the starting node as visited and adding it to the current queue. The main processing loop operates in parallel, with each thread handling a subset of nodes and exploring their neighbors. Unvisited neighbors are marked as visited and added to the next queue. Synchronization is achieved through shared memory and atomic operations, ensuring accurate queue updates. The algorithm iterates until all nodes are processed, taking advantage of GPU parallelism for faster BFS traversal on large graphs.

To run the code: nvcc project.cu -o project
                 ./project
