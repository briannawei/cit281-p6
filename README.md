## Project 6



### p6.js
```
/*
Name: Brianna Wei
Professor Phil Colbert
CIT 281
p6.js
*/


class Shape {
    constructor(
        sides = []
    ) {
        this.sides = sides;
    }

    perimeter() {
        return (this.sides.length) ? this.sides.reduce((a,b) => a + b) : 0
    }
}

// Test Shape Class
console.log(new Shape([5, 10]).perimeter());  // 15
console.log(new Shape([1, 2, 3, 4, 5]).perimeter()); // 15
console.log(new Shape().perimeter()); // 0


class Rectangle extends Shape {
    constructor(
        width = 0,
        length = 0
    ){
        super([length, width, length, width]);
        this.width = width;
        this.length = length;
    }

    area() {
        let areaOfRect = this.length * this.width;
        return areaOfRect
    }
}

// Testing Rectangle Class
console.log(new Rectangle(4, 4).perimeter());  // 16
console.log(new Rectangle(4, 4).area());  // 16
console.log(new Rectangle(5, 5).perimeter()); // 20
console.log(new Rectangle(5, 5).area()); // 25
console.log(new Rectangle().perimeter()); // 0
console.log(new Rectangle().area()); // 0



class Triangle extends Shape{
    constructor(
        sideA = 0,
        sideB = 0,
        sideC = 0
    ){
        super([sideA, sideB, sideC]);
        this.sideA = sideA;
        this.sideB = sideB;
        this.sideC = sideC;
    }
    area() {
        let s = ( (this.sideA + this.sideB + this.sideC) / (2) )
        return Math.sqrt(s * (s - this.sideA) * (s - this.sideB) * (s - this.sideC))
    }
}

console.log(new Triangle(3, 4, 5).perimeter());  // 12
console.log(new Triangle(3, 4, 5).area());  // 6
console.log(new Triangle().perimeter()); // 0
console.log(new Triangle().area()); // 0



function test(){
    const data = [ [3, 4], [5, 5], [3, 4, 5], [10], [] ];
    const firstIndexPerm = (new Shape([3,4]).perimeter()) * 2;
    const firstIndexArea = new Rectangle(3,4).area();
    const secondIndexPerm = (new Shape([5,5]).perimeter()) * 2;
    const secondIndexArea = new Rectangle(5,5).area();
    const thirdIndexPerm = new Shape([3,4,5]).perimeter();
    const thirdIndexArea = new Triangle(3,4,5).area();

    for (const element of data) {
        switch(element.length){
            case(2):
                console.log(`Rectangle with sides ${data[0].toString()} has a perimeter of ${firstIndexPerm} and area of ${firstIndexArea}`)
                console.log(`Square with sides ${data[1].toString()} has a perimeter of ${secondIndexPerm} and area of ${secondIndexArea}`)
                break;
            case(3):
                console.log(`Triangle with sides ${data[2].toString()} has perimeter of ${thirdIndexPerm} and area of ${thirdIndexArea}`)
                break;
            case(1):
                console.log("Shapes with 1 side unsupported")
                break;
            case(0):
                console.log("Shapes with 0 sides unsupported")
                break;
        }
    }
}

test()

```
