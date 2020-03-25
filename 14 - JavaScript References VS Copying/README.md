# JavaScript30 - 14 - JavaScript References VS Copying

---

- array를 copy하는 방법들

  - Array.prototype.slice()

  ```
    const team2 = players.slice();
  ```

  - Array.prototype.concat()

  ```
    const team3 = [].concat(players);
  ```

  - ES6 Spread

  ```
    const team4 = [...players];
    team4[3] = "heeee hawww";
    console.log(team4);

  ```

  - Array.prototype.from()

  ```
    const team5 = Array.from(players);
  ```

- object를 copy하는 방법들

  - Object.prototype.assign()

  ```
    const person = {
        name: "Wes Bos",
        age: 80
    };
    const cap2 = Object.assign({}, person, { number: 99, age: 12 });
  ```

  - JSON

  ```
    const dev2 = JSON.parse(JSON.stringify(person));
  ```
