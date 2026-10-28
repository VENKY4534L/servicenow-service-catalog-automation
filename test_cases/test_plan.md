# Test plan — execute these in your PDI and record actual results

| ID | Scenario | Expected result |
|---|---|---|
| TC-01 | Submit valid software access request | Request record created with expected variables |
| TC-02 | Omit required application name | Submission blocked with validation message |
| TC-03 | Submit hardware request | Correct item and variables recorded |
| TC-04 | Submit employee support Record Producer | Target record created and mapped fields correct |
| TC-05 | Manager approves | Request moves to approved/fulfillment path |
| TC-06 | Manager rejects | Request marked rejected and requester notified |
| TC-07 | Approved request | One fulfillment task created for correct group |
| TC-08 | Duplicate flow trigger | No duplicate approvals/tasks |
| TC-09 | Requester views own request | Only permitted request details visible |
| TC-10 | Requester attempts unauthorized update | ACL denies restricted update |
| TC-11 | REST endpoint returns success | Response status/body handled as expected |
| TC-12 | REST endpoint fails or times out | Error handled and logged without exposing secrets |

For each case record: instance/release, date, tester, steps, expected result, actual result, pass/fail, and screenshot evidence. Do not mark tests passed until performed.
