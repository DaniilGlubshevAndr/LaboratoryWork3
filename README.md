Salt-and-pepper noise filtering on GPU
=====================
В программе на Python в среде Google Colaboratory реализован медианный фильтр "соль и перец" (фильтрация шума).
Для проверки работы программы на вход подадим 2 фотографии: 512х512 и 1024х1024. Для каждой рассмотрим фильтр 3х3 и 5х5.

512х512
Фильтр | Время CPU | Время GPU | Ускорение | 
--- | --- | --- | --- |
3х3 | 2104.34024 | 0.59865 | 3515.16531 | 
5х5 | 4969.09584 | 2.54651 | 1951.33856 | 

1024х1024
Фильтр | Время CPU | Время GPU | Ускорение | 
--- | --- | --- | --- |
3х3 | 8634.49404 | 1.63751 | 5272.95441 | 
5х5 | 19760.58671 | 8.44777 | 2339.14856 | 

Из таблиц виден очевидный прирост производительности при исользовании PyCuda. 
Чем больше размер файла, тем дольше происходит фильтрация

**Пример работы программы <br />**
![Image alt](https://github.com/DaniilGlubshevAndr/skrin/blob/main/scrin1.jpg)

Исходное изображение:

![Image alt](https://github.com/DaniilGlubshevAndr/skrin/blob/main/512.bmp)

После применения фильтра (CPU):

![Image alt](https://github.com/DaniilGlubshevAndr/skrin/blob/main/cpu512.bmp)

После применения фильтра (GPU):

![Image alt](https://github.com/DaniilGlubshevAndr/skrin/blob/main/gpu512.bmp)
