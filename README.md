# winter-coding

### SQL
- [SELECT, GROUP BY, JOIN](https://spring-slipper-6a7.notion.site/SELECT-GROUP-BY-JOIN-287ab2a704964c31b04628193b1425a4)
- [Operators and Functions](https://spring-slipper-6a7.notion.site/Operators-and-Functions-6fe89bf2dd024e879e2ec16849d457b7)

`SELECT`  
  col `AS` col_alias  
`FROM` table table_alias    
`JOIN` table table_alias  
  `ON` join_condition  
`WHERE` select_condigion  
`GROUP BY` col     
  `HAVING` aggregate_condition  
`ORDER BY` col `ASC`, col `DESC`  
`LIMIT`  

### JavaScript
- [Basic JavaScript Syntax](https://spring-slipper-6a7.notion.site/Basic-JavaScript-Syntax-2337194a7b8c43b6adb901fd1e62f2dc)


### Algorithms

**Matrix Search**
```js
const dx = [1, -1, 0, 0];
const dy = [0, 0, 1, -1];

let nx = 0;
let ny = 0;

for (let i = 0; i < 4; i++) {
nx = x + dx[i];
ny = y + dy[i];

if (nx < 0 || nx > len - 1 || ny < 0 || ny > len - 1) continue;
}
```

**IsPrime**
```js
const isPrime = num => {
  if (num === 1) return false;
  if (num === 2 || num === 3) return true;
  for (let i = 2; i < Math.sqrt(num); i++) {
    if (num % i === 0) return false;
  }
  return true;
};
```

**combination**

```js
const getCombinations = (arr, cnt) => {
  if (cnt === 1) return arr.map(t => [t]);

  const collection = [];

  arr.forEach((cur, i) => {
    const rest = arr.slice(i + 1);
    const subCollection = getCombinations(rest, cnt - 1);
    const curCollection = subCollection.map(combination => [
      cur,
      ...combination,
    ]);
    collection.push(...curCollection);
  });

  return collection;
};

console.log(getCombinations([1, 2, 3, 4], 2));
```

**permutation**

```js
const getPermutations = (arr, cnt) => {
  if (cnt === 1) return arr.map(t => [t]);

  const collection = [];

  arr.forEach((cur, i) => {
    const rest = [...arr.slice(0, i), ...arr.slice(i + 1)];
    const subCollection = getPermutations(rest, cnt - 1);
    const curCollection = subCollection.map(permutation => [
      cur,
      ...permutation,
    ]);
    collection.push(...curCollection);
  });

  return collection;
};

console.log(getPermutations([1, 2, 3, 4], 2));
```

**DFS**
```
function DFS (starting vertex)
	Initialize an empty 'stack' and a 'visited'
	Add the starting vertex to the 'stack' and 'visited'
	While 'stack' is not empty:
		- Pop and store current vertex
		- Iterate through current vertex's adjacency list:
			- For each adjacency vertex, if vertex is unvisited:
				- Add vertex to 'visited'
				- Push vertex to 'stack'  
```

```js
function dfs(vertex, graph, visited = new Set()) {
  visited.add(vertex);
  console.log(vertex);

  graph.get(vertex).forEach(neighbor => {  // graph = new Map(...)
    if (visited.has(neighbor)) return;
    dfs(neighbor, visited);
  });
}
```

**BFS**
```
function BFS (starting vertex)
	Initialize an empty 'queue' end a 'visited'
	Add the starting vertex to the 'queue' and 'visited'
	While 'queue' is not empty:
		- Dequeue and store current vertex
		- Iterate through current vertex's adjacency list:
			- For each adjacency vertex, if vertex is unvisited:
				- Add vertex to 'visited'
				- Enqueue vertex
```

```jsx
function bfs(startVertex) {
	const visited = new Set([startVertex]);
	const queue = [startVertex];

	while (queue.length) {
		const vertex = queue.shift();
		console.log(vertex)

		graph.get(vertex).forEach(neighbor => {  // graph = new Map(...)
			if (visited.has(neighbor)) return;
			visited.add(neighbor)
			queue.push(neighbor)
		})
	}
}
```

