```js
import { writable } from "svelte/store";

export const originalData = [
  { id: 1, name: "John", age: 36, country: "England", options: "controls" },
  { id: 2, name: "Katy", age: 8, country: "Ireland", options: "controls" },
  { id: 3, name: "Mike", age: 65, country: "USA", options: "controls" },
];

const clonedData = [...originalData];

export const dataRows = writable(clonedData);
```
