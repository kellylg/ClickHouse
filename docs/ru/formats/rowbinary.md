<a name="rowbinary"></a>

# RowBinary

Форматирует и парсит данные по строкам, в бинарном виде. Строки и значения уложены подряд, без разделителей.
Формат менее эффективен, чем формат Native, так как является строковым.

Числа представлены в little endian формате фиксированной длины. Для примера, UInt64 занимает 8 байт.
DateTime представлены как UInt32, содержащий unix timestamp в качестве значения.
Date представлены как UInt16, содержащий количество дней, прошедших с 1970-01-01 в качестве значения.
String представлены как длина в формате varint (unsigned [LEB128](https://en.wikipedia.org/wiki/LEB128)), а затем байты строки.
FixedString представлены просто как последовательность байт.

Array представлены как длина в формате varint (unsigned [LEB128](https://en.wikipedia.org/wiki/LEB128)), а затем элементы массива, подряд.
