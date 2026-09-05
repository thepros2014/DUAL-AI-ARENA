# Tutorial: your first Arena battle

**Goal:** run a small, controlled review and understand the handoff between Red Team and Blue Team.

## 1. Prepare a practice challenge

Open **Create Challenge** and paste the JavaScript below into the source input. If your build uses folder import, save it as `practice.js` in a new practice folder and import that folder.

```javascript
function totalPrice(price, quantity) {
  return price * quantity;
}
```

This example deliberately leaves input validation undefined. It contains no real customer information or application credentials.

Add these requirements to the challenge description or instructions:

> Review this function against the following contract. Price must be a finite, non-negative number. Quantity must be a non-negative safe integer. Do not convert strings into numbers. Reject invalid inputs and non-finite results with an error. Preserve valid multiplication, including zero. Focus on correctness and input validation; do not add unrelated features.

If your build has no separate instructions field, place these requirements in a comment above the function.

## 2. Choose your model

Enable a configured provider and select an available model. Start with a configuration you have already confirmed works. If your build supports separate team assignments, choose a model for each team.

## 3. Enter the Arena

Select **Start Match & Enter Arena** or the equivalent start control. Leave **AUTO HANDOFF** off for this exercise so you can read each team's output before continuing.

Run the Red Team turn using **Run Red Team Attack** or the equivalent control.

## 4. Read the finding

Look for a concrete mismatch with the contract. For example, the original function accepts a string price because JavaScript converts it during multiplication. A useful finding explains the input, observed result, and expected behavior.

The model may identify different cases or miss some. If the output is vague, narrow the instructions: “Show an input that violates the stated contract and explain the expected result.”

## 5. Run the defense turn

Use **Run Blue Team Patch** to request a change. Read the proposed code and explanation. Check whether it addresses the stated requirements without changing the function's purpose.

Do not judge success from a completion message alone. Continue with [[Tutorial-Review-and-Test-a-Patch]] to check the result.

## 6. Try automatic handoff later

Once the manual workflow is familiar, create another practice challenge and enable automatic handoff. If your build exposes round limits, choose a small limit while learning. Monitor the turns and review the final result in the same way as a manual battle.

**You have completed this tutorial when:** you can identify a Red Team finding, locate the Blue Team proposal, and explain which requirement the proposed change addresses.

[[Arena-Tutorials]] · [[Tutorial-Review-and-Test-a-Patch]]
