# programming-langs-comparison

## Pass by value or reference

1. __C++__
  - pass by value which meand a compiler will make a copy
2. __Golang__
  - TBD
3. __JavaScript__
  - (ANSWER BY TIM GOODMAN FROM STACKOVERFLOW) It's always pass by value, but for objects the value of the variable is a reference. Because of this, when you pass an object and change its members, those changes persist outside of the function. This makes it look like pass by reference. But if you actually change the value of the object variable you will see that the change does not persist, proving it's really pass by value. Everything is pass-by-value, full stop. The confusing thing is that you cannot pass an object, nor can you store an object in a variable. Every time you think you're doing that, you're actually passing or storing a reference to that object. But when you go to access its members, there's a silent dereferencing that happens, that perpetuates the fiction that your variable held the actual object.
  - ```
    function changeObject(x) {
      x = { member: "bar" };
      console.log("in changeObject: " + x.member);
    }
    
    function changeMember(x) {
      x.member = "bar";
      console.log("in changeMember: " + x.member);
    }
    
    var x = { member: "foo" };
    
    console.log("before changeObject: " + x.member);
    changeObject(x);
    console.log("after changeObject: " + x.member); /* change did not persist */
    
    console.log("before changeMember: " + x.member);
    changeMember(x);
    console.log("after changeMember: " + x.member); /* change persists */
    ```
