# Whitespace
## Indentation Type
There is Tabs or Spaces, then your Tab Size.
You choose whether to have your whitespace use Space or Tab characters.
Regardless of either, you must decide your 'Tab Size' which is how many spaces does the Tab represent.
Tab Size: 4 is a Tab character with the width of 4 spaces.
Spaces: 4 is how many Space characters are typed to represent the width of a Tab.
```
Indent Type: Spaces
Tab Size: 4
```

## Indentation Levels
3 level indentation is the most before you should extract into a seperate function
4 levels is okay as long as its object properties, array items, or the like being defined
while the containing object/array/etc is being used in some way on level 3

#### Example of Ideal
```typescript
export default class IndentationExample {

    constructor() {
        for (let i = 0; i < 2; i++) {
            console.log("This log line is on the 3rd indentation level");
            console.log("Probably shouldn't nest anymore code in this for loop without extracting it");
        }
    }

}
```
#### Example of Okay
```typescript
export default class IndentationExample {

    constructor() {
        for (let i = 0; i < 2; i++) {
            let ArrayDefinedOnLevel3 = [
                "Array",
                "items",
                "defined",
                "on",
                "level",
                "4",
            ]
            console.log(`Thats okay, not ideal, but like i guess if you have to\n${ArrayDefinedOnLevel3}`);

            let ObjectDefinedOnLevel3 = {
                Obj: "props",
                defined: "on",
                level: 4
            }
            console.log(`Same thing. Its okay if you have to or it doesnt improve nor ruin the readibility regardless of where it goes.\n${ObjectDefinedOnLevel3}`);
        }
    }

}
```
#### Example of "Not Gamer"
```typescript
export default class IndentationExample {

    constructor() {
        for (let i = 0; i < 2; i++) {
            let ArrayDefinedOnLevel3 = [
                "Array",
                "items",
                "defined",
                "on",
                "level",
                "4",
            ]
            for (let str of ArrayDefinedOnLevel3) {
                console.log(`Method Call on Level 4. This is one level too many.\n${str}`);
                for (let s of str.split("")) {
                    console.log(`Should've refactored while you were ahead. This is a log line on Level 5. Two levels too many.\n${s}`);
                }
            }
        }
        console.log(`If you're on level 3 and about to nest again, just immediately switch to writing a new function/method`);
    }

}
```
