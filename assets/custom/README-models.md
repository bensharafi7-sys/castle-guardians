# מודלים מקצועיים — הוראות חיבור

1. מעתיקים לתיקייה הזו (`assets/custom/`) קובצי GLB של הדמויות. כל דמות צריכה **שלד (Rig)** ואנימציות בתוך הקובץ, ורצוי טקסטורה אחת (Atlas) או צבעי חומר.
2. יוצרים כאן קובץ `models.json` (אפשר להעתיק את `demo.json` כתבנית):

```json
{
  "units": {
    "knight":  { "file": "my_knight",  "height": 1.45, "rotateY": 0,
                 "anims": { "idle": "Idle", "move": "Run", "atk": "Attack", "die": "Death" } },
    "soldier": { "file": "my_archer",  "anims": { "idle": "Idle", "move": "Run", "atk": "Shoot", "die": "Death" } },
    "minion":  { "file": "my_goblin",  "anims": { "idle": "Idle", "move": "Run", "atk": "Attack", "die": "Death" } }
  },
  "heroes": {
    "hero": { "file": "my_hero", "anims": { "idle": "Idle", "move": "Run", "atk": "Shoot", "die": "Death", "cast": "Cast" } }
  }
}
```

**שמות היחידות:** `soldier` (קשתים), `knight` (אבירים), `horse` + `rider` (פרשים), `minion`, `srogue`, `warrior`, `warriorS`, `minionB`, `smage` (אויבים). גיבורים: `hero`, `heroKnight`, `heroMage`.

- `file`: שם הקובץ בלי סיומת. באפליקציה נטען `.glb`, ובגרסת הדפדפן נטען `.json` (glTF מוטמע).
- `height`: גובה הדמות במשחק, ביחידות עולם. אביר רגיל הוא בערך 1.4.
- `rotateY`: סיבוב במעלות, אם הדמות פונה לכיוון הלא נכון.
- `anims`: שמות האנימציות כפי שהם מופיעים בקובץ. אם יש קידומת כמו `Armature|Run`, מספיק לכתוב `Run`.

**בדיקה:** פותחים את המשחק עם `?models` בכתובת, ומופיעה טבלה עם כל מודל: פעיל ✓, או מה חסר (קובץ, שלד, אנימציות). אנימציות שקיימות בקובץ מוצגות בטבלה. מודל שנכשל לא נטען, והמשחק ממשיך עם הדמות המובנית.

**הדגמה:** `?demo=models` טוען את `demo.json`, שמחליף את האבירים באביר CC0 של Quaternius, כדי להראות שהצינור עובד.
