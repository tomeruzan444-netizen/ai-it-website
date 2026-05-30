# AI IT Website - Claude Code Context

## הקשר כללי

אתה בונה את **AI IT** - פורטל הבינה המלאכותית הגדול בישראל.
המייסד הוא **תומר**, יועץ AI לעסקים קטנים ובינוניים (SMB).
המטרה: להנגיש AI לבעלי עסקים ישראלים, לספק תוכן מעמיק ואמין, ולהוביל גולשים להשאיר פרטים לשיחת ייעוץ חינמית עם תומר.
הסגנון: חבר מומחה שמסביר דבר מורכב בפשטות - חם, ישיר, מתוך ניסיון אמיתי.

---

## ארכיטקטורת האתר - רשימת כל הקבצים לבנות

```
ai-it-website/
├── index.html              - דף הבית
├── ai-implementation.html  - הטמעת AI בארגון
├── ai-automation.html      - אוטומציה לעסקים
├── ai-consulting.html      - ייעוץ טכנולוגי
├── ai-solutions.html       - פתרונות AI
├── claude.html             - המדריך המלא ל-Claude
├── chatgpt.html            - המדריך המלא ל-ChatGPT
├── gemini.html             - המדריך המלא ל-Gemini
├── grok.html               - המדריך המלא ל-Grok
├── perplexity.html         - המדריך המלא ל-Perplexity
├── sitemap.xml
└── robots.txt
```

סה"כ: 10 עמודי HTML + sitemap + robots.txt

**כל עמוד הוא קובץ HTML עצמאי עם CSS ו-JS מוטמעים בתוכו. אין קבצים חיצוניים.**

---

## URLs - קצרים, באנגלית, משמעותיים

```
https://ai-it.co.il/                    → index.html
https://ai-it.co.il/ai-implementation   → ai-implementation.html
https://ai-it.co.il/ai-automation       → ai-automation.html
https://ai-it.co.il/ai-consulting       → ai-consulting.html
https://ai-it.co.il/ai-solutions        → ai-solutions.html
https://ai-it.co.il/claude              → claude.html
https://ai-it.co.il/chatgpt             → chatgpt.html
https://ai-it.co.il/gemini              → gemini.html
https://ai-it.co.il/grok                → grok.html
https://ai-it.co.il/perplexity          → perplexity.html
```

---

## דרישות טכניות ו-SEO - חובה בכל עמוד

### HTML סמנטי (קריטי לגוגל ולמנועי AI)

```html
<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>[כותרת ייחודית עד 60 תווים]</title>
  <meta name="description" content="[תיאור ייחודי עד 155 תווים]">
  <meta name="robots" content="index, follow">
  <link rel="canonical" href="https://ai-it.co.il/[שם-עמוד]">

  <!-- Open Graph -->
  <meta property="og:title" content="[כותרת]">
  <meta property="og:description" content="[תיאור]">
  <meta property="og:url" content="https://ai-it.co.il/[עמוד]">
  <meta property="og:type" content="website">
  <meta property="og:locale" content="he_IL">
  <meta property="og:site_name" content="AI IT">

  <!-- Schema JSON-LD ייחודי לכל עמוד -->
  <script type="application/ld+json">{ ... }</script>
</head>
```

### כללי SEO קבועים

- H1 אחד בלבד בכל עמוד
- היררכיה: H1 > H2 > H3 - אין דילוג
- Alt text תיאורי לכל SVG ואלמנט ויזואלי
- Internal linking: כל עמוד מקשר לפחות ל-4 עמודים אחרים בצורה טבעית בתוך הטקסט
- Breadcrumb navigation בכל עמוד פנימי
- Anchor links לסקשנים ארוכים (id על כל H2)

### ביצועים (Core Web Vitals)

