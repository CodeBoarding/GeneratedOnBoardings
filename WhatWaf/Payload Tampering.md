```mermaid
componentDiagram
  ContentProcessingModule --> TamperScripts : applies
  TamperScripts --> RandomDecoys : implements
  TamperScripts --> RandomComments : implements
  TamperScripts --> RandomUnicode : implements

  class ContentProcessingModule{
    get_working_tampers
  }
  class TamperScripts{
    <<Abstract>>
    tamper(payload)
  }
  class RandomDecoys{
    tamper(payload)
  }
  class RandomComments{
    tamper(payload)
  }
  class RandomUnicode{
    tamper(payload)
  }


```

## Components Description:

**Content Processing Module**
*Description*: Orchestrates the WAF detection process, including loading tamper scripts and applying them to payloads.
*Interaction*: Uses `TamperScripts` to modify the payload.
*Source Files*: `repos.WhatWaf.content`

**Tamper Scripts**
*Description*: An abstract component that defines the interface for tamper scripts. Concrete tamper scripts implement the `tamper` method.
*Interaction*: Implemented by concrete tamper scripts like `RandomDecoys`, `RandomComments`, and `RandomUnicode`.
*Source Files*: N/A (Abstract)

**RandomDecoys Tamper Script**
*Description*: Adds random decoy parameters to the payload to obfuscate it.
*Interaction*: Implements the `tamper` method from `TamperScripts`. Called by `ContentProcessingModule`.
*Source Files*: `repos.WhatWaf.content.tampers.randomdecoys`

**RandomComments Tamper Script**
*Description*: Adds random comments to the payload to obfuscate it.
*Interaction*: Implements the `tamper` method from `TamperScripts`. Called by `ContentProcessingModule`.
*Source Files*: `repos.WhatWaf.content.tampers.randomcomments`

**RandomUnicode Tamper Script**
*Description*: Adds random unicode characters to the payload to obfuscate it.
*Interaction*: Implements the `tamper` method from `TamperScripts`. Called by `ContentProcessingModule`.
*Source Files*: `repos.WhatWaf.content.tampers.randomunicode`
