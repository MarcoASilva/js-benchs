## ASSIGNMENTS

### object vs primitive
- Specs:
| Machine                   | Runtime | Runtime Version |
|---------------------------|---------|-----------------|
| MacBook Pro M1 (2022) 32GB| NodeJs  | 22.2.0          |

- Results (avg of 10 runs)
| Object    | Primitive |
|-----------|-----------|
| 452.252ms | 125.116ms |


#### code
- object
```javascript
const a = 1;

const object = {
    b: {
        c: {
            d: 1,
        },
    }
}

console.time("time took");
for (let i = 0; i < 100_000_000; i++) {
    object.b.c.d += i + a;
}
console.timeEnd("time took");
```

- primitive
```javascript
const a = 1;

let primitive = 0;

console.time("time took");
for (let i = 0; i < 100_000_000; i++) {
    primitive += i + a;
}
console.timeEnd("time took");
```