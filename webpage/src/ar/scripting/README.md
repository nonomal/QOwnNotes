# برمجة QOwnNotes

أي بُريمج QOwnNotes يكون في معظمه **جافاسكربت** في [ملفات Qt QML](https://doc.qt.io/qt-5/qtqml-index.html).

```js
import QtQml 2.0
import QOwnNotesTypes 1.0

Script {
    /**
        * سيعمل عندما يتهيأ محرك البرمجة
        */
    function init() {
        script.log("Hello world!");
    }
}
```

يمكنك وضع ملفات QML هذه في أي مكان تحبه، ثم **تضيفهم في QOwnNotes** بإضافتهم في **إعدادات البرمجة** (يوجد زر `أضف بُريمِجًا` &gt; `أضف بُريمِجًا محليًا`).

::: tip
ألقِ نظرة على [أمثلة البُريمِجات](https://github.com/pbek/QOwnNotes/blob/develop/docs/scripting/examples) للبدء بسرعة.
:::

في **إعدادات البرمجة**، يمكنك أيضا تثبيت بُريمِجات مباشرةً من [**مستودع البُريمِجات**](https://github.com/qownnotes/scripts).

للإبلاغ عن مشاكل أو أسئلة أو طلبات خصائص لبُريمِج من **مستودع البُريمِجات**، برجاء فتح مسألة على [صفحة مسائل مستودع QOwnNotes للبُريمِجات](https://github.com/qownnotes/scripts/issues).

::: tip
إذا أردت اقتراح بُريمِجًا لنشره في **مستودع البُريمِجات**، نرجو اتباع التعليمات التي في [مستودع بُريمِجات QOwnNotes](https://github.com/qownnotes/scripts).
:::

إذا كنت بحاجة إلى الوصول إلى وظيفة معينة في QOwnNotes أو لديك أسئلة أو أفكار، فيرجى فتح مسألة على [صفحة مسائل QOwnNotes](https://github.com/pbek/QOwnNotes/issues).

::: tip
For logging you can use the `script.log()` command to log to the log widget.
:::