- CSS מוטמע ב-`<style>` ב-head בלבד - אין קובץ חיצוני
- JS מינימלי, מוטמע לפני `</body>`
- אין תמונות חיצוניות - כל הויזואלים SVG inline או CSS טהור
- `font-display: swap` על כל פונטים
- `loading="lazy"` על כל אלמנט כבד
- Skip to content: `<a href="#main-content" class="skip-link">דלג לתוכן</a>`

### נגישות WCAG AA

- `aria-label` על כל כפתור ולינק ללא טקסט ברור
- ניגודיות צבעים מינימום 4.5:1
- Focus styles גלויים
- כל טופס עם `<label>` מתאים

---

## עיצוב ומיתוג

### פלטת צבעים

```css
:root {
  --primary:       #0A0F1E;
  --primary-light: #111827;
  --surface:       #161D2E;
  --accent:        #3B82F6;
  --accent-warm:   #F59E0B;
  --accent-glow:   rgba(59,130,246,0.12);
  --text-primary:  #F9FAFB;
  --text-secondary:#9CA3AF;
  --border:        #1F2937;
  --success:       #10B981;
}
```

### פונטים

```css
@import url('https://fonts.googleapis.com/css2?family=Heebo:wght@300;400;500;700;900&family=Space+Mono:wght@400;700&display=swap');
body { font-family: 'Heebo', sans-serif; }
.mono, .stat-number, code, pre { font-family: 'Space Mono', monospace; }
```

### עקרונות עיצוב

- Dark mode first - רקע כהה בכל האתר
- Whitespace נדיב - אל תדחוס תוכן
- כרטיסים: `border: 1px solid var(--border)` + `border-radius: 12px`
- Hover: `transform: translateY(-2px)` + `border-color: var(--accent)` (transition 200ms)
- Glow עדין: `box-shadow: 0 0 20px var(--accent-glow)`
- אייקונים: SVG inline בלבד - אין ספריות חיצוניות
- **אין מקף ארוך — בשום מקום - רק -**

---

## מבנה Layout - זהה בכל עמוד

```
┌─────────────────────────────────────────┐
│  HEADER (sticky)                        │
├─────────────────────────────────────────┤
│  HERO (full width)                      │
├────────────────────┬────────────────────┤
│  MAIN CONTENT ~68% │  SIDEBAR ~28%      │
│                    │  sticky top:80px   │
├─────────────────────────────────────────┤
│  FULL WIDTH SECTIONS (FAQ, CTA)         │
├─────────────────────────────────────────┤
│  FOOTER                                 │
└─────────────────────────────────────────┘
```

---

## Header - זהה בכל עמוד

```html
<header class="site-header">
  <div class="container">
    <a href="index.html" class="logo" aria-label="AI IT - דף הבית">
      <span class="logo-ai">AI</span><span class="logo-it">IT</span>
    </a>
    <nav aria-label="תפריט ראשי">
      <ul>
        <li><a href="index.html">בית</a></li>
        <li class="has-dropdown">
          <a href="#">שירותים</a>
          <ul class="dropdown">
            <li><a href="ai-implementation.html">הטמעת AI בארגון</a></li>
            <li><a href="ai-automation.html">אוטומציה לעסקים</a></li>
            <li><a href="ai-consulting.html">ייעוץ טכנולוגי</a></li>
            <li><a href="ai-solutions.html">פתרונות AI</a></li>
          </ul>
        </li>
        <li class="has-dropdown">
          <a href="#">כלי AI</a>
          <ul class="dropdown">
            <li><a href="chatgpt.html">ChatGPT</a></li>
            <li><a href="claude.html">Claude</a></li>
            <li><a href="gemini.html">Gemini</a></li>
            <li><a href="grok.html">Grok</a></li>
            <li><a href="perplexity.html">Perplexity</a></li>
          </ul>
        </li>
        <li><a href="#contact">יצירת קשר</a></li>
      </ul>
    </nav>
    <a href="#lead-form" class="btn btn-cta">ייעוץ חינמי</a>
    <button class="hamburger" aria-label="פתח תפריט">
      <span></span><span></span><span></span>
    </button>
  </div>
</header>
```

