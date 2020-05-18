# Business Rules
Simple interface to create custom business rules that you can process on your code and check if pass or not

# Example
```js
import { RulesManager } from "ami_business_rules";

var rm = RulesManager.get();

rm.addRule(ruleObject, "Rule Group Name");

var result = rm.process("Rule Group Name");

if (!result){
    console.log("FAILS");
} else {
    console.log("PASS");
}

```

# Run test
You can run the test
```bash
npm run start-test
```


