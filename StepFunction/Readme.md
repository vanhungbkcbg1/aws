## State Machine structure
State machines are defined using JSON text that represents a structure containing the following fields.
  - Comment (Optional)
  - Started At ( Required): A string that must exactly match (is case sensitive) the name of **one** of the state objects.
  - States: An object containing a comma-delimited set of states.
      ```
         {
            "State1" : {
            },

            "State2" : {
            },
            ...
        }
      ```
## States
States are elements in your state machine. A state is referred to by its name, which can be any string, but which must be unique within the scope of the entire state machine.
States can perform a variety of functions in your state machine:
   - Do some work in your state machine( A Task state)
   - make a choice between  branches of execution (a Choice state)
   - Stop an execution with fail or success( a Fail or Success state)
   - pass its input to its output or injected some data to workflow ( a Pass state)
   - Begin parallel branches of execution ( a Parallel state)
   - Dynamically iterate steps ( a Map state)
## Common State Field
- Type(Required): type of state
- Next(Required if you don't set value for End field)
    The name of the next state that is run when the current state finishes
- End: if you want mark this state is terminal state
- InputPath(Optional): choose input for state process
- OutputPath(Optional): defined output of this state