עיצוב לוגו: "AI" - `color: var(--accent)` + `font-weight: 900` | "IT" - `color: var(--accent-warm)` + `font-weight: 900` | גודל 28px, ללא תמונה

---

## Footer - זהה בכל עמוד

4 עמודות:

1. אודות AI IT - תיאור קצר + "כל הזכויות שמורות AI IT 2025"
2. שירותים - לינקים לכל 4 עמודי שירות
3. כלי AI - לינקים לכל 5 עמודי כלים
4. יצירת קשר - טופס מיני

Schema Organization בפוטר:

```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "AI IT",
  "url": "https://ai-it.co.il",
  "founder": {"@type": "Person", "name": "תומר"},
  "description": "פורטל הבינה המלאכותית הגדול בישראל",
  "areaServed": "IL"
}
```

---

## סיידבר - מותאם לכל קבוצת עמודים

### סיידבר דף הבית:
- כרטיס "דבר עם תומר" + טופס ליד מיני
- "השירותים שלי" - 4 לינקים לעמודי שירות
- "כלי AI מומלצים" - 5 לינקים לעמודי כלים
- "מאמרים אחרונים" - 5 placeholder כותרות

### סיידבר עמודי שירות (ai-implementation, ai-automation, ai-consulting, ai-solutions):
- כרטיס "רוצה להתחיל?" + CTA בולט + טופס
- "תוכן עניינים" - anchor links לסקשנים בעמוד
- "שירותים קשורים" - לינקים ל-3 עמודי שירות אחרים
- "כלים שאני משתמש בהם" - לינקים לעמודי כלים רלוונטיים

### סיידבר עמודי כלים (claude, chatgpt, gemini, grok, perplexity):
- "השווה כלים" - mini comparison table
- "כלי AI נוספים" - לינקים לכל שאר עמודי הכלים
- "מקרי שימוש מהירים" - 5 bullet points
- כרטיס "רוצה ללמוד להשתמש?" + CTA

---

## כללי כתיבת תוכן - חובה לעמוד בהם

### סגנון ו-E-E-A-T

כתוב בגוף ראשון מלא מאת תומר. כל טענה מגובה בניסיון אישי, מספר, או פרויקט ספציפי.

**חוקים קשיחים:**
- פסקאות מקסימום 3 משפטים - לא יותר
- אחרי כל 2-3 פסקאות - תבליטים, טבלה, או אלמנט ויזואלי
- **אין מקף ארוך — - רק -**
- אין AI clichés: "עולם דינמי", "נוף משתנה", "בעידן ה-AI"
- אין מילות מילוי: "כמובן", "בהחלט", "ללא ספק"
- אין פתיחות גנריות: "בעולם של היום...", "כולנו יודעים ש..."

**חובה:**
- כל 300 מילה - לפחות דוגמה ספציפית אחת עם מספרים
- כל סקשן - פסקה אחת לפחות בגוף ראשון ("אני", "עבדתי", "ראיתי")
- ציון שגיאות ומגבלות - מומחה אמיתי לא משבח הכל
- "לקח" או "מה זה אומר עליך" בסיום כל סקשן עיקרי

### מבנה פסקה אידיאלי

```
הצהרה ישירה. (משפט 1)
הסבר קצר עם ניסיון. (משפט 2-3)

- נקודה ספציפית עם מספר
- נקודה ספציפית עם עובדה
- נקודה ספציפית עם תוצאה

לקח: [חיבור לקורא]
```

### אלמנטים ויזואלים - חובה בכל עמוד

- **Stat Cards** (3-4) - מספרים בולטים עם Space Mono
- **Info Boxes** (2-3) - אייקון SVG + כותרת + 2-3 שורות
- **Process Steps** - ממוספרים עם קו מחבר ויזואלי
- **Comparison Table** (1-2) - עיצוב מותאם
- **Quote Block** - ציטוט מתומר עם border-right + background
- **Callout Box** - רקע `var(--accent-glow)` לדגשים
- **Terminal Block** - לדוגמאות Prompt, רקע כהה + Space Mono
- **Case Study Card** - כרטיס עם 4 tabs: רקע | אתגר | פתרון | תוצאות

