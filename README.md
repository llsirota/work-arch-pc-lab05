; hello.asm
SECTION .data ; Начало секции данных
msg: DB 'Лев Сирота',0xa
len: EQU $-msg ; Длина строки hello
SECTION .text ; Начало секции кода
GLOBAL _start
_start: 
mov eax,4 ; Системный вызов для записи (sys_write)
mov ebx,1 ; Описатель файла '1' - стандартный вывод
mov ecx,msg ; Адрес строки hello в ecx
mov edx,len ; Размер строки hello
int 80h ; Вызов ядра
mov eax,1 ; Системный вызов для выхода (sys_exit)
mov ebx,0 ; Выход с кодом возврата '0' (без ошибок)
int 80h ; Вызов ядра
