# Business Rules
Simple interface to create custom business rules that you can process on your code and check if pass or not

# Example
```js

import { Rule } from "../main";
import { RulesManager } from "ami_business_rules";

export class TestRule implements Rule {
    public status: boolean;
    public code: string;
    public msg: string;
    private data: boolean;
    constructor(code: string, data: boolean) {
        this.code = code;
        this.data = data;
        this.status = true;
    }
    public process(): boolean {
        console.log("Processing " + this.code);
        if (!this.data){
            this.msg = "Fails rule";
            this.status = false;
        } else {
           this.msg = "Pass rule";
        }
        return this.status;
    }


}

var ruleObject = new TestRule();
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

## Contributing

Refer to [CONTRIBUTING.md](https://gitlab.xmltravelgate.com/amian84/business_rules/blob/master/CONTRIBUTING.md)
