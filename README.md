

Hello world example
```bash
curl -X POST -H "Content-Type: application/json" -d '{"query": "{ hello }"}' http://localhost:4000/graphql
```

Passing arguments
```bash

```

Roll dice
```bash
curl -X POST -H "Content-Type: application/json" -d \
'{"query":"query RollDice($dice: Int!, $sides: Int) { rollDice(numDice: $dice, numSides: $sides) }","variables":{"dice":3,"sides":6}}' \
http://localhost:4000/graphql
```