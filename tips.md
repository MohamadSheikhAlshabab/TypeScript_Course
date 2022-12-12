# TypeScript:

- ● WHAT IS TYPESCRIPT?

  - ●  TypeScript Is A Strongly Typed Programming Language That Builds On JavaScript
  - ● TypeScript Developed And Maintained By Microsoft
  - ● TypeScript Is JavaScript With Types
  - ● Typescript Add Features To JavaScript Without Changing It

---

- ● WHY WE NEED TYPESCRIPT?

  - ●  Detect Errors Without Running The Code "Static Type Checking"
  - ●  Analyze The Code As You Type
  - ●  Save Some Unit Tests As The Error Show While Writing
  - ●  Every JS File Is Valid TS File
  - ●  Will Help You When You Write React, Vue, Angular Apps
  - ●  Gives You The Missing Features In JS Like "Interfaces, Generics, Decorators"

---

- ● HOW TYPESCRIPT WORKS? OLT

  - ● TypeScript Compiler Compile TS Code Into JavaScript Code "This Called Transpilation"
  - ● How About The New Features? Workaround

---

- ## 03 - Create Configuration And Watch Files


- ● TypeScript Commands:

  - ● `tsc index.ts` compile typescript file to javascript file with same name and javascript extension (index.js).
  - ● `tsc -h` flag for show help for tsc command.
  - ● `tsc -w` watch input files; any changes in file will automatically update.
  - ● `tsc --init` create a new tsconfig.json with : target:(ecmascript version), rootDir:(root folder that contain typescipt files to complie them), outDir:(this output folder for all files after complie them or emitted files)


---

- ## 04 - Statically vs Dynamically Typed Languages 

- ● Statically Typed Language Like [Rust, C, C++]
  - ● Variables Types Are Static, Once You Declare It You Cannot Change
  - ● Type Of A Variable Is Known At Compile Time "Do Type Checking At Compile-Time"
  - ● Have Better Performance At Run-Time Due To Not Needing To Check Types Dynamically
  - ● Error Detected Earlier

- ● Dynamically Typed Language Like [PHP, Python, JavaScript]
  - ● Variables Types Are Dynamic, You Can Always Change It
  - ● "Type Checking At Execution-Time"
  - ● Error Can Be Detected After Execution

          // let num = 10;
          // num = "Elzero";
          // console.log(num);

          let age = 40;
          if (age > 30) {
            console.log("Good");
          } else {
            console.log(age.repeat(3)); /ERROR/ Property 'repeat' does not exist on type 'number'. ts(2339)
          }
          
 ---
 
- ## 05 - Type Annotations And Any Type 


- ● Type Annotations || Signature
  - ● Indicate The Data Type Of Variables
  - ● Indicate The Data Type Of Functions Input/Output
  - ● Objects, etc.

  - ● Why We Use It ?
  - ● Is It Mandatory ?
  - ● What Happen If We Didnt Use It ?


        let theName = "Elzero";
        let theAge: number = 40;
        let hire: boolean = true;
        let all: any = "Elzero Web School";
        let allVars; // Any

        theName = "Osama";
        all = 100;

        function add(n1: number, n2: number) {
          return n1 + n2;
        }

        console.log(add(10, 20));
        console.log(typeof add(10, 20));

        function add(n1, n2) {
          return n1 + n2;
        }

        console.log(add(10, "20"));
        console.log(typeof add(10, "20"));
        
---

- ## 06 - Type Annotations With Array 



      let all: string | number | boolean = "Osama";

      all = "A";
      all = 100;
      all = true;

      let myFriends: string[] = ["Osama", "Ahmed", "Sayed"];

      for (let i = 0; i < myFriends.length; i++) {
        console.log(myFriends[i].repeat(3));
      }
        
---

- ## 07 - Type Annotations With Multi-Dimensional Array

- ● Type Annotations With Multidimensional Arrays

      let arrayOne: number[] = [1, 2, 3, 4, 5];
      let arrayTwo: string[] = ["A", "B", "C"];
      let arrayThree: (string | number)[] = [1, 2, 3, 4, "A", "B", "C"];

      let arrayFour: (string | number | string[] | boolean)[] = [1, 2, 3, 4, "A", "B", ["C", "D"], true, false];
            
---

- ## 08 - Type Annotations With Function 

- ● Type Annotations With Functions

 - ● noImplicitAny

  - ● noImplicitReturns
    - Will Check All Code Paths In A Function To Ensure They Return A Value

  - ● noUnusedLocals
    - Report Errors On Unused Local Variables

  - ● noUnusedParameters
    - Report Errors On Unused Parameters In Functions.

          let showMsg = true;

          function showDetails(name: string, age: number, salary: number) : string {
            let test = 10;
            if (showMsg) {
              return `Hello ${name}, Age Is ${age}, Salary Is ${salary}, Test Variable ${test}`;
            }
            return `No Data To Show`;
          }

          console.log(showDetails("Osama", 40, 5000));
                