---

## בנק פרויקטים - השתמש בהם לאורך כל האתר

### פרויקט 1 - חברת ביטוח (12 עובדים, תל אביב)

**רקע:** חברת ביטוח בינונית. 4 נציגי שירות, עומס גבוה, תגובות איטיות.

**אתגר:** כל נציג בזבז 3 שעות ביום בכתיבת מיילים ידנית - הסברים על פוליסות, טיפול בתביעות, חידושים.

**פתרון:** prompt library ב-Claude עם 22 תבניות מייל. 6 שבועות עבודה - שבוע מיפוי, שבועיים בניית תבניות, שבועיים הדרכה, שבוע כיול.

**תוצאות:**
- חיסכון של 2.5 שעות יומי לנציג (10 שעות לצוות)
- שביעות רצון לקוחות עלתה ב-18% תוך 3 חודשים
- הנציגים דיווחו על פחות עייפות ויותר זמן לשיחות מורכבות

**לקח מתומר:** "הדבר שהכי עזר לא היה ה-AI עצמו - היה זה המיפוי. כשישבנו וכתבנו 22 סיטואציות שחוזרות על עצמן, בעל החברה הבין לראשונה כמה זמן הולך לבזבוז אמיתי."

---

### פרויקט 2 - רשת אופנה (4 סניפים, 30 עובדים)

**רקע:** מנהלת שיווק אחת לכל הרשת. עומס קיצוני.

**אתגר:** 60 שעות שבוע, ורוב הזמן על כתיבת פוסטים, תיאורי מוצרים, ניהול מיילים.

**פתרון:** 3 חודשי עבודה:
- שלב 1 (2 שבועות) - מיפוי כל פעולות השיווק
- שלב 2 (3 שבועות) - בניית "מוח המותג" ב-Claude: קול המותג, 6 קהלי יעד, 40 מסרים ליבה
- שלב 3 (3 שבועות) - workflow ייצור תוכן שבועי: 4 שעות במקום 20
- שלב 4 (4 שבועות) - אינטגרציה עם Canva API לוויזואלים אוטומטיים

**תוצאות:**
- המנהלת עובדת 42 שעות (ירידה מ-60)
- כמות התוכן עלתה ב-300%
- מכירות אונליין עלו ב-23% תוך 6 חודשים

**לקח מתומר:** "ה'מוח המותג' שבנינו ב-Claude הוא הנכס האמיתי. זה לקח 3 שבועות לבנות ואף אחד לא מספר לך עליו בפוסטים שאתה רואה בלינקדאין."

---

### פרויקט 3 - משרד עורכי דין (8 עו"ד)

**רקע:** משרד בינוני - מסחרי, נדל"ן, עבודה.

**אתגר:** עו"ד מבכירים בזבזו שעות על ניסוח חוזים סטנדרטיים, תמצות פסיקות, מענה ראשוני לפניות.

**פתרון:** 4 חודשים - הפרויקט המורכב ביותר שביצעתי:
- שלב 1 - מיפוי 40 סוגי מסמכים, מיון לפי מורכבות
- שלב 2 - prompt library ב-Claude עם 40 templates ייעודיים
- שלב 3 - מערכת תמצות פסיקות: פסיקה של 80 עמוד הופכת לתמצות של 2 עמוד
- שלב 4 - הדרכה מותאמת לכל עו"ד לפי תחום התמחות

**תוצאות:**
- 35% קיצור בזמן ניסוח מסמכים סטנדרטיים
- כל עו"ד פינה 8 שעות שבועיות לעבודה בעלת ערך גבוה
- המשרד גייס 4 לקוחות גדולים כי פתאום היה זמן לפנות אליהם

