<img height=250 width=auto src="https://user-images.githubusercontent.com/90899789/180600941-107a6877-f443-498d-8e64-d5dc6b9aa82d.png">

### Prelude
Tests are inevitable to continuous integration and continuous delivery. Writing tests in ESM JavaScript with top-level async/await can be tricky. Especially in the case where we might want to maintain a sequence of tests. The implementation is more of a concept, than an attempt replace `mocha` or `jest` or `AVA`.

A simple test suite:
```ts
const $ = new Suite('Math')

$.it('adds', _ => expect(2+1).equals(3))

await $.it('adds async', async _ => {
  const req = await fetch('http://api.mathjs.org/v4/?expr=1%2B2')
  const result = await req.text()
  expect(result).equals('3')
})

$.done()
```

### Features
- Simplicity
- Simplicity
- Simplicity
- Works for pure ESM TypeScript
- Batteries included i.e. `expect` is provided with plugins:
  - chai-http
  - chai-array
  - chai-sorted, etc
