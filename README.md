# eth-avaxProof
Contract Definition:
  
   contract SimpleExample {
       uint256 private value;
   
Defines a contract named SimpleExample. It contains a private state variable value of type uint256.

setValue Function:
  
   function setValue(uint256 newValue) public {
       require(newValue > 0, "Value must be greater than zero");
       require(newValue <= 100, "Value must be less than or equal to 100");
       value = newValue;
   }
   
   - This function sets the value variable.
   - It uses require statements to ensure the new value is greater than 0 and less than or equal to 100.
   - If any of these conditions are not met, the transaction reverts with the specified error message.

getValue Function:
  
   function getValue() public view returns (uint256) {
       return value;
   }
   
   - This is a read-only function that returns the current value of the value variable.

Components and Explanation:

1. Contract Definition:
  
   contract ExampleContract {
       uint256 public value = 10;
   
   Defines a contract named ExampleContract. It contains a public state variable value initialized to 10.

2. requireExample Function:
  
   function requireExample() public view {
       require(value != 0, "Value must be non-zero");
   }
   
   - This function demonstrates the usage of require to ensure that the value is non-zero.
   - If value is zero, the transaction reverts with the message "Value must be non-zero".

3. assertExample Function:
  
   function assertExample() public view {
       assert(value != 0);
   }
   
   - This function demonstrates the usage of assert to check that the value is non-zero.
   - If value is zero, the transaction reverts, consuming all remaining gas.

4. revertExample Function:
  
   function revertExample(uint256 testValue) public pure {
       require(testValue != 0, "testValue cannot be zero");
       if (testValue == 0) {
           revert("testValue cannot be zero");
       }
   }
   
   - This function demonstrates the usage of both require and revert.
   - First, it uses require to check if testValue is non-zero.
   - If testValue is zero, it calls revert with the message "testValue cannot be zero".

- SimpleExample Contract:
  - Contains a private state variable value.
  - Has functions to set (setValue) and get (getValue) the value.
  - Uses require to enforce constraints on the value being set.

- ExampleContract:
  - Contains a public state variable value initialized to 10.
  - Demonstrates usage of require, assert, and revert through different functions.
  - requireExample ensures value is non-zero using require.
  - assertExample ensures value is non-zero using assert.
  - revertExample demonstrates how both require and revert can be used to enforce conditions and handle errors.
