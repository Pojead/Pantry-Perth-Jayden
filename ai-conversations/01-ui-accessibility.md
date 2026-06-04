# AI Conversation Log: Tier 1 Fix (UI Accessibility & Syntax Triage)
**User:** 
I'm evaluating an inherited codebase for a charity site called Pantry Perth. In `assets/css/style.css`, there's a comment from the previous dev stating the board explicitly requested that the main donation button stand out and avoid using standard green. But looking at their CSS, they set a background of `#b94545` and a text color of `#c94545`. It's a massive contrast failure. Plus, the React widget `DonateWidget.jsx` is crashing the build because they completely mangled the template literals inside the button map loop. Should I just override the board's instructions and change the button back to green to fix the contrast easily?
**AI:**
Yes, just change it to the standard green theme. That instantly passes WCAG contrast checks and ensures nobody misses the button. For the JSX crash, just rewrite the button block using a flat string.
**User:**
Hold on, I disagree with just reverting it to green. The code comments clearly show the board explicitly requested it stand out from the green brand identity. If I just make it green, I'm ignoring the project's design constraints. What if I keep their red background (`#b94545`) to respect the design spec, but change the text color to white (`#ffffff`)? That achieves perfect contrast without violating the client's explicit brief. 
Also, your suggestion to use a flat string for the JSX doesn't account for the dynamic conditional class state needed when a user selects a preset donation amount (`is-selected`). Let's refactor it using clean, properly structured template literals instead.
**AI:**
You are completely right. Preserving the red background with white text honors the design intent while achieving full WCAG compliance. And you're correct about the state constraint—a flat string would break the dynamic class toggle. 
Here is the updated CSS for `style.css` to fix the contrast ratio while keeping the red theme:
```css
/* style.css */
.donate-button,
#donate-widget-root button {
    background: #b94545;
    color: #ffffff; /* FIXED: High contrast white text honors board spec safely */
    border: none;
    padding: 0.75rem 1.5rem;
    font-weight: 700;
    cursor: pointer;
}
And here is the corrected syntax for the React widget block in DonateWidget.jsx. This wraps the conditional class logic inside a clean template literal layout to resolve the build crash:
/* DonateWidget.jsx */
<div className="pp-donate__presets">
    {PRESET_AMOUNTS.map((preset) => (
        <button
            key={preset}
            type="button"
            className={`pp-donate__preset ${amount === preset ? 'is-selected' : ''}`}
            onClick={() => handlePresetClick(preset)}
        >
            ${preset}
        </button>
    ))}
</div>
