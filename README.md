# Fallback-functions
How correctly build a fallback functions

Fallback function is very important thing to have in contract:

1) Receive function is trigerred automatically when we get a empty data transfer. This is for .transfer .send or emty data .call 
 The function cannot have arguments, cannot return anything,  and must have external visibility and payable state mutability
                  
                 // Calls with no data + value
                 receive() external payable{
                    // React to receiving ether
                 }

2) Fallback function is execute when no other function matches. Another words someone (another external contract) try to call function that we didn't have in our contract. Function can be, but doesn't have to be payable. If someone send a empty data call with value and we doesn't have receive() and we want to receive funds, and we have fallback payable function, it will work as long as it's payable. The fallback function always receives data, but to also receive Ether, you should mark it as payable
This function cannot have arguments, cannot return anything, and must have external visibility

                 // When no other function matches 
                 fallback() external payable{
                    // execution
                 }
