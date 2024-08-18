#  Template class of Tree and Iterators
## Project Description
In this project i implemented a template container that represents a K-ary tree that can hold Nodes of any type.

# All the different classes and their hierarchy
 tree.hpp - a Template K-ary tree container, has a Node<T>* root. uses the iterators.hpp to travers the tree in different ways (depends what K is the tree). the tree class uses the type_traits library to use compile-time type manipulation based on certain conditions (see Explenation about the tree container usage with iterators below for additional explenation). In order to print the tree using gui we used QT library.
 node.hpp - a Template Node class to hold any type.
complex.hpp - represents complex numbers, can be used by node.hpp to store complex numbers as data.
We have 6 different iterator classes inside the file iterators.hpp:
in_order_iterator - Traverses Binary tree in in-order way, for any (K!=2)-Tree will travers the tree using dfs.
pre_order_iterator - Traverses Binary tree in pre-order way, for any (K!=2)-Tree will travers the tree using dfs.
post_order_iterator - Traverses Binary tree in post-order way, for any (K!=2)-Tree will travers the tree using dfs.
min_heap_iterator - Turns a Binary tree to a minimum heap and travers it ,for any (K!=2)-Tree will travers the tree using dfs.
dfs_iterator - Works on any K-tree.
bfs_iterator - Works on any K-tree.





בפרויקט הזה מימשנו קונטיינר המייצג עץ k-ארי (עץ k-ארי הוא עץ שבו לכל קודקוד יש לכל היותר k ילדים. למשל, עץ בינארי הוא עץ 2-ארי.) גנרי שמכיל מפתחות מכל סוג (למשל מספרים, מחרוזות ומחלקות). 
המצב הדיפולטיבי של העץ הוא עץ בינארי (כלומר k=2). בשלב היצירה של הקונטיינר עליכם יהיה לציין את הסוג של המפתחות שהוא מכיל ואת מספר הילדים המקסימלי שיכול להיות לכל קודקוד. אם המספר הזה לא צוין, העץ יהיה עץ בינארי.
 המכיל את האיטרטורים הבאים:
1. איטרטור Pre-Order - איטרטור הסורק את העץ בצורה הבאה: צומת נוכחית -> תת עץ שמאלי -> תת עץ ימני (האיטרטור הזה עובד בצורה הזאת עבור עץ בינארי בלבד! עבור עץ כללי החזירו סריקת DFS רגילה שמתחילה מהשורש של העץ).
2. איטרטור Post-Order - איטרטור הסורק את העץ בצורה הבאה: תת עץ שמאלי -> תת עץ ימני -> צומת נוכחית (האיטרטור הזה עובד בצורה הזאת עבור עץ בינארי בלבד! עבור עץ כללי החזירו סריקת DFS רגילה שמתחילה מהשורש של העץ).
3. איטרטור In-Order  - איטרטור הסורק את העץ בצורה הבאה: תת עץ שמאלי -> צומת נוכחית -> תת עץ ימני (האיטרטור הזה עובד בצורה הזאת עבור עץ בינארי בלבד! עבור עץ כללי החזירו סריקת DFS רגילה שמתחילה מהשורש של העץ).
5. איטרטור BFS - סריקת העץ לרוחב (משמאלי לימין) (עובד על עץ כללי).
6. איטרטור DFS - סריקת העץ בעזרת אלגוריתם DFS (עובד על עץ כללי).
7. איטרטור Heap - הפיכת עץ בינארי לערימת מינימום, לקריאה נוספת: https://he.wikipedia.org/wiki/%D7%A2%D7%A8%D7%99%D7%9E%D7%94_%D7%91%D7%99%D7%A0%D7%90%D7%A8%D7%99%D7%AA .

שם הקונטיינר צריך להיות `tree`. ויש בו את המתודות הבאות:
1. המתודה `add_root` - הוספת השורש של העץ. המתודה מקבלת צומת כלשהו ושמה אותו בשורש העץ.
2. המתודה `add_sub_node` - הוספת ילד לאב. המתודה מקבלת צומת בעץ וצומת כלשהו ויוצרת בן עבור אותו צומת.
3. המתודות `begin_pre_order`, `end_pre_order`. המתודות מחזירות איטרטורים לצורך מעבור על העץ בשיטת Pre-Order.
4. המתודות `begin_post_order`, `end_post_order`. המתודות מחזירות איטרטורים לצורך מעבור על העץ בשיטת Post-Order.
5. המתודות `begin_in_order`, `end_in_order`. המתודות מחזירות איטרטורים לצורך מעבור על העץ בשיטת In-Order.
6. המתודות `begin_bfs_scan`, `end_bfs_scan`. המתודות מחזירות איטרטורים לצורך מעבור על העץ בעזרת האלגוריתם BFS.
7. המתודות `begin_dfs_scan`, `end_dfs_scan`. המתודות מחזירות איטרטורים לצורך מעבור על העץ בעזרת האלגוריתם DFS.
8. המתודה `myHeap`. המתודה מקבלת איטרטורים לעץ בינארי ומחזירה איטרטורים עבור הערימה שהתקבלה.
9. יש לממש מפרק (Destructor) המוחק את כל העץ.
10. אופרטור פלט. הפלט יהיה בעזרת GUI. עליכם ליצור ממשק שמדפיס את העץ על המסך בצורה הגיוניות לשיקולכם.

בנוסף יש בפרויקט גם מחלקת complex (מספרים ממשים)

# הערות 
1. בבנאי כאשר מוסיפים ילדים לקודקוד הבנים נוספים משמאל לימין
2. ניתן להוסיף ילדים רק באמצעות המתודה add_sub_node
3. בפרויקט שמתי את כל המימושים בקובץ hpp מכיון שמדובר במחלקות template , עבור כל איטרטור בניתי מחלקה שמששמת את כל האופרטורים הדרושים לאיטרטור ועוד פונקציות נוספות למימוש הלוגיקה של המעבר על העץ.