**אזהרה מתומר:** "כל מסמך שיצא מ-Claude עבר בדיקת עו"ד. AI לא מחליף את הבדיקה המשפטית - הוא מייצר טיוטה ראשונה מהירה יותר."

---

### פרויקט 4 - סוכנות נדל"ן (15 סוכנים)

**רקע:** סוכנות פעילה, הרבה נכסים, מעט זמן.

**אתגר:** כל סוכן בזבז 5 שעות שבוע על פרסומי נכסים, מענה ראשוני ללידים, הכנת מצגות.

**פתרון:** 6 שבועות, focus על אינטגרציה עם מערכות קיימות:
- ChatGPT + Zapier + CRM: כל נכס חדש מייצר 3 גרסאות פרסום אוטומטית
- Claude לכתיבת דוחות שמאות ראשוניים
- מערכת מענה ראשוני ללידים תוך דקות

**תוצאות:**
- 4.5 שעות חיסכון שבועי לסוכן (67.5 שעות לצוות)
- 40% עלייה בנכסים מפורסמים באותו גודל צוות
- זמן תגובה ללידים ירד מ-4 שעות ל-12 דקות
- סגירת עסקאות עלתה ב-15%

---

### פרויקט 5 - מסעדה (2 סניפים)

**רקע:** בעל מסעדה שניהל לבד את כל השיווק. ידע בישול, לא ידע AI.

**אתגר:** פוסטים, ביקורות, תפריטים עונתיים - הכל על אחד.

**פתרון:** 2 שבועות - הפרויקט הקצר עם ה-ROI הגבוה ביותר:
- ChatGPT לניסוח תגובות לביקורות Google
- Claude לתפריטים עונתיים ותיאורי מנות
- Canva AI לוויזואלים

**תוצאות:**
- 6 שעות חיסכון שבועי
- דירוג Google עלה מ-4.1 ל-4.6 תוך 3 חודשים
- "לראשונה מזה שנתיים יש לי ערב אחד בשבוע פנוי"

**לקח מתומר:** "לפעמים הפרויקטים הכי פשוטים הם אלה שמשנים חיים. לא צריך אינטגרציה מורכבת כדי לראות תוצאות."

---

### פרויקט 6 - חברת תוכנה B2B (50 עובדים)

**רקע:** חברת SaaS ישראלית, 18 מפתחים.

**אתגר:** 30% מזמן הפיתוח על דוקומנטציה, code review, ובאגים שגרתיים.

**פתרון:** 4 חודשים מלאים:
- שלב 1 - Claude Code לעזרה ב-code review: כל PR עובר סריקת AI לפני review אנושי
- שלב 2 - GitHub Copilot לכל הצוות + 3 ימי הדרכה
- שלב 3 - ChatGPT לכתיבת דוקומנטציה אוטומטית
- שלב 4 - pipeline שלם: קוד נכתב, AI בודק, AI מתעד, אנשים מאשרים

**תוצאות:**
- 25% עלייה בתפוקת צוות הפיתוח
- 40% ירידה בבאגים ב-production
- כל מפתח חסך 6 שעות שבועיות
- זמן onboarding למפתח חדש ירד מ-3 שבועות לשבוע וחצי

---

### פרויקט 7 - רשת קליניקות (6 קליניקות, 40 עובדים)

**רקע:** רשת פיזיותרפיה. הרבה ניירת, מעט סדר.

**אתגר:** תיאום תורים, מענה לפניות, דוחות חודשיים - כולם ידניים.

**פתרון:** 3 חודשים:
- אוטומציה של מענה ראשוני בווטסאפ + ChatGPT
- Claude לכתיבת דוחות טיפול מובנים מהערות קצרות
- סיכום חודשי אוטומטי: מנהל מקבל דוח ב-30 שניות

