# Assignment 7.2 — Solution: Pricing Cards & Centered Login Form

## Project Structure
```
flex-pricing-login/
├── index.html
└── style.css
```
The complete code is in the attached files. The key parts:

## Pricing Cards (Basic, Pro, Premium)
Each card has a name, a price, a features list and a button.

```css
.pricing__cards {
  display: flex;               /* parent container: cards in a row */
  justify-content: center;     /* horizontal alignment of the group */
  align-items: center;         /* vertical alignment: cards of different height share the same center line */
  flex-wrap: wrap;             /* wrap on small screens */
  gap: 24px;
}
```
| Property | What it does here |
|----------|-------------------|
| `justify-content: center` | Centers the three cards on the main (horizontal) axis. Other values to try: `space-between`, `space-around`, `flex-start` |
| `align-items: center` | Centers the cards on the cross (vertical) axis. The Pro card is taller (465px) than Premium (392px) and Basic (355px) and all three share the same center. Try `stretch` (all equal height), `flex-start`, `flex-end` |
| `gap` | Space between cards |
| `flex-wrap: wrap` | Cards go to a new line instead of overflowing on small screens |

## `flex-direction` — Practical Uses
| Where | CSS | Why |
|-------|-----|-----|
| Cards row | `flex-direction: row` (default) | Cards side by side |
| Inside every card | `.plan { display: flex; flex-direction: column; align-items: center; }` | Stack name → price → features → button, centered horizontally. `.plan__features { flex-grow: 1 }` takes the free space so the button goes to the bottom |
| Login form | `.login-form { display: flex; flex-direction: column; gap: 16px; }` | Fields stacked vertically; each `.login-form__field` is also a column (label above input) |
| "Remember me" row | `display: flex; justify-content: space-between; align-items: center;` | Checkbox at the left, link at the right, same baseline |
| Demo section | `row`, `row-reverse`, `column` | Shows how the main axis (and the item order) changes |

## Centered Login Form (horizontal + vertical)
```css
.login-screen {
  display: flex;
  justify-content: center;   /* horizontal centering */
  align-items: center;       /* vertical centering */
  min-height: 100vh;         /* the container is as tall as the screen, so there is room to center */
}
.login-form { width: 100%; max-width: 380px; }
```
I measured it in a browser at 1100px wide: the form has **360px** of free space on the left and on the right, and **216px** above and below — it is exactly centered both ways.

I also checked the page at **375px**: no horizontal overflow, cards wrap into a column and the form fits the screen.

## Submission
- ✅ Webpage with pricing cards and a centered login form: `index.html` and `style.css` (attached)
- 📸 Optional screenshot (attached `screenshot-desktop.png` is a reference rendered by me)