---

- ##  09 - Optional And Default Parameter 

- ● Function
  - ● Optional and Default Parameters
  - ● In JavaScript, Every Parameter Is Optional => "undefined" If You Didnt Use It
  - ● "?" Optional Parameter


        function showData(name?: string, age?: number, country?: string) {
          return `${name} - ${age} - ${country}`;
        }

        console.log(showData("Osama", 40, "Egypt"));
                     
---

- ##  10 - Function Rest Parameter 


- ●  Function
  - ● Rest Parameter
  - ● What About Float => All Is Under Type Number


          function addAll(...nums: number[]) : number {
            let result = 0;
            for (let i = 0; i < nums.length; i++) {
              result += nums[i];
            }
            // nums.forEach((num) => result += num);
            return result;
          }

          console.log(addAll(10, 20, 30, 100, 10.5, +true));
          
                     
---

- ## 11 - Anonymous And Arrow Function 

- ● Function
  - ● Anonymous Function
  - ● Arrow Function
  
  

        const add = function(num1: number, num2: number) : number {
          return num1 + num2;
        }

        console.log(add(10, 20));

        const addWithArrow = (num1: number, num2: number) : number => num1 + num2;

        console.log(addWithArrow(10, 20));
                    
                     
---

- ## 12 - Type Alias

- ● Data Types
  - ● Type Alias

          type st = string;
          let theName: st = "Elzero";
          theName = "Osama";

          type standnum = string | number;
          let all: standnum = 10;
          all = 100;
          all = "Osama";
                    
                     
---

- ##  13 - Type Alias Advanced 


- ● Data Types
  - ● Advanced Type Alias


          type Buttons = {
            up: string,
            right: string,
            down: string,
            left: string
          }

          type Last = Buttons & {
            x: boolean
          }

          function getActions(btns: Last) {
            console.log(`Action For Button Up Is ${btns.up}`);
            console.log(`Action For Button Right Is ${btns.right}`);
            console.log(`Action For Button Down Is ${btns.down}`);
            console.log(`Action For Button Left Is ${btns.left}`);
          }

          getActions({ up: "Jump", right: "Go Right", down: "Go Down", left: "Go Left", x: true });
                              
                     
---

- ##   14 - Literal Types 
 
- ● Data Types
  - ● Literal Types


        type nums = 0 | 1 | -1;

        function compare(num1: number, num2: number) : nums {
          if (num1 === num2) {
            return 0;
          } else if (num1 > num2) {
            return 1;
          } else {
            return -1;
          }
        }

        console.log(compare(20, 20)); // 0
        console.log(compare(20, 15)); // 1
        console.log(compare(20, 30)); // -1

        let myNumber: nums = 1;
                              
                     
---

- ##   15 - Tuple

- ● Data Types
  - ● Tuple
    - ● Is Another Sort Of Array Type
    - ● We knows Exactly How Many Elements It Contains
    - ● We Knows Which Types It Contains At Specific Positions


            let article: readonly [number, string, boolean] = [11, "Title One", true];
            article = [12, "Title Two", false];
            // article.push(100);
            console.log(article);

            const [id, title, published] = article;
            console.log(id);
            console.log(title);
            console.log(published);

                     
---

- ##   16 - Void And Never 

- ● Data Types
  - ● Void
    - ● Function That Will Return Nothing
    - ● Function In JavaScript That Not Return A Value Will Show undefined
    - ● undefined is not void
  - ● Never
    - ● Return Type Never Returns
    - ● The Function Doesn't Have A Normal Completion
    - ● It Throws An Error Or Never Finishes Running At All "Infinite Loop"


            function logging(msg: string) : void {
              console.log(msg);
              return;
            }

            console.log(logging("Iam A Message"));
            console.log("Test");

            const fail = (msg: string) => {
              throw new Error(msg);
              // return 10;
            }

            function alwaysLog(name: string) : never {
              while(true) {
                console.log(name);
              }
            }

            alwaysLog("Osama");
            // console.log("Test");

                     
---

- ##   17 - Enums Part 1

- ● Data Types
  - ● Enums => Enumerations
    - ● Allow Us To Declare A Set Of Named Constants
    - ● Used For Logical Grouping Collection Of Constants "Collection Of Related Values"
    - ● It Organize Your Code
    - ● By Default Enums Are Number-Based, First Element Is 0
    - ● Theres A Numeric Enums
    - ● Theres A String-Based Enums
    - ● Theres Heterogeneous Enums [String + Number]


          const KIDS = 15;
          const EASY = 9;
          const MEDIUM = 6;
          const HARD = 3;

          enum Level {
            Kids = 15,
            Easy = 9,
            Medium = 6,
            Hard = 3
          }

          let lvl: string = "Easy";

          if (lvl === "Easy") {
            console.log(`The Level Is ${lvl} And Number Of Seconds Is ${Level.Easy}`);
          }
                     
---

- ##   17 - Enums Part 1
