# eGA3
### Simulator of the eGA3 address assignment implemented in Python
#### About
#
   * The simulator executes the eGA3 protocol on all hierarchical topologies located in the directory you indicate, likewise these topologies must have the following format:
    - $topJAC <- always
    - duplex-link 
    - Source:
      - Switch: $n("Hier_src"s"Pos_src"): where Hier_src is the source level and Pos_src is the position on the level, e.g. $n(0s0)
    - Destination
      - For switch: $n("Hier_dst"s"Pos_dst"): where Hier_dst is de destination level and Pos_des is the position on the level, e.g. $n(1s7)
      - For host: $n(h"num_host): where h indicate host and num_host is de number of host, e.g. $n(h155)
   * The results show the HLMAC address assignment for all nodes

#### Use
#
```sh
            ./etoriiAddressAssign.py
            Subdirectory name topologies:
```
### Topology Builder
#### About
#
   * It generates as many hierarchical topologies files as we want, after introducing the following parameters: 
    - Number of Topologies.
    - Number of Hierarchical levels [nL: 2..9]:
    - Number of nodes at level-> X: 
    - Number of links down from level-> X:
    - Number of Host:
   * It produces several files, each one containing one topology

#### Use
#
```sh
            python genHierarchicalTopology.py   

            Builds arbitrary datacenter topologies:
                [1] Hierarchical
            
            Select[1, [0 to abort]]: 1 
            
            Builds T arbitrary hierarchical DC topologies of nL levels of switches,
            nLi nodes at level Li, lLi links between level Li and Li+1
            nH hosts (end systems) single connected to a nLth level switch
            -----------------------------------------------------------------------
            Number of Topologies [nT: 1..100]: 
            Number of Hierarchical levels [nL: 2..9]: 
            Number of nodes at level-> 0 [nL0: 1..1000]: 
            Number of nodes at level-> 1 [nL1: 1..1000]: 
            Number of nodes at level-> 2 [nL2: 1..1000]: 
            Number of links down from level-> 0 [dlL0: 16..2000]:
            Number of links down from level-> 1 [dlL0: 16..2000]:
            Number of links down from level-> 2 [dlL0: 16..2000]:
```
### Painter Topologies
#### About
#
   * It gets two parameters from a topology file, which can be generated by the generator. The parameters are:
    - Nodes: represented by circles.
    - Links: represented by lines ranging from a source node to a destination node
   * The result is four files: a PNG, a PDF, EPS and SGV, all of them containing the representation of the topology in different formats

#### Use
#
```sh
            python pintar_topologia.py 
```
