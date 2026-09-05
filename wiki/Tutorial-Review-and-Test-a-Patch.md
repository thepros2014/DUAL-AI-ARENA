# Tutorial: review and test a patch

**Goal:** decide whether a proposed change actually satisfies your challenge.

Begin with the result from [[Tutorial-Your-First-Arena-Battle]].

## 1. Inspect the finding and the change

Open the findings and working-source views. Use the diff view if available. Read both removed and added lines, then compare the proposal with the original requirements.

For the practice function, ask:

- Does it accept valid numbers and preserve zero?
- Does it reject strings instead of silently converting them?
- Does it reject negative, fractional, or unsafe quantities?
- Does it reject non-finite inputs and results?
- Did it introduce unrelated behavior or dependencies?

## 2. Copy the proposal into a practice file

Use the source inspection and copy controls described in [[Viewing-and-Exporting-Results]]. Save the proposed function in a separate practice file. Keep the original example so you can compare them.

## 3. Check the contract

Use this table as a checklist, or turn it into tests in your normal JavaScript test runner. These checks are performed outside the Arena unless your installed build explicitly provides a test-running feature.

| Price | Quantity | Expected result |
| --- | --- | --- |
| `5` | `3` | `15` |
| `0` | `4` | `0` |
| `5` | `0` | `0` |
| `"5"` | `3` | Error |
| `-1` | `2` | Error |
| `5` | `1.5` | Error |
| `5` | `-1` | Error |
| `NaN` | `2` | Error |
| `Infinity` | `2` | Error |
| `1` | `Number.MAX_SAFE_INTEGER + 1` | Error |
| `Number.MAX_VALUE` | `2` | Error |

An error should be explicit; returning zero or an invalid numeric result does not meet the exercise contract. The contract does not require a particular error message.

## 4. Feed back a failing case

If a check fails, describe the specific mismatch in the next available instruction field or a new challenge:

> The proposed function still accepts a fractional quantity. `totalPrice(5, 1.5)` must throw an error. Fix that case while preserving the valid cases and the other validation requirements.

Review and test the next proposal again. Keep feedback focused on observed behavior.

## 5. Record the outcome

Save a brief note stating what changed, which checks you ran, and anything still unresolved. For real projects, also run existing tests and review the change through your normal development process.

**You have completed this tutorial when:** you can distinguish a proposed fix from a tested fix and identify evidence that supports accepting or rejecting it.

[[Arena-Tutorials]] · [[Tutorial-Review-Your-Own-Project]]
