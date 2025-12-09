# Learning Hub Builder - Reusable Prompt Template

## Quick Start Prompt

Copy and paste this prompt to start building a new course:

---

```
I need you to build an interactive HTML Learning Hub for a technical training course.

**Course Topic:** [TOPIC NAME - e.g., "SuiteFlow", "SuiteScript Advanced", "NetSuite Administration"]

**Output Requirements:**
1. Master Dashboard (main navigation page)
2. Weekly modules organized by topic progression
3. Individual module pages with embedded content
4. Appendices:
   - A: Code/Configuration Examples (annotated)
   - B: Hands-On Exercises
   - C: Real-World Case Studies
   - D: Searchable Glossary/Reference

**Design Standards:**
- Modern gradient styling (purple/blue theme)
- Responsive cards for navigation
- Syntax-highlighted code blocks
- Color-coded info boxes (blue=info, yellow=warning, green=success, purple=note)
- Module cross-references using 📚 emoji annotations
- Self-contained HTML files (no external dependencies except Google Fonts)

**Naming Conventions:**
- Field prefix: `_urk` (e.g., `custfield_urk_fieldname`)
- Script prefix: `{project}_` (e.g., `urk_ue_scriptname`)

**Before you begin, please ask me for the source materials.**
```

---

## Handover Checklist (AI Should Ask For)

When the AI receives the prompt above, it should request:

### Required Materials

| Material | Format | Purpose |
|----------|--------|---------|
| **Training Transcripts/Lectures** | .txt, .md, .docx | Core teaching content |
| **Student Guide/Manual** | .pdf | Exercises, official curriculum |
| **Slide Decks** | .pptx, images | Visual aids, diagrams |

### Optional Materials (Enhance Quality)

| Material | Format | Purpose |
|----------|--------|---------|
| **Real-World Scripts/Code** | .js, .xml, .json | Case studies, production examples |
| **Documentation (README, etc.)** | .md | Architecture explanations |
| **Exercise Images/Screenshots** | .png, .jpg | Step-by-step visuals |
| **Quick Reference Cards** | .md, .pdf | Glossary source material |

### Information to Gather

1. **Course Structure**
   - How many modules/lessons?
   - Suggested weekly breakdown?
   - Prerequisites?

2. **Target Audience**
   - Beginner / Intermediate / Advanced?
   - Role (Developer, Admin, Consultant)?
   - Certification alignment?

3. **Customization**
   - Company-specific branding?
   - Custom field/script naming prefix?
   - Specific topics to emphasize?

---

## Standard AI Response (Handover Script)

The AI should respond with something like:

```
Great! I'll build your [TOPIC] Learning Hub. Before I start, please provide:

**Required (minimum to proceed):**
□ Training transcripts or lecture notes (.txt, .md, or .docx)
□ Number of modules/lessons in the course

**Recommended (significantly improves quality):**
□ Student guide or manual (PDF preferred)
□ Any slide deck images or diagrams

**Optional (for advanced features):**
□ Real-world code examples you want included
□ Exercise screenshots
□ Quick reference materials

**Quick questions:**
1. Target audience level? (Beginner/Intermediate/Advanced)
2. Preferred weekly breakdown? (e.g., 2-3 modules per week)
3. Any certification this aligns with?
4. Custom naming prefix for fields/scripts? (default: _urk)

Upload what you have and I'll get started!
```

---

## Build Process (Internal Recipe)

Once materials are received, follow this sequence:

### Phase 1: Structure
1. Analyze source materials for module count and topics
2. Create weekly groupings (2-3 modules per week typical)
3. Generate Master Dashboard with week cards

### Phase 2: Content
4. Create week dashboard pages
5. Create individual module pages with:
   - Learning objectives
   - Core concepts (from transcripts)
   - Code examples (syntax highlighted)
   - Key takeaways
   - Navigation links

### Phase 3: Appendices
6. **Appendix A:** Extract and annotate code examples
7. **Appendix B:** Convert exercises from student guide
8. **Appendix C:** Add real-world case studies (if provided)
9. **Appendix D:** Build searchable glossary from all terms

### Phase 4: Polish
10. Add cross-references (📚 MODULE X: annotations)
11. Sanitize company-specific info → placeholders
12. Test all navigation links
13. Package as .zip

---

## File Structure Template

```
[Course-Name]-Learning-Hub/
├── Master-Dashboard.html
├── Week-1/
│   ├── week-1-dashboard.html
│   ├── Module-1.html
│   └── Module-2.html
├── Week-2/
│   └── ...
├── Week-N/
│   └── ...
├── Appendix-A-Code-Examples.html
├── Appendix-B-Exercises.html
├── Appendix-C-Case-Studies.html
├── Appendix-D-Glossary.html
└── Resources/
    ├── Student-Guide.pdf
    └── [images]
```

---

## Styling Reference

### Info Box Classes
```html
<div class="info-box blue">Info/Definition</div>
<div class="info-box yellow">Warning/Caution</div>
<div class="info-box green">Success/Best Practice</div>
<div class="info-box purple">Note/Tip</div>
<div class="info-box red">Error/Danger</div>
```

### Code Block with Syntax Highlighting
```html
<pre><code><span class="comment">// Comment</span>
<span class="keyword">var</span> x = <span class="string">'value'</span>;
<span class="function">myFunction</span>();
</code></pre>
```

### Module Cross-Reference
```html
<span class="module-ref">📚 Module 5</span>
```

---

## Courses This Template Works For

- [x] SuiteScript 2.x Fundamentals (COMPLETED)
- [ ] SuiteScript Advanced
- [ ] SuiteFlow (Workflows)
- [ ] SuiteAnalytics
- [ ] NetSuite Administration
- [ ] SuiteTalk (Web Services)
- [ ] SuiteCommerce
- [ ] Any technical training with modules + exercises

---

**Template Version:** 1.0  
**Created:** December 2025  
**Based On:** NetSuite SuiteScript Learning Hub build