**תוצאות:**
- כל פיזיותרפיסט חסך 45 דקות ביום
- תגובה לפניות: מ-6 שעות ל-4 דקות
- "לראשונה אנחנו מסתכלים על הנתונים כי עכשיו הם נגישים"

---

## עמוד 1: דף הבית (index.html)

### Meta Tags

```html
<title>AI IT - פורטל הבינה המלאכותית לעסקים ישראלים</title>
<meta name="description" content="AI IT הוא פורטל ה-AI הגדול בישראל. מדריכי ChatGPT, Claude, Gemini, הטמעת AI לעסקים וייעוץ מאת תומר - יועץ AI לעסקים קטנים ובינוניים.">
<meta property="og:title" content="AI IT - פורטל הבינה המלאכותית לעסקים ישראלים">
<meta property="og:description" content="מדריכי AI, הטמעת AI לעסקים וייעוץ אישי מאת תומר. מנגיש את עולם הבינה המלאכותית לעסקים ישראלים.">
```

### Schema JSON-LD

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebSite",
      "name": "AI IT",
      "url": "https://ai-it.co.il",
      "inLanguage": "he"
    },
    {
      "@type": "Organization",
      "name": "AI IT",
      "url": "https://ai-it.co.il",
      "founder": {"@type": "Person", "name": "תומר"},
      "description": "פורטל הבינה המלאכותית הגדול בישראל"
    }
  ]
}
```

### מבנה הדף

**1. Hero Section (full width)**
- H1: "AI IT - הפורטל הישראלי לבינה מלאכותית"
- תת-כותרת: "אני תומר. אני עוזר לבעלי עסקים ישראלים לשלב AI בעסק שלהם - בלי מינוח מסובך, בלי בלבול."
- אנימציית CSS typing effect על מילים מתחלפות: "ChatGPT" / "Claude" / "Gemini"
- 2 כפתורים: "התחל עם ייעוץ חינמי" (primary) + "קרא מדריכים" (secondary)
- Stat bar: 7 פרויקטים | 150+ שעות חסכון | 5 כלי AI | ייעוץ חינמי

**2. About Tomer Section**
- תמונה placeholder (SVG avatar) + ביוגרפיה קצרה
- ניסיון: 7 פרויקטים מוכחים, SMB focus
- CTA: "קרא עליי עוד" + "שוחח עם תומר"

**3. Services Section (4 כרטיסים)**
- הטמעת AI בארגון - ai-implementation.html
- אוטומציה לעסקים - ai-automation.html
- ייעוץ טכנולוגי - ai-consulting.html
- פתרונות AI - ai-solutions.html

**4. AI Tools Section (5 כרטיסים)**
- ChatGPT, Claude, Gemini, Grok, Perplexity
- כל כרטיס: לוגו SVG + תיאור 1 שורה + לינק לעמוד

**5. Case Studies Section**
- 3 כרטיסי case study מקוצרים (מהבנק למעלה)
- כפתור "ראה עוד מקרים"

**6. Lead Form Section (full width, id="lead-form")**
- כותרת: "ייעוץ חינמי עם תומר - 30 דקות שיכולות לשנות את העסק שלך"
- שדות: שם | טלפון | אימייל | תחום עסק | כפתור שליחה
- תחת הטופס: "מגיב תוך 24 שעות | ללא התחייבות | שיחה בעברית"

**7. FAQ Section**
- 6 שאלות נפוצות בפורמט accordion
- Schema FAQ markup

---

## הנחיות עבודה כלליות

1. **בנה קובץ אחד בכל פעם** - אל תבנה כמה קבצים במקביל
2. **בדוק internal links** - כל לינק מצביע לקובץ שנבנה
3. **שמור עקביות** - header ו-footer זהים בכל הקבצים
4. **אל תשנה URLs** - השתמש ברשימה הסופית למעלה
5. **טופס הליד** - id="lead-form" בכל עמוד, עם שדות זהים
6. **Mobile first** - בדוק responsive בכל קובץ
