# Swift

## Types

- Int ⇒ Intergers ou números inteiros
- Float ⇒ Decimais com precisão de 6 casas decimais
- Double ⇒ Decimais com precisão de 15 casas decimais
- String ⇒ Nomes, palavras, frases…
- Bool ⇒ Booleano → True/False

```swift
var isInt: Int = 10
var isFloat: Float = 10.45
var isDouble: Double  = 10.4653735487345737
var isString: String = "Gabriel" 
var isBool: Bool = true  // or false
```

## Variables

- Capture value
    - variable → value can be changed ⇒ var
    - constant → value cannot be changed (bc it’s a constant…) ⇒ let

```swift
var name = "Gabriel"
name = "André"

let age = 19
age = 21 // Cannot change 

```

## Array

- Container/List of objects
- Ordered
- Duplicates

![Untitled](Swift%203d54a866c8ff44cda641b17665ea2c24/Untitled.png)

![Untitled](Swift%203d54a866c8ff44cda641b17665ea2c24/Untitled%201.png)

```swift
var ages: [Int] = [12, 46, 89, 13 , 10, 36, 83, 65] // Declaring the type of the array
var ages: [Int] = []

ages.count // method to count the element inside the array
ages.first // find the first index of the array
ages.last // find the last index of the array
ages[0] // find the index by the position

ages.append(99) // put a new element into the array
ages.insert(44, at: 0)  // put a new element in a specific location 
ages.sort()
ages.reverse()
ages.shuffle()

```

## Set

- Similar to the array
- Unordered
- No duplicates
- Better performance

```swift
var ages = [18, 85, 34, 73, 15, 24, 18]
var agesSet: Set<Int> = []  // Set<typeof>

var agesSet = Set(ages) // will remove the duplicated values

ages.insert(101)
agesSet.contains(101) // O(n) 

```

## Dictionary

- key: value

```swift
let devices: [String: String] = [
	"phone": "Iphone 11",
	**"laptop": "2020 Macbook Air",
	"desktop": "Windows PC",
]

// find an element by key
devices["laptop"]
devices["desktop"]
```

## Functions

- Set of instructions

```swift
func printName(name: String) {
	print(name)
}

printName(name: "Pipoca")

// function signature
// return a value so that we can use it outside the function
// to = argument label
// firstNumber and secondNumber are the parameter label
func add(firstNumber: Int, to secondNumber: Int) -> Int {
	let sum = firstNumber + secondNumber
	return sum
} 
```

## If/Else

- Conditional operator

```swift
 var isDarkModeOn = true

if isDarkModeOn == true {
	print("it's dark!")
} else {
		print("Uhh, not dark")
}

var playerScore = 100
var cpuScore = 500

if playerScore > cpuScore {
		print("Congrats, player!!")
} else {
	print("Congrats, cpu!")
}

/*
if something {
		action
} else if something {
		action
} else {
		action
}
*/
```

## For Loops

- Iterate over a collection
- do something N times

```swift
let allStars = ["James", "Davis", "Harden", "Doncic", "Leonard"]

for player in allStars {
		print(player)
}
// It will print their names, one by one

for player in allStars where player == "Harden" {
		print(player)
}
// It will print only Harden

var randomInts: [Int] = []

for _ in 0..<25 {
		let randomNumber = Int.random(in: 0...100)
		randomInts.append(randomNumber)
} 

print(randomInts)
```

## Enum

- Group of values that are related
- Case

```swift
enum Phone {
		case Iphone11
		case S22
		case Pixel
		case Nokia
}

func getGabrielsOpinion(on phone: Phone) {
		if phone == .Iphone11 {
				print("Esse vai ser meu prox telefone")
		} else if phone == .S22 {
				print("bla bla bla")
		} else if phone == .Pixel {
				print("kgmalgnakn")
		} else {
				print("indestrutivel")
		}
}

getGabrielsOpinion(on: .Iphone11)

// OR

enum Phone: String {
		case Iphone11 = "Esse vai ser meu prox telefone"
		case S22 = "bla bla bla"
		case Pixel = "kgmalgnakn"
		case Nokia = "indestrutivel"
}

func getGabrielsOpinion(on phone: Phone) {
		print(phone.rawValue)
}

getGabrielsOpinion(on: .Nokia)
```

## Switch Statements

```swift
enum Phone {
		case Iphone11 
		case S22 
		case Pixel 
		case Nokia 
}

func getGabrielsOpinion(on phone: Phone) {
	switch phone {
		case .Iphone11:
				print("Esse vai ser meu prox telefone")
		case .Pixel:
					print("kgmalgnakn") 
		case .Nokia:
				print("indestrutivel")
		case .S22:
				print("bla bla bla")
	}
}

getGabrielsOpinion(on: .Nokia)

let matchmakingRank = 900

func findPlayerLeague(from rank: Int ) {
	switch rank {
			case 0:
				print("Play the game to determine your league")
			case 1..<50:
				print("You're in BRONZE League")
			case 50..<100:
				print("You're in SILVER League")
			case 100..<200:
				print("You're in GOLD League")
			default:
				print("You're a natural")
	}
}

findPlayerLeague(from: matchmakingRank)
```

