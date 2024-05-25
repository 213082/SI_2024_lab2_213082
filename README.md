# SI_2024_lab2_213082
Leona Negrioska 213082

Control Flow Graph

![213082](https://github.com/213082/SI_2024_lab2_213082/assets/162737828/b9bc2b36-f512-42c5-beab-9c9b662f2bfc)

Цикломатска комплексност:

E е бројот на ребра (edges) во графот: 48. 
N е бројот на јазли (nodes) во графот: 42.
P е бројот на поврзани компоненти: 1.

V(G) = 48−42+2×1 = 12

Тест случаи според критериумот Every statement:
- Случај 1: allItems е null
  Влез: checkCart(null, 100)
  Очекуван излез: RuntimeException("allItems list can't be null!")

- Случај 2: item.getName() == null или item.getName().length() == 0:
  Влез: checkCart([new Item(null, "123", 100, 0)], 100)
  Очекуван излез: true

- Случај 3: item.getBarcode() == null:
  Влез: checkCart([new Item("item", null, 100, 0)], 100)
  Очекуван излез: RuntimeException("No barcode!")

- Случај 4: Невалиден карактер во item.getBarcode():
  Влез: checkCart([new Item("item", "123a", 100, 0)], 100)
  Очекуван излез: RuntimeException("Invalid character in item barcode!")

- Случај 5: Важечки баркод и попуст:
  Влез: checkCart([new Item("item", "123", 100, 0.1f)], 100)
  Очекуван излез: true

- Случај 6: Важечки баркод без попуст:
  Влез: checkCart([new Item("item", "123", 100, 0)], 100)
  Очекуван излез: true

- Случај 7: Условот item.getPrice() > 300 && item.getDiscount() > 0 && item.getBarcode().charAt(0) == '0' е вистинит:
  Влез: checkCart([new Item("item", "0123", 400, 0.1f)], 100)
  Очекуван излез: false

  
Тест случаи според критериумот Every path

- Случај 1: Сите услови се вистинити.
  Влез: checkCart([new Item("item", "0123", 400, 0.1f)], 100)
  Очекуван излез: false

- Случај 2: item.getPrice() <= 300, останатите услови се вистинити.
  Влез: checkCart([new Item("item", "0123", 300, 0.1f)], 100)
  Очекуван излез: true

- Случај 3: item.getDiscount() <= 0, останатите услови се вистинити.
  Влез: checkCart([new Item("item", "0123", 400, 0)], 100)
  Очекуван излез: true

- Случај 4: item.getBarcode().charAt(0) != '0', останатите услови се вистинити.
  Влез: checkCart([new Item("item", "1123", 400, 0.1f)], 100)
  Очекуван излез: false


