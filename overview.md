 - Need for Parallel 
   - Single thread performance increases slowly-> moores law
   - Several application domains require much computing power than a single processor can provide. (simulation, ML training, BigData problems)

 - Perfromance:
   - execution time
   - FLOPS
   - CPI
   - speedup
   - Efficiency
   - Scalability (strong/weak, amdahls law)
   - notes

    - Performance challanges
      - Idle time / Load imbalance / Efficiency ->  Dynamic scheduling / Work stealing
      - I/O operations
      - Task Dependencies -> DAG / task level / maximum width / critical path

 - Parallel Architectures and Programming Models 
    - Flynn's taxonomy:
      - SISD, MISD, SIMD, MIMD
      - SIMD -> same inst broadcast to all ALUs. Limitation -> Adapted to very regular processing
      - SIMD performance branching
      - Many MIMD architectures include SIMD sub-components

    - Programming Models:
      - Shared memory (Threads/processes communicate by running operations in a shared memory space)
      - Message passing (Threads/processes communicate by sending and receiving messages)
      - Data parallelism *
    
    - Programming model vs communication abstraction:
      - The programming model is independent of the underlying communication architecture. (Message passing over shared memory is possible and vice-versa)
      - Note that a shared memory system is ultimately a message passing system (A network interconnects the processor cores and the memory controllers)
      - Hybrid architectures (cluster of nodes) and applications (MPI between nodes, OpenMP within node)

    - Data parallelism*:
      - functions (transformation) to be applied on all the data (MapReduce)
      - popular approach to process large amount of data
      - Benefits
      - ata parallelism can be implemented on top of shared memory and message passing (most common) communication systems

    - SPMD:
      - A SPMD application could (theoretically) be translated into a single stream of SIMD instructions.
    
    - MPMD:
      - Master-worker or Workflow of tasks