## Operators

- Check, change and combine values
- `+, -, *, %, <, >, ≤, ≥, !, ==, &&, ||`
- Decrease the counter ⇒ `-=`
- Increase the counter ⇒ `+=`

```swift
let valueOne = 55
let valueTwo = 88

let sum1 =  valueOne + valueTwo
let sum2 =  valueOne - valueTwo
let sum3=  valueOne * valueTwo
let sum4 =  valueOne / valueTwo // it will give me a fraction -> but it wont show, bc the values are ints
```

## Optionals

- Handling nil values

```swift
var ages: [Int] = [21, 45, 73, 69, 17]
ages.sort()

// if let
if let oldestAge = ages.last {
		print("oldest age is /(oldestAge)") // a barrinha so q pro outro lado (string interpolation)
} else {
		print("There isnt an oldest age ")
}

// nil coalescing
let oldestAge = ages.last ?? 999  // any value

//guard statement
func getOldestAge {
		guard let oldestAge = ages.last else {return}
		print("/(oldesAge) is the oldest age")
}
getOldestAge()

//force unwrap
let oldestAge = age.last!  // dangerous

```

## Self

- Se refere  a propria classe

## Class

- Is an object
- Can have properties and fuctions attached
- Reference types: point to a specific set of data

```swift
class Developer {
	var name: String  
	var jobTitle: String
	var yearsExp: Int

	init(name: String, jobTitle: String, yearsExp: Int) {
			self.name = name
			self.jobTitle = jobTitle
			self.yearsExp = yearsExp
	}
}

let person = Developer(name: "Gabriel", jobTitle: "Dev", yearsExp: 2 )

person.name
person.jobTitle
person.yearsExp

// if we want to make it optional / empty version

class Developer {
	var name: String?  
	var jobTitle: String?
	var yearsExp: Int?
	
	init() {}
	
	init(name: String, jobTitle: String, yearsExp: Int) {
			self.name = name
			self.jobTitle = jobTitle
			self.yearsExp = yearsExp
	}
}

let gabriel = Developer()

gabriel.name = "johnny"
gabriel.jobTitle = "Codador"
gabriel.yearsExp = 20

// Classes can have functions

class Developer {
	var name: String?  
	var jobTitle: String?
	var yearsExp: Int?
	
	init() {}
	
	init(name: String, jobTitle: String, yearsExp: Int) {
			self.name = name
			self.jobTitle = jobTitle
			self.yearsExp = yearsExp
	}
	
	func speakName() {
			print(name!) // force unwrap
		}
}

let person = Developer(name: "Gabriel", jobTitle: "Coder", yearsExp: 2 )

person.speakName()
```

## Inheritance

- SubClass

```swift
// class subClass: Class 

class iOSDeveloper: Developer {
		var favoriteFramework: String?
		
		func speakFavoriteFramework() {
					if let favoriteFramework = favoriteFramework {
								print(favoriteFramework)						
		} else {
				print("i dont have a favorite framework")
		}
					
	}

	override func speakName() {
			print("/(name!) - /(jobTitle!)") // dangerous force unwrap
	}
}

let person = iOSDeveloper(name: "Gabriel", jobTitle: "Coder", yearsExp: 2)

person.favoriteFramework = "MapKit"
person.speakFavoriteFramework()
```

## Struct

- It’s an object
- Can have properties, functions…
- Ligh-weight
- Better perfomance over classes
- Value types: copy the set of data in its own instance when created

```swift
// Reference type any changes you make will change the same source of truth
var gabriel = Developer(name: "Gabriel", jobTitle: "Coder", yearsExp: 2 )

var claudio = gabriel // gabriel

claudio.name = "Claudio" // Claudio
gabriel.name  // Claudio

// Value Type

struct Developer {
		var name: String  
		var jobTitle: String
		var yearsExp: Int
}

var gabriel = Developer(name: "Gabriel", jobTitle: "Dev", yearsExp: 2 )

var claudio = gabriel
claudio.name = "Claudio" // Claudio
gabriel.name // Gabriel
```

- Very important Note:
    - reference types vs value types is  a common interview question
    

## Extension

- Way to add custom functionality to an existing type

```swift
extension String {
		
		func removeWhitespace() -> String {
			return components(separetedBy: .whitespaces).joined()
	}	
}

let alphabet = "A B C D E F G" // IT WILL PRINT EXACTLY LIKE THIS
print(alphabet.removeWhitespace()) // ABCDEFG (NO SPACES)
```
