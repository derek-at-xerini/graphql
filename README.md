
## server.js
Hello world example
```bash
curl -X POST -H "Content-Type: application/json" -d '{"query": "{ hello }"}' http://localhost:4000/graphql
```

Roll dice
```bash
curl -X POST -H "Content-Type: application/json" -d \
'{"query":"query RollDice($dice: Int!, $sides: Int) { rollDice(numDice: $dice, numSides: $sides) }","variables":{"dice":3,"sides":6}}' \
http://localhost:4000/graphql
```

## server2.js
Create message
```bash
curl -X POST -H "Content-Type: application/json" -d \
'{"query":"mutation CreateMessage($input: MessageInput) {  createMessage(input: $input) {    id  }}","variables":{"input":{"author":"andy","content":"hope is a good thing"}}}' \
http://localhost:4000/graphql
```

Update message
```bash
curl -X POST -H "Content-Type: application/json" -d \
'{"query":"mutation UpdateMessage($id: ID!, $input: MessageInput) {  updateMessage(id: $id, input: $input){ content, author } }","variables":{"id":"a5298cb557b4c1cffbef", "input":{"author":"derek","content":"hope is a good thing"}}}' \
http://localhost:4000/graphql
```

Get message
```bash
curl -X POST -H "Content-Type: application/json" -d \
'{"query":"query GetMessage($id: ID!) {  getMessage(id: $id){ content, author} }","variables":{"id":"a5298cb557b4c1cffbef" }}' \
http://localhost:4000/graphql
```