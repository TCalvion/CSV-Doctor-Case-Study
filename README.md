# CSV Doctor

*In development. The encoding-choice workflow has passed a scoped independent audit. Live checkout is still in development.*

CSV Doctor diagnoses and repairs malformed CSV files. The planned web flow starts with a free report that shows what went wrong before the user decides whether to pay for a repaired download.

The Python engine diagnoses the file and prepares the repair. CSV rows are processed without sending them to an AI model.

## When the encoding is ambiguous

An encoding guess can leave a file looking readable while changing a name or a value. CSV Doctor shows plausible readings for free when it can put every detected ambiguous passage in front of the user. After the user picks a reading, it scans the whole file again with that interpretation before preparing a repair. If the examples cannot cover the ambiguity, it asks for a new export. Encoding uncertainty alone never increases the price.

## What independent testing changed

An early encoding fix passed 1,544 automated tests. An independent audit still found incorrect handling of short fields and cases where an encoding warning moved a file to a higher price tier. Those findings became acceptance criteria for subsequent rounds.

In a later scoped audit, the reviewer verified that the chosen reading carried through to the repaired CSV and that six valid older packages in the test set were returned byte for byte. The audit used synthetic files, browser tests, and simulated payments.

## Project status

The source repository is private. Development and evaluation take place at TCalvion Tech.

I define the repair and pricing rules and decide what the release must demonstrate. I use separate builders and reviewers so the evidence includes tests the builder did not anticipate.

*Steve Jensen · TCalvion Tech OÜ*
