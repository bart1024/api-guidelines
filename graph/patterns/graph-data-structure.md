TODO do you want to describe different representations of graphs?
TODO do you want to call out a tree specifically?


# Graph data structure

Microsoft Graph API Design Pattern

*A graph is a data structure that represents the many-to-many relationships between nodes.
Note that a tree is just an acyclic directed graph and should be modeled accordingly.*


## Problem

Clients may have a need to represent dynamic relationships between their data.
In these cases, the relationships themselves becomes part of the client data, and need to be modeled to show both the data being related and the relationships between the data.

## Solution

A graph is represented by its nodes, each of which navigate to its related nodes.
Each node has its own value:
```
<EntityType Name="node">
  <Property Name="data" Type="..." />
  <NavigationProperty Name="subnodes" Type="self.node" ContainsTarget="false" />
</EntityType>

<EntityContainer Name="container">
  <EntitySet Name="nodes" EntityType="self.node" />
</EntityContainer>
```

Generally, more specific naming is desired. 

## When to use this pattern

*Describe when and why the solution is applicable and when it might not be.*

## Issues and considerations

*Describe tradeoffs of the solution.*

## Example

*Provide a short example from real life.*
