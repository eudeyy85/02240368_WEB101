Documentation — Main Concepts I Applied.
1. Next.js App Router
    > I used Next.js with the App Router, where every folder I created inside src/app/ automatically became a URL route. For example, when I created src/app/profile/page.jsx, the /profile page was instantly available without me needing to configure anything extra. This made adding new pages really simple.

2. Component-Based Architecture
    > I built the project using reusable React components. Instead of repeating the same code on every page, I created components like MainLayout.jsx, VideoCard.jsx, and VideoFeed.jsx that I could reuse across the whole app. Each component had one clear job:
    - MainLayout.jsx — wraps every page with the sidebar and header.
    - VideoCard.jsx — displays a single post.
    - VideoFeed.jsx — combines multiple VideoCards into a scrollable feed.
    
3. Tailwind CSS for Styling.
 > I styled everything using Tailwind CSS utility classes directly inside my JSX. Instead of writing separate CSS files, I just added classes like flex, bg-red-500, text-xl, and rounded-full inline. This felt much faster than writing traditional CSS and kept everything in one place.

 4. React State with useState
    > I used the useState hook to handle interactivity. The clearest example was the like button inside VideoCard.jsx — when I click it, it toggles liked between true and false, which instantly updates the heart icon color and the like count on screen without reloading the page.
5. Props — Passing Data Between Components
    > I learned how to pass data between components using props. VideoFeed.jsx passes each post's data down to VideoCard.jsx as a post prop. This means the card doesn't hardcode anything — it just displays whatever data it receives, making it flexible and reusable.

6. React Hook Form and Form Validation
    > For the login and signup pages, I used the react-hook-form library to manage my form inputs and validation. The key things I used were:
    register — to connect each input field to the form
    handleSubmit — to only submit when all validations pass
    watch — to read a field's live value (I used this to compare password and confirm password)
    errors — to show error messages under each input

7. Form Validation Techniques
    > I applied several validation rules in my signup form:
    required — to make fields mandatory
    pattern — to check input against a regex, like a valid email format
    minLength — to enforce a minimum number of characters
    validate — a custom function I wrote to make sure both password fields matched

8. Loading States
    > I used an isLoading state on my forms so that when a user submits, the button changes to "Logging in..." and gets disabled. This stops someone from clicking submit multiple times and gives visual feedback that something is happening.

b) Reflection
What I Learned
    This practical taught me how real web apps are built. I learned that React is all about components — breaking the UI into small reusable pieces like VideoCard and VideoFeed made everything easier to manage.
    Next.js file-based routing surprised me with how simple it was — just create a folder and a page.jsx and the route exists. Tailwind CSS felt weird at first but turned out to be much faster than writing separate CSS files. React Hook Form showed me why developers use libraries — managing forms manually gets messy fast. I also realized the login form is just a frontend — it doesn't actually log anyone in, which made me curious about real backend authentication.

Challenges I Faced and How I Overcame Them
Challenges
    1. Folder structure — Too many files at the start, didn't know what went where. Fixed it by tracing how files connect to each other.
    2. Tailwind not working — Styles weren't showing. Missing @import "tailwindcss" in globals.css was the problem.
    3. 'use client' error — Got an error using useState. Learned that Next.js components are server-side by default and adding 'use client' at the top fixed it.
    4. Confirm password not matching — Didn't know how to compare two fields. Used watch('password') from React Hook Form with a custom validate function.
    5. MainLayout not on all pages — Put it inside individual pages instead of layout.js. Moving it to layout.js fixed it and wrapped all pages automatically.