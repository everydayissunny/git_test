# CSE4110 Database System Project 2

## 1. Project Explanation

It is a project that builds a logical schema based on the schema created by project 1 and inquires about information by blowing query statements.

The database was built as a logical schema through mysql workbench, and a C++ program was created to query or generate desired information by sending a query written in mysql to this database.

## 2. Creating Data

I generated the data considering below conditions.

1) According to the client, studio or one-bedroom apartments must have at least one interior photo. Multi-bedroom apartments or detached houses should have at least one exterior photo and one floor plan each.
   
2) Deals must be conducted through agents. In other words, buyers and sellers cannot make deals directly with each other. This is a design feature of my database. Therefore, when a buyer or seller registers, an agent is assigned to them immediately.

3) The property can only be uploaded to the market by an agent, and the deal related to that property can only be participated in by that agent who uploaded it to the market. Therefore, when an 'available' property is registered, the buyer who is willing to buy that property is automatically connected to that agent responsible for that property.

### 3. Guidelines for Program Execution

  * Query Type 1-1
    
    Since there was a condition 'Mapo' in the main query(TYPE1), I interpreted this subquery to search for properties that satisfy this condition and are located in Mapo-gu.

  * Query Type 2-1

    In the main query(TYPE2), there was a condition '8 school districts', so I interpreted this subquery to search for properties satisfying this condition and located in the 8 school districts

  * Query Type 3-1

    Due to the limitations of the internally generated data, only up to 2 confirmations are possible (available k = 0, 1, 2).

  * Query Type 3-2

    Although it calculates the bottom 10% of agents, due to limitations in generated data by me, when the number of agents is less than 10, it's configured to output only one agent. 
    I interpreted it as outputting the number of agents equal to 10% of the total number of agents rather than 10% of the total number of agents who made deals in 2021.

  * Query Type 4

    Due to limitations in the generated data, agents who did not sell any properties in specific year are not included in the output image.

  * Query Type 4-2

    Due to limitations in the generated data, agents who did not sell any properties(all ‘available’ status)  prints ‘NULL’.

  * Query Type 6

    As mentioned before starting the '3. Query' part, in the database I designed, the 'agent' is fixed the moment a property is registered. Therefore, there's no need to update the selling agent and buyer's agent. 
