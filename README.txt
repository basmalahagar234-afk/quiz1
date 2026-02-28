Question 3 – Prompt Engineering and Verification Evidence

------------------------------------------------------------

1) Prompt 1 – Planning Prompt (No Code)

Planning Prompt I Asked:

I asked ChatGPT to give me a plan (without code) for how to:
- Create responsive breakpoints for desktop, tablet, and mobile
- Make the hero section two columns on desktop and stacked vertically on mobile
- Align the header logo on the left and navigation on the right on desktop, and stack them on mobile

Two Things I Accepted:

1. I accepted using Flexbox for the header and hero section because it makes it easy to align items horizontally and then switch to vertical layout using flex-direction in a media query.

2. I accepted using media queries at 900px and 600px because they clearly separate desktop, tablet, and mobile layouts and match the assignment requirements (4 columns, 2 columns, 1 column).

One Thing I Rejected (and Why):

I rejected using CSS Grid for the hero section because it only has two elements. Flexbox was simpler and easier to control for alignment and stacking behavior.

------------------------------------------------------------

2) Prompt 2 – Debug Prompt

Problem I Had:

When I resized the browser below 600px, the hero section did not stack vertically. The hero text and hero card stayed side-by-side instead of stacking.

Exact CSS Snippet I Asked About:

.hero {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 40px 0;
  gap: 20px;
}

Most Important Part of the AI Response:

ChatGPT explained that Flexbox defaults to a horizontal layout (row). It said I needed to add a media query with max-width: 600px and change flex-direction to column so the elements would stack vertically.

What I Changed Afterward:

I added a media query and changed the hero layout to:

@media (max-width: 600px) {
  .hero {
    flex-direction: column;
    text-align: center;
  }
}

After adding this, the hero section stacked correctly on mobile screens.

------------------------------------------------------------

3) Verification List

Viewport Sizes I Tested:

- 375px (Mobile)
- 768px (Tablet)
- 1200px (Desktop)

What I Checked Visually:

At 375px:
- Header stacked vertically
- Navigation centered
- Hero stacked vertically
- Grid displayed 1 column
- No horizontal scrolling

At 768px:
- Grid displayed 2 columns
- Layout looked clean
- No overflow issues

At 1200px:
- Logo aligned left and navigation aligned right
- Hero displayed in two columns
- Grid displayed 4 columns
- Hero card aligned to the right
