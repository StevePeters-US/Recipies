# Recipe Extraction TODO

These are instructions for Gemini Flash. Extract each recipe from its source URL and save it as a markdown file using the template and formatting rules described below. A completion summary is required at the end.

---

## Template Format

Every recipe file must follow this exact structure:

```markdown
# Recipe Title

[From Here](SOURCE_URL)

> One to two sentence description of the dish. Keep it short and enticing.

## Ingredients

| Ingredient          | Qty    | Unit  | Notes                                                |
|:--------------------|:------:|:-----:|:-----------------------------------------------------|
| Example Ingredient  | 1      | cup   | Diced                                                |
||||

## Instructions

1. **Step Name:** Step description.
2. **Step Name:** Step description.

**Notes:**

* **Note Title:** Note details.

**Source:**
```

### Formatting Rules

- **Title (`# Recipe Title`):** Use title case. Use the exact title from the page unless a title override is specified in the task list below.
- **Source link:** Always use the original URL as the `[From Here](URL)` link. Do not leave a separate `**Source:**` line — leave it blank (just the label with no value, or omit it entirely if there are no source-specific notes).
- **Intro blockquote (`>`):** Write a brief, enticing 1–2 sentence description. Pull from the page intro or write one that matches the dish.
- **Ingredients table:**
  - Columns: `Ingredient`, `Qty`, `Unit`, `Notes`
  - Use `||||` (empty row) to visually separate ingredient groups (e.g., sauce from main, wet from dry).
  - `Qty` and `Unit` columns are center-aligned. `Ingredient` and `Notes` are left-aligned.
  - Leave `Unit` blank for items that have no unit (e.g., eggs, whole garlic cloves if counted as "cloves" goes in unit).
  - Common unit abbreviations: `tsp`, `Tbsp`, `cup`, `oz`, `lbs`, `pkg`, `cloves`, `cans`.
  - Put preparation details in `Notes` (e.g., "Diced", "Minced", "To taste", "Optional").
- **Instructions:**
  - Number each step.
  - Bold the step label (e.g., `**Saute:**`).
  - Combine small steps where it reads naturally; don't fragment into micro-steps.
- **Notes section:**
  - Use bullet points with bold labels.
  - Include any tips, substitutions, or make-ahead info from the original page.
  - If no relevant notes exist, omit the Notes section entirely.
- **File naming:** Use title case with spaces, e.g., `White Chicken Chili.md`. Match the recipe title used in the file.

---

## Available Folders

Place each recipe in the most appropriate folder:

| Folder       | Use For                                                       |
|:-------------|:--------------------------------------------------------------|
| `BakedGoods` | Breads, muffins, biscuits, cookies, pastries                  |
| `Breakfast`  | Breakfast or brunch dishes                                    |
| `Dessert`    | Cakes, pies, puddings, sweet cookies, ice cream               |
| `Dinner`     | Main dinner dishes, proteins, pasta, rice bowls               |
| `Drinks`     | Beverages, cocktails, hot drinks, smoothies                   |
| `Sauces`     | Sauces, dressings, condiments, glazes                         |
| `Seasonings` | Dry rubs, spice blends                                        |
| `Sides`      | Side dishes, salads, appetizers                               |
| `Snacks`     | Snacks, appetizers, light bites                               |
| `Soups`      | Soups, stews, chilis                                          |

---

## Recipes to Extract

Process each recipe below. The **File Path** column shows exactly where to save the file.

| # | URL | Title Override | File Path |
|:--|:----|:---------------|:----------|
| 1 | https://tastesbetterfromscratch.com/creamy-white-chicken-chili/ | Creamy White Chicken Chili | `Soups/Creamy White Chicken Chili.md` |
| 2 | https://tastesbetterfromscratch.com/pad-thai/ | *(none — use page title)* | `Dinner/Pad Thai.md` |
| 3 | https://sugarspunrun.com/big-soft-oatmeal-cookies/ | Big Soft Oatmeal Cookies | `BakedGoods/Big Soft Oatmeal Cookies.md` |
| 4 | https://www.simplyrecipes.com/recipes/shrimp_po_boy_sandwich/ | Shrimp Po Boy Sandwich | `Dinner/Shrimp Po Boy Sandwich.md` |
| 5 | https://www.kitchensanctuary.com/honey-garlic-chicken/ | Honey Garlic Chicken | `Dinner/Honey Garlic Chicken.md` |
| 6 | https://www.allrecipes.com/recipe/219170/ham-and-split-pea-soup-recipe-a-great-soup/ | Ham and Split Pea Soup | `Soups/Ham and Split Pea Soup.md` |
| 7 | https://foodwishes.blogspot.com/2015/12/homemade-instant-hot-chocolate-mix.html | Homemade Instant Hot Chocolate Mix | `Drinks/Homemade Instant Hot Chocolate Mix.md` |
| 8 | https://www.allrecipes.com/recipe/259887/simple-teriyaki-sauce/ | Simple Teriyaki Sauce | `Sauces/Simple Teriyaki Sauce.md` |
| 9 | https://joyfoodsunshine.com/asian-chicken-lettuce-wraps/ | Chicken Lettuce Wraps | `Dinner/Chicken Lettuce Wraps.md` |
| 10 | https://smittenkitchen.com/2017/03/mushroom-tartines/ | Mushroom Tartines | `Dinner/Mushroom Tartines.md` |

> **Note for Recipe #9:** The source page title may include "Asian" — remove it from the title. The file should be named `Chicken Lettuce Wraps.md`.

---

## Completion Summary

After all recipes have been extracted and saved, provide a summary in the following format:

```
## Recipe Extraction Summary

| # | Recipe Title | Folder | File |
|:--|:-------------|:-------|:-----|
| 1 | Creamy White Chicken Chili | Soups | Creamy White Chicken Chili.md |
| 2 | Pad Thai | Dinner | Pad Thai.md |
| 3 | Big Soft Oatmeal Cookies | BakedGoods | Big Soft Oatmeal Cookies.md |
| 4 | Shrimp Po Boy Sandwich | Dinner | Shrimp Po Boy Sandwich.md |
| 5 | Honey Garlic Chicken | Dinner | Honey Garlic Chicken.md |
| 6 | Ham and Split Pea Soup | Soups | Ham and Split Pea Soup.md |
| 7 | Homemade Instant Hot Chocolate Mix | Drinks | Homemade Instant Hot Chocolate Mix.md |
| 8 | Simple Teriyaki Sauce | Sauces | Simple Teriyaki Sauce.md |
| 9 | Chicken Lettuce Wraps | Dinner | Chicken Lettuce Wraps.md |
| 10 | Mushroom Tartines | Dinner | Mushroom Tartines.md |

**Total:** 10 recipes extracted.
**Folders used:** Soups (×2), Dinner (×5), BakedGoods (×1), Drinks (×1), Sauces (×1)
```

If any recipe could not be extracted (e.g., page blocked, paywall, missing content), note it in the summary with a status of `FAILED` and a brief reason.
