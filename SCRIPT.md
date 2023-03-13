# General Demo Script

[Neo4j Walk Through Demo Under 10 Minutes](https://www.youtube.com/watch?v=c2-cPzD8mRI)

Key messages:

- Neo4j Graphs make it easy to uncover insights that can be hidden with other types of databases
- Neo4j Graphs remove the "impedance mismatch" between how people understand data and how IT models it
- Neo4j Graphs can easily answer questions that are complex or difficult for other databases

Key steps in the demo:

- Use Bloom's `Show me a Graph` query to show (Bloom on Desktop or "Explore" in Workspace on Aura)
    - Easy to visualize a sample of your data
    - Immediately see "important" things (there will likely be a central node)
    - Easy to explore

- Clear the scene and show a specific analysis (stack overflow example below):
    - search for a node of interest (e.g. `User with display_name <tab> Ranjana `)
    - Right-click the node and expand all to see the user's questions
    - Right-click the question and expand all to see the answers and tags
    - Right-click the answer and expand all to see who provided it 

- Clear the scene and show some more analysis (stack overflow example below):
    - Search for the user Ranjana as above
    - Search for User with display_name Petyr
    - Command-click (or I think control-click on Windows) to select both users
    - Right-click one and choose "Path->shortest path" There will be an obvious path through the "neo4j" tag
    - As above, expand each of the Users' questions, answers, and find out that jose_bacoy has answered questions for both of them
    - Expand all for jose_bacoy to see that he has answered lots of questions

- Use Browser (or "Query" in Workspace on Aura) to show how simple and easy it is to understand the schema
    - Run the query `call db.schema.visualization` (switch to graph view if you get a tabular/textual view)
    - Observe how the resulting visual is understandable, even if you know nothing about data modeling

- Use Browser to answer a "graphy" kind of question
    - For example: who are the most active users?
    - What does "active" mean? It's about the most interactions (questions, answers, comments)
    - Think about how many joins a RDBMS would need
    - In Browser, run a query like this: `match (u:User)-[]-() return u, count(*) as cnt order by cnt desc limit 10` (note the brackets are completely optional, but make make it easier to understand the query)
    - Switch to tabular view to show top users (top should be cybersam)
    - point out the speed (on my Desktop, it started in 1ms and finished in 19ms)

- If you like, run a query that shows all of the connections between Ranjana and Petyr (from the bloom demo)
    - `match p=(r:User {display_name: "Ranjana Jha"})-[*1..6]-(x:User {display_name: "PetyrBaelish"}) return p`
    - depending on your memory config, making this longer than 6 could start to slow down. Both AuraDB Free and Desktop have some pretty tiny memory allocations by default